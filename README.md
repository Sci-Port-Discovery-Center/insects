# DrawAnInsect.com - Interactive Insect Drawing

🪲 **[DrawAnInsect.com](https://drawainsect.com)** 🪲

Users have their insect drawings AI-validated in real time and watch their creations crawl or fly in a shared tank. 

[![Insect Drawing](https://img.shields.io/badge/Game-Live-brightgreen)](https://drawainsect.com)
[![AI Powered](https://img.shields.io/badge/AI-ONNX-blue)](https://onnx.ai/)
[![Community](https://img.shields.io/badge/Community-Voting-orange)](#features)

## 🎮 Features

### 🎨 **Interactive Drawing**
- **Real-time AI validation** - Draw insects and get instant feedback from our neural network.
- **Smart canvas** - Intuitive drawing tools with pressure-sensitive input
- **Live classification** - Background color changes as the AI recognizes your insect
- **Drawing hints** - Visual cues help you create better insect drawings

### 🏊 **Community Insect Tank**
- **Shared insectarium** - Watch your insects crawl and fly with creations from artists worldwide
- **Multiple view modes** - See most recent, popular, or random insects
- **Smooth animations** - Insects move with mode-specific animations in the virtual tank
- **Interactive experience** - Click insects to learn about their creators

### 🗳️ **Voting & Rankings**
- **Community voting** - Rate insect drawings from other artists
- **Smart ranking system** - Algorithm balances recency and popularity
- **Artist profiles** - Track your stats and see your insect collection
- **Leaderboards** - Discover the most loved insects in the community

### 🗂️ **Personal Collections**
- **Custom insect tanks** - Create themed collections of your favorite insects
- **Share collections** - Let friends explore your curated tanks
- **Privacy controls** - Make tanks public or keep them private
- **Organize by theme** - Group insects by color, style, or any criteria

## 🧠 How the AI Works

The app uses machine learning for real-time insect recognition:

- **ONNX Runtime Web** - Runs neural network inference entirely in your browser
- **PyTorch-trained model** - Originally developed and trained using PyTorch
- **Instant feedback** - Classification happens with every brush stroke
- **Quality control** - Only validated insects can join the community tank

## 🚀 Getting Started

1. **Visit [DrawAnInsect.com](https://drawainsect.com)**
2. **Start drawing** on the canvas (insect should face right!)
3. **Watch the AI** give feedback through background color changes
4. **Submit your insect** when you're happy with it
5. **See it move** in the community tank with other creations
6. **Vote and explore** other artists' insects in the rankings

## 📱 Cross-Platform Compatible

- **Desktop browsers** - Full experience with mouse/trackpad drawing
- **Tablet friendly** - Touch-optimized for iPad and Android tablets  
- **Mobile responsive** - Works on phones with simplified interface
- **Progressive Web App** - Can be installed like a native app

## 🌟 Community Features

### For Artists
- **Profile system** - Track your insect creations and statistics
- **Personal galleries** - Showcase your best work
- **Achievement tracking** - See your voting scores and community engagement
- **Social sharing** - Share your insects and tanks on social media

### For Viewers  
- **Discovery tools** - Find new artists and trending insects
- **Voting system** - Help surface the best community content
- **Collections** - Save favorites to personal insect tanks
- **Commenting** - Engage with the community (coming soon)

## 🔧 Technical Details

## Project Structure

### HTML Pages (Root Directory)
- `index.html` — Main drawing page and UI
- `tank.html` — Insect tank display with crawling/flying animations
- `rank.html` — Insect ranking and voting system
- `login.html` — Authentication page for moderation
- `moderation.html` — Moderation interface for managing submissions

### Source Files
- `src/js/` — JavaScript files
  - `app.js` — Main drawing, AI, and UI logic
  - `tank.js` — Insect tank animation and display
  - `rank.js` — Ranking system logic
  - `login.js` — Authentication handling
  - `moderation.js` — Moderation tools
  - `fish-utils.js` — Shared utilities and API calls (legacy filename)
  - `firebase-init.js` — Firebase/Firestore initialization
- `src/css/` — Stylesheets
  - `style.css` — Main application styles
  - `moderation.css` — Moderation-specific styles

### Assets
- `assets/` — Static assets (images, models)
- `public/` — Public assets (favicon, etc.)

## Connected Repositories

### [fish-trainer](https://github.com/aldenhallak/fish-trainer)
- Contains the PyTorch code for training the doodle classifier used by this app (legacy repo name).
- Exports the trained model to ONNX format, which is used by DrawAnInsect.com for in-browser inference.
- Includes data augmentation, preprocessing, and model evaluation scripts.

### [fish-be](https://github.com/aldenhallak/fish-be)
- The backend for DrawAnInsect.com, deployed as a serverless function (Cloud Run).
- Handles insect image uploads, processes and stores submissions, and returns the canonical insect image for the tank.
- May also provide endpoints for moderation, stats, or gallery features.

## Setup & Deployment
1. Clone this repository.
2. Place the ONNX model (`fish_doodle_classifier.onnx`) in the `assets/models/` directory.
3. Configure `src/js/firebase-init.js` if using Firestore for real-time features.
4. Deploy the static site (e.g., Vercel, Netlify, Firebase Hosting).
5. Ensure the backend endpoint in `src/js/fish-utils.js` points to the deployed `fish-be` instance.

### Local development server

For offline testing you can run the bundled lightweight Node server that mimics the production REST API:

1. `cd server`
2. `npm install` (installs Express, multer, etc.)
3. `npm run dev:server`

This starts a backend on `http://localhost:8080` that supports uploads, insect listing, voting, reports, and the authentication flows used on the login/reset pages. When you load the frontend from `localhost`, `src/js/fish-utils.js` automatically points `BACKEND_URL` at this local server; you can also override it by setting `window.BACKEND_URL` or a `BACKEND_URL` entry in `localStorage`.

## Credits
- AI model and training: [fish-trainer](https://github.com/aldenhallak/fish-trainer) (legacy name)
- Backend: [fish-be](https://github.com/aldenhallak/fish-be) (legacy name)
- Frontend & UI: This repository

---

This repository was about ~80% AI generated. I used copilot + zencoder. Both tools worked great, but could not be trusted to make decisions on their own :)
