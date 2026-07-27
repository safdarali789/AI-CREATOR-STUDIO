# 🎨 AI Photo Studio - Object Editor

> An intelligent photo editor powered by **Google Gemini AI** with object replacement, outfit modification, background swapping, and more! Built with **React + TypeScript + Tailwind CSS**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8-blue)
![React](https://img.shields.io/badge/React-19.0-61dafb)

---

## ✨ Features

### 🤖 AI-Powered Editing
- **Object Replacement**: کسی بھی چیز کو دوسری چیز سے بدلیں
- **Outfit Modification**: کپڑے اور accessories تبدیل کریں
- **Background Swap**: پس منظر بدلیں
- **Color Adjustment**: رنگ customize کریں

### 🎯 Professional Tools
- ✂️ **Crop & Rotate**: تصویر کو صحیح کریں
- 🎨 **Filters Gallery**: 20+ پہلے سے تیار filters
- 🔧 **Manual Adjustments**: Brightness, contrast, saturation
- 📜 **History Tracking**: تمام steps track کریں (undo/redo)

### 🌐 Bilingual UI
- 🇺🇸 **English** - مکمل interface
- 🇵🇰 **Urdu** - مکمل Urdu support

### 💾 Cloud Integration
- Save & sync تصاویر
- Share links بنائیں
- Batch operations

---

## 🚀 Quick Start

### Prerequisites
```bash
✓ Node.js 18+
✓ npm or yarn
✓ Google Gemini API key (FREE!)
```

### 1. Clone Repository
```bash
git clone https://github.com/safdarali789/ai-photo-studio.git
cd ai-photo-studio
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Setup Environment
```bash
# Create .env from template
cp .env.example .env

# Add your Gemini API key
# Get free key: https://aistudio.google.com/app/apikey
```

### 4. Start Development
```bash
npm run dev
```

Open **http://localhost:3000** میں اپنا browser کھولیں! 🎉

---

## 📦 Production Build

```bash
# Build for production
npm run build

# Start production server
npm run start
```

---

## 🏗️ Project Structure

```
📁 ai-photo-studio/
├── 📄 README.md                    # یہ فائل
├── 📄 package.json                 # Dependencies
├── 📄 tsconfig.json                # TypeScript config
├── 📄 index.html                   # Entry point
│
├── 📁 src/
│   ├── main.tsx                    # React app start
│   ├── App.tsx                     # Main component
│   ├── types.ts                    # TypeScript interfaces
│   │
│   ├── 📁 components/
│   │   ├── Navbar.tsx              # Top navigation
│   │   ├── CloudSyncModal.tsx      # Cloud sync
│   │   ├── SamplePickerModal.tsx   # Sample images
│   │   │
│   │   ├── 📁 Editor/              # Photo editor
│   │   │   ├── CanvasArea.tsx
│   │   │   ├── AIEditToolbar.tsx
│   │   │   ├── FilterGallery.tsx
│   │   │   ├── ManualAdjustments.tsx
│   │   │   ├── CropRotateModal.tsx
│   │   │   └── HistoryDrawer.tsx
│   │   │
│   │   ├── 📁 Gallery/
│   │   │   └── GalleryView.tsx
│   │   │
│   │   └── 📁 Share/
│   │       └── ShareModal.tsx
│   │
│   ├── 📁 data/
│   │   ├── filterPresets.ts        # Filter definitions
│   │   ├── sampleImages.ts         # Sample photos
│   │   └── urduTranslations.ts     # 🇵🇰 Translations
│   │
│   ├── 📁 utils/
│   │   ├── canvasUtils.ts          # Canvas helpers
│   │   └── cloudSync.ts            # Cloud API calls
│   │
│   └── index.css                   # Tailwind styles
│
├── server.ts                       # Express backend
├── vite.config.ts                  # Build config
├── .env.example                    # Environment template
└── assets/                         # Images & icons
```

---

## 🔒 Security & API Keys

### ✅ Your API Keys Are Safe!

1. **`.env` in `.gitignore`** ← API keys never exposed
2. **Server-side API calls** ← Keys stay on backend
3. **No client-side secrets** ← Frontend never sees keys
4. **`.env.example`** ← Shows template without real keys

### Get Free Gemini API Key
1. Go to: https://aistudio.google.com/app/apikey
2. Click "Create API Key"
3. Copy to your `.env` file
4. No credit card required! 🎉

---

## 📚 API Documentation

### Gemini AI Edit Endpoint
```typescript
POST /api/ai/edit-image

Request:
{
  "imageBase64": "...",
  "prompt": "تصویر میں شام کی روشنی شامل کریں",
  "quality": "high"
}

Response:
{
  "success": true,
  "image": "base64_encoded_result",
  "processingTime": 1234
}
```

### Example Usage
```typescript
// Frontend - Safe! (No API key exposed)
const response = await fetch('/api/ai/edit-image', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    imageBase64: canvas.toDataURL(),
    prompt: userPrompt
  })
});

