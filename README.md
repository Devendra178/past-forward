

# Past Forward - Your Personal Time Machine

Past Forward is an innovative AI-powered web application that reimagines you through the decades. Using Google's Gemini 2.5 Flash Image model, the application transforms your photos to show how you would have looked in different eras, from the 1950s to the 2000s, complete with period-appropriate clothing, hairstyles, and photo aesthetics.

## 🌟 Features

- **Multi-Decade Transformation**: Generate your images across six different decades (1950s, 1960s, 1970s, 1980s, 1990s, 2000s)
- **AI-Powered Generation**: Utilizes Google's Gemini 2.5 Flash Image model for photorealistic transformations
- **Interactive UI**: Engaging polaroid-style cards with drag-and-drop functionality on desktop
- **Batch Processing**: Concurrent image generation with a controlled concurrency limit
- **Error Handling**: Robust retry mechanism and fallback prompts for failed generations
- **Individual Downloads**: Download any single decade image
- **Album Creation**: Combine all generated images into a single downloadable album
- **Responsive Design**: Optimized for both desktop and mobile devices
- **Smooth Animations**: Framer Motion powered transitions and effects

## 🚀 Technology Stack

- **Frontend Framework**: React 19.1.1
- **Build Tool**: Vite 6.2.0
- **Language**: TypeScript 5.8.2
- **AI Model**: Google Gemini 2.5 Flash Image (@google/genai ^1.14.0)
- **Styling**: Tailwind CSS (via tailwind-merge)
- **Animations**: Framer Motion 12.23.12
- **Additional Libraries**: clsx for conditional classes

## 📋 Prerequisites

Before running this application, ensure you have:

- **Node.js**: Version 18 or higher recommended
- **npm**: Package manager (comes with Node.js)
- **Gemini API Key**: Obtain from [Google AI Studio](https://aistudio.google.com/app/apikey)

## 🛠️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/architxkumar/past-forward.git
cd past-forward
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env.local` file in the root directory:

```bash
GEMINI_API_KEY=your_gemini_api_key_here
```

Replace `your_gemini_api_key_here` with your actual Gemini API key.

### 4. Run the Development Server

```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or another port if 5173 is in use).

## 📦 Available Scripts

- **`npm run dev`**: Starts the development server with hot module replacement
- **`npm run build`**: Creates an optimized production build
- **`npm run preview`**: Previews the production build locally

## 🎯 How to Use

1. **Upload Photo**: Click on the polaroid card to upload your photo (supports PNG, JPEG, WEBP)
2. **Generate**: Click the "Generate" button to start transforming your image across all decades
3. **Wait**: The app processes two decades at a time to optimize API usage
4. **Interact**: 
   - On desktop: Drag polaroid cards around the screen
   - On mobile: Scroll through the results
   - Shake any card to regenerate that specific decade
5. **Download**: 
   - Click individual cards to download single images
   - Use "Download Album" to get all images combined

## 🏗️ Project Structure

```
past-forward/
├── components/
│   ├── Footer.tsx              # Footer component
│   ├── PolaroidCard.tsx        # Polaroid-style image card component
│   └── ui/
│       └── draggable-card.tsx  # Draggable card wrapper
├── services/
│   └── geminiService.ts        # Gemini API integration and image generation
├── lib/
│   ├── albumUtils.ts           # Album creation utilities
│   └── utils.ts                # General utility functions
├── App.tsx                     # Main application component
├── index.tsx                   # Application entry point
├── index.html                  # HTML template
├── vite.config.ts              # Vite configuration
├── tsconfig.json               # TypeScript configuration
└── package.json                # Project dependencies and scripts
```

## 🔧 Key Components

### GeminiService (`services/geminiService.ts`)

Handles all interactions with the Gemini API:
- Image generation with decade-specific prompts
- Retry mechanism for API failures (up to 3 attempts with exponential backoff)
- Fallback prompts if primary prompts are blocked
- Response processing and error handling

### App Component (`App.tsx`)

Main application logic:
- State management for upload, generation, and results
- Concurrent image generation with controlled concurrency (2 at a time)
- Individual image regeneration
- Album download functionality
- Responsive layout switching

### PolaroidCard Component (`components/PolaroidCard.tsx`)

Interactive card component featuring:
- Loading states with spinners
- Error display
- Shake-to-regenerate functionality
- Download button
- Drag-and-drop support (desktop)

## 🔐 Security & Privacy

- API keys are stored in environment variables, never in code
- Images are processed client-side when possible
- No user data is stored on servers
- All image generation happens through secure Gemini API calls

## 🌐 AI Studio Integration

View and deploy this app on AI Studio: https://ai.studio/apps/drive/1Vbs9d7eCcGivYwfx3D0B0eOaDAyVUjeP

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the Apache-2.0 License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Google AI for providing the Gemini API
- The React and Vite communities
- All contributors to the open-source libraries used in this project

## 📞 Support

For issues, questions, or suggestions, please open an issue on the GitHub repository.

---

Made with ❤️ using React, TypeScript, and Google Gemini AI
