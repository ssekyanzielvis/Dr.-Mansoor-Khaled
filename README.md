# Dr. Mansoor Khalid - Portfolio Website

A modern, responsive portfolio website showcasing professional expertise in pharmacy and software engineering.

## 🌟 Features

- **Responsive Design** - Optimized for all devices (mobile, tablet, desktop)
- **Dynamic Content Loading** - Lazy loading images and progressive content reveal
- **Floating Windows/Modals** - Interactive project details and contact information
- **Tailwind CSS** - Modern utility-first CSS framework with PostCSS build process
- **Smooth Animations** - Staggered card animations and scroll reveals
- **SEO Optimized** - Fast loading times and optimized content
- **Mobile-First** - Vertical stacking for small screens

## 🛠️ Technologies Used

- HTML5
- CSS3 (Tailwind CSS v4)
- JavaScript (Vanilla)
- PostCSS
- Autoprefixer
- Node.js (for build process)

## 📦 Installation

1. Clone the repository:
```bash
git clone https://github.com/ssekyanzielvis/Dr.-Mansoor-Khaled.git
cd Dr.-Mansoor-Khaled
```

2. Install dependencies:
```bash
npm install
```

3. Build CSS:
```bash
npm run build
```

4. Open `DrMansoorPortifolio.html` in your browser

## 🔧 Development

### Build CSS once:
```bash
npm run build:css
```

### Watch for CSS changes (development):
```bash
npm run watch:css
```

## 🚀 Deployment to Vercel

### Option 1: Deploy via Vercel Dashboard (Recommended)

1. **Push your code to GitHub** (if not already done)
   ```bash
   git add .
   git commit -m "Prepare for Vercel deployment"
   git push origin main
   ```

2. **Go to [Vercel Dashboard](https://vercel.com/dashboard)**
   - Sign in with GitHub

3. **Import your GitHub repository**
   - Click "Add New" → "Project"
   - Select "Import Git Repository"
   - Choose `Dr.-Mansoor-Khaled` repository

4. **Configure your project**
   - Framework Preset: **Other**
   - Root Directory: `./` (leave as default)
   - Build Command: `npm run build`
   - Output Directory: `.` (current directory)
   - Install Command: `npm install`

5. **Click "Deploy"**
   - Vercel will automatically build and deploy your site
   - You'll get a production URL like: `https://dr-mansoor-khaled.vercel.app`

### Option 2: Deploy via Vercel CLI

1. **Install Vercel CLI**:
```bash
npm install -g vercel
```

2. **Login to Vercel**:
```bash
vercel login
```

3. **Deploy**:
```bash
vercel
```

4. **For production deployment**:
```bash
vercel --prod
```

## 📁 Project Structure

```
Dr.-Mansoor-Khaled/
├── DrMansoorPortifolio.html    # Main HTML file
├── src/
│   └── input.css               # Tailwind CSS source
├── dist/
│   └── output.css             # Compiled CSS (generated)
├── package.json               # Dependencies & scripts
├── tailwind.config.js         # Tailwind configuration
├── postcss.config.js          # PostCSS configuration
├── vercel.json                # Vercel deployment config
├── .gitignore                 # Git ignore rules
└── README.md                  # This file
```

## 🎨 Sections

- **Hero** - Professional introduction
- **About** - Background and expertise
- **Quantum Innovations** - Company information
- **Pharmacy Services** - Healthcare solutions
- **Software Engineering** - Development services
- **Projects** - Featured work portfolio
- **Contact** - Get in touch form

## 🔥 Dynamic Features

- **Lazy Loading Images** - Images load as they enter viewport
- **Progressive Content Loading** - Content reveals on scroll
- **Load More Projects** - Pagination for project cards
- **Floating Action Button** - Quick contact access
- **Modal Windows** - Detailed project information
- **Staggered Animations** - Sequential card reveals
- **Page Loader** - Initial loading screen

## 📱 Mobile Responsive

- All components stack vertically on mobile
- Touch-friendly buttons and navigation
- Optimized for screens 320px and up
- Hamburger menu for mobile navigation

## 🌐 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 📝 License

ISC

## 👤 Author

**Dr. Mansoor Khalid**
- Email: dr.mansoor.khalid@example.com
- GitHub: [@ssekyanzielvis](https://github.com/ssekyanzielvis)
- Company: Quantum Innovations, Inc.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## ⭐ Show your support

Give a ⭐️ if you like this project!