const result = await response.json();
```

---

## 🎯 Usage Examples

### Replace Object
```
صحافت: "اس تصویر میں قمیض کو نیلی قمیض سے بدل دیں"
→ AI فوری طور پر قمیض تبدیل کر دے گا
```

### Modify Background
```
صحافت: "پس منظر کو ساحل میں تبدیل کریں"
→ یہ خود بخود background بدل دے گا
```

### Filters
```
قدیم تصویر، سیاہ و سفید، سنہری، وغیرہ
```

---

## 🛠️ Development

### Available Scripts

```bash
npm run dev      # Start dev server (localhost:3000)
npm run build    # Build for production
npm run start    # Run production build
npm run lint     # TypeScript check (no emit)
```

### Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React 19 + TypeScript |
| **Styling** | Tailwind CSS |
| **Build Tool** | Vite 6 |
| **Backend** | Express.js + Node.js |
| **AI API** | Google Gemini |
| **UI Components** | Lucide React Icons |
| **Animations** | Motion |

---

## 🚀 Deployment

### Deploy to Vercel (Recommended)
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel
```

### Deploy to GitHub Pages (Static)
```bash
npm run build
# Upload dist/ folder
```

### Deploy to Heroku
```bash
heroku create your-app-name
git push heroku main
```

---

## 🐛 Troubleshooting

### Issue: "API Key Error"
```bash
✓ چیک کریں .env میں GEMINI_API_KEY ہے
✓ API key صحیح ہے
✓ npm run dev دوبارہ شروع کریں
```

### Issue: "Canvas is Not Defined"
```bash
✓ یقینی بنائیں browser modern ہے (Chrome/Firefox)
✓ HTML5 Canvas support چیک کریں
```

### Issue: "Build Fails"
```bash
# Cache صاف کریں
rm -rf node_modules dist
npm install
npm run build
```

---

## 📋 Requirements & Compatibility

| Feature | Browser | Status |
|---------|---------|--------|
| Canvas API | Chrome/Firefox/Safari | ✅ |
| File Upload | All modern | ✅ |
| Gemini API | Server-side | ✅ |
| Mobile UI | Responsive | ✅ |
| Urdu Text | All browsers | ✅ |

---

## 🤝 Contributing

ہمارے project میں شامل ہوں! 💪

```bash
# Fork & Clone
git clone https://github.com/YOUR_USERNAME/ai-photo-studio.git

# نیا branch بنائیں
git checkout -b feature/amazing-feature

# Commit کریں
git commit -am 'Add amazing feature'

# Push کریں
git push origin feature/amazing-feature

# Pull Request کھولیں
```

📖 **مکمل Contributing Guide**: [CONTRIBUTING.md](./CONTRIBUTING.md)

---

## 📄 License

MIT License - آزادانہ استعمال کریں! 🎉

See [LICENSE](LICENSE) for details.

---

## 👨‍💻 Author

**Safdar Ali**
- GitHub: [@safdarali789](https://github.com/safdarali789)
- Brand: AI Naqshify Studio

---

## 🌟 Show Your Support

اگر یہ tool آپ کو پسند ہے تو:
- ⭐ Star دیں
- 🍴 Fork کریں  
- 💬 Feedback دیں
- 🔄 Share کریں

---

## 📞 Support & Questions

- **GitHub Issues**: [Create an issue](../../issues/new)
- **Discussions**: [Ask a question](../../discussions/new)
- **Twitter**: [@safdarali789](https://twitter.com/safdarali789)

---

## 🎯 Roadmap

- [ ] Batch image processing
- [ ] Custom AI models
- [ ] More filters & presets
- [ ] Mobile app (React Native)
- [ ] Plugin system
- [ ] Multi-language support (+Punjabi, Pashto)

---

## 🙏 Acknowledgments

- Google Gemini API
- React & TypeScript Community
- Open source contributors

---

**Made with ❤️ by Safdar Ali** | AI Naqshify Studio

```
٪ ہر خواب کو حقیقت بنایا جا سکتا ہے ٪
Every dream can be turned into reality
```
