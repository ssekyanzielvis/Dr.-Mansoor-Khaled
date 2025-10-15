# Render Deployment Troubleshooting

## Error: Cannot find module '/opt/render/project/src/index.js'

### Problem
Render is trying to run `node index.js` instead of `npm start` (which runs `node server.js`)

### Root Cause
Render is using default Node.js settings instead of reading your configuration.

### Solutions (Try in order)

---

## Solution 1: Update Start Command in Dashboard (RECOMMENDED)

1. Go to https://dashboard.render.com/
2. Click on your service: `dr-mansoor-portfolio`
3. Click **"Settings"** tab (left sidebar)
4. Scroll down to **"Build & Deploy"** section
5. Find **"Start Command"**
6. Change from: `node index.js`
7. Change to: **`npm start`**
8. Click **"Save Changes"** button
9. Render will automatically redeploy with correct command

**Expected Result:** 
- Deployment should succeed
- Server will start with `node server.js`
- Site will be live

---

## Solution 2: Delete and Recreate Service

If updating settings doesn't work:

### Step 1: Delete Current Service
1. Go to Render dashboard
2. Select your service
3. Go to **"Settings"**
4. Scroll to bottom
5. Click **"Delete Web Service"**
6. Confirm deletion

### Step 2: Create New Service with Correct Settings
1. Click **"New +" button**
2. Select **"Web Service"**
3. Connect repository: `Dr.-Mansoor-Khaled`
4. Configure with these EXACT settings:

```
Name: dr-mansoor-portfolio
Region: Any (your preference)
Branch: main
Root Directory: (leave blank)
Environment: Node
Build Command: npm install && npm run build
Start Command: npm start          ← CRITICAL!
```

5. Select **"Free"** plan
6. Click **"Create Web Service"**

---

## Solution 3: Alternative - Use Render Blueprint

1. Make sure `render.yaml` is in your repository root
2. In Render dashboard, create **"New Blueprint Instance"**
3. Select your repository
4. Render will use settings from `render.yaml`

---

## Verification Steps

After deployment, check:

### 1. Build Logs Should Show:
```
==> Running build command 'npm install && npm run build'...
✓ Dependencies installed
✓ CSS compiled to dist/output.css
```

### 2. Start Logs Should Show:
```
==> Running 'npm start'
Server running at http://localhost:[PORT]/
Serving DrMansoorPortifolio.html
```

### 3. Your Site Should:
- Load at the Render URL
- Show all styling (CSS loaded)
- Display images correctly
- Work on all pages

---

## Common Issues & Fixes

### Issue: Build succeeds but start fails
**Fix:** Verify Start Command is `npm start` not `node index.js`

### Issue: "Cannot find module 'postcss'"
**Fix:** Ensure package.json has all dependencies
```bash
npm install --save-dev @tailwindcss/postcss postcss postcss-cli autoprefixer
```

### Issue: CSS not loading
**Fix:** Make sure build command includes `npm run build`

### Issue: Port binding error
**Fix:** Ensure server.js uses `process.env.PORT`:
```javascript
const PORT = process.env.PORT || 3000;
```

---

## Emergency: Deploy Without CSS Build

If CSS build is causing issues, temporarily simplify:

**In Render Settings:**
- Build Command: `npm install`
- Start Command: `npm start`

Then manually build CSS locally and commit:
```bash
npm run build
git add dist/output.css
git commit -m "Add pre-built CSS"
git push
```

---

## Alternative Hosting Options

If Render continues to have issues:

### Option A: Netlify
1. Create `netlify.toml`:
```toml
[build]
  command = "npm run build"
  publish = "."

[[redirects]]
  from = "/*"
  to = "/DrMansoorPortifolio.html"
  status = 200
```
2. Deploy via Netlify dashboard

### Option B: Vercel
Already configured with `vercel.json`
- Deploy via Vercel dashboard
- Or use: `vercel --prod`

### Option C: Railway
1. Add Procfile: `web: npm start`
2. Deploy via Railway dashboard

---

## Checklist Before Deployment

✅ `server.js` exists in root  
✅ `package.json` has `"start": "node server.js"`  
✅ `package.json` has `"build": "npm run build:css"`  
✅ All dependencies in `package.json`  
✅ `DrMansoorPortifolio.html` exists  
✅ `src/input.css` exists  
✅ No syntax errors in any files  
✅ All changes committed and pushed  

---

## Need Help?

1. Check Render logs in dashboard
2. Verify all files committed: `git status`
3. Test locally: `npm start`
4. Check package.json scripts
5. Review this troubleshooting guide

---

## Success Indicators

When deployment is successful, you'll see:

```
==> Build successful 🎉
==> Deploying...
==> Running 'npm start'
Server running at http://0.0.0.0:[PORT]/
Serving DrMansoorPortifolio.html
==> Your service is live 🎉
```

URL will be: `https://dr-mansoor-portfolio.onrender.com`
