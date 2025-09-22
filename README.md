# 🎵 Music Dashboard with AI-Powered Features

A modern, responsive music distribution dashboard built with Next.js, featuring AI-generated descriptions and smart genre suggestions using local LLMs.

## 🚀 Features

### ✅ Core Features
- **Track Management**: Upload, view, edit, and delete music tracks
- **Dashboard Overview**: Cards showing total tracks, recent uploads, and analytics
- **Responsive Design**: Mobile-first with hamburger menu and adaptive layouts
- **Dark/Light Theme**: Toggle between themes with persistence
- **Authentication**: Session-based login system
- **Data Visualization**: Overview cards and status badges

### 🤖 AI-Powered Features
- **AI Description Generation**: Generate creative track descriptions using Phi-1.5 LLM
- **Smart Genre Suggestions**: AI suggests music genres based on title and artist
- **Local LLM Integration**: Python Flask backend with Hugging Face Transformers
- **Fallback System**: Random templates if AI model fails

### 🎨 UI/UX
- **Modern Design**: Clean interface with CSS variables and animations
- **Toast Notifications**: Real-time feedback for actions
- **Loading States**: Spinners and disabled states during async operations
- **Accessibility**: Semantic HTML, focus states, and ARIA support
- **Touch-Friendly**: Large buttons and touch targets for mobile

## 🛠 Tech Stack

### Frontend
- **Next.js 15** (Pages Router)
- **React 18** with Hooks
- **CSS Modules** with custom properties
- **Local Storage** for theme persistence

### Backend
- **Next.js API Routes** for CRUD operations
- **Python Flask** for AI services
- **Hugging Face Transformers** for LLM inference

### AI/ML
- **Phi-1.5 Model** (1.3B parameters, efficient)
- **Text Generation Pipeline** for descriptions and suggestions
- **Fallback Templates** for reliability

## 📁 Project Structure

```
music-dashboard/
├── components/
│   ├── Layout.js          # Main layout with navigation
│   ├── StatusBadge.js     # Track status indicators
│   └── Toast.js           # Notification system
├── lib/
│   └── data.js            # In-memory data store
├── pages/
│   ├── api/               # API routes
│   │   ├── tracks/        # CRUD for tracks
│   │   ├── generate-description.js  # AI description API
│   │   └── suggest-genre.js        # AI genre suggestion API
│   ├── _app.js            # App wrapper
│   ├── dashboard.js       # Main dashboard
│   ├── login.js           # Authentication
│   ├── track/[id].js      # Track details
│   └── upload.js          # Upload form with AI
├── public/                # Static assets
├── styles/
│   └── globals.css        # Global styles with themes
└── README.md
```

## 🏗 Approach & Architecture

### 🎯 Problem Solving
- **Scalable Architecture**: Separated concerns (UI, API, AI)
- **Performance**: Memoization, debouncing, and efficient rendering
- **Error Handling**: Comprehensive try/catch with user feedback
- **Security**: Input validation and CORS configuration

### 🤖 AI Integration Strategy
- **Local Inference**: No API costs, privacy-focused
- **Model Selection**: Phi-1.5 for balance of performance and size
- **Fallback Design**: Multiple layers of reliability
- **User Experience**: Seamless AI suggestions without disruption

### 📱 Responsive Design
- **Mobile-First**: Designed for touch devices
- **Progressive Enhancement**: Core functionality works everywhere
- **Accessibility**: WCAG-compliant with keyboard navigation

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- Python 3.8+ with pip
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/music-dashboard.git
   cd music-dashboard
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up AI Backend** (see separate repo: music-llm-backend)
   ```bash
   # In another terminal
   git clone https://github.com/yourusername/music-llm-backend.git
   cd music-llm-backend
   pip install -r requirements.txt
   python app.py
   ```

4. **Environment Variables**
   Create `.env.local`:
   ```
   BACKEND_URL=http://localhost:5000
   ```

5. **Run the development server**
   ```bash
   npm run dev
   ```

6. **Open** [http://localhost:3000](http://localhost:3000)

## 📱 Usage

### Basic Workflow
1. **Login**: Use any email/password (demo authentication)
2. **Dashboard**: View track overview and recent activity
3. **Upload**: Add new tracks with AI assistance
   - Enter title/artist
   - Click "🎯 AI Suggest" for genre
   - Click "🤖 Generate AI Description" for text
4. **Manage**: Edit, view, or delete tracks

### AI Features
- **Description Generation**: Creates creative blurbs for marketing
- **Genre Suggestions**: Intelligent categorization based on metadata

## 🔧 API Reference

### Tracks API
- `GET /api/tracks` - List all tracks
- `POST /api/tracks` - Create new track
- `GET /api/tracks/[id]` - Get track by ID
- `PUT /api/tracks/[id]` - Update track
- `DELETE /api/tracks/[id]` - Delete track

### AI APIs
- `POST /api/generate-description` - Generate AI description
- `POST /api/suggest-genre` - Suggest genres

## 🎨 Customization

### Themes
Modify `styles/globals.css` for custom colors:
```css
:root {
  --primary: #your-color;
  --bg: #your-bg;
  /* ... */
}
```

### AI Models
Update `music-llm-backend/app.py` to use different models:
```python
generator = pipeline('text-generation', model='your-model')
```

## 📈 Performance

### Frontend
- **Bundle Size**: Optimized with Next.js
- **Rendering**: Client-side with SSR support
- **Caching**: Local storage for user preferences

### AI Backend
- **Model Size**: Phi-1.5 (~2.5GB download)
- **Inference Speed**: ~1-2 seconds per generation
- **Memory Usage**: ~4GB RAM during operation

## 🧪 Testing

### Manual Testing
- Upload tracks with/without AI features
- Test responsiveness on different devices
- Verify theme switching and persistence

### API Testing
```bash
# Test description generation
curl -X POST http://localhost:3000/api/generate-description \
  -H "Content-Type: application/json" \
  -d '{"track_title": "Midnight Dreams"}'
```

## 🚢 Deployment

### Frontend (Vercel)
1. Connect GitHub repo
2. Add `BACKEND_URL` environment variable
3. Deploy automatically

### Backend (Render)
1. Connect GitHub repo
2. Set build/start commands
3. Deploy with free tier

See `DEPLOY_README.md` for detailed instructions.

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **Next.js** for the amazing framework
- **Hugging Face** for Transformers library
- **Phi-1.5** model by Microsoft
- **Open source community** for inspiration

---

**Built with ❤️ for music creators everywhere**
