# Project Structure

## Directory Layout

```
multi-device-preview/
│
├── README.md                 # Project documentation
├── LICENSE                   # MIT License
├── .gitignore               # Git ignore rules
├── package.json             # Project dependencies and scripts
├── tsconfig.json            # TypeScript configuration
├── next.config.js           # Next.js configuration
├── tailwind.config.js       # Tailwind CSS configuration
├── postcss.config.js        # PostCSS configuration
│
├── src/
│   ├── components/          # Reusable React components
│   │   ├── PreviewPanel/    # Individual preview panel component
│   │   ├── DeviceSelector/  # Device type selector
│   │   ├── URLInput/        # URL input component
│   │   └── ControlBar/      # Control bar component
│   │
│   ├── pages/               # Next.js pages
│   │   ├── index.tsx        # Main preview page
│   │   ├── _app.tsx         # App wrapper
│   │   └── _document.tsx    # Document wrapper
│   │
│   ├── hooks/               # Custom React hooks
│   │   └── usePreviewPanel.ts
│   │
│   ├── utils/               # Utility functions
│   │   └── deviceSizes.ts
│   │
│   ├── types/               # TypeScript type definitions
│   │   └── index.ts
│   │
│   └── styles/              # Global styles
│       └── globals.css
│
├── public/                  # Static assets
│   ├── images/              # Images and icons
│   └── favicon.ico          # Favicon
│
└── docs/                    # Documentation
    ├── CONTRIBUTING.md      # Contributing guidelines
    ├── SETUP.md            # Setup instructions
    └── API.md              # API documentation
```

## Getting Started

1. Install dependencies: `npm install`
2. Run development server: `npm run dev`
3. Open http://localhost:3000 in your browser

## Development

- **Build**: `npm run build`
- **Start**: `npm start`
- **Lint**: `npm run lint`
