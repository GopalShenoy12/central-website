# Central Website - Dark Theme

A modern website with dark theme featuring various developer tools.

## Features

- 🌙 **Dark Theme**: Modern dark color scheme with excellent contrast
- 🛠️ **Developer Tools**: 
  - UUID Generator
  - Word & Character Counter
  - JSON Formatter
- 📱 **Responsive Design**: Works on all devices
- ⚡ **Fast Loading**: Optimized assets and caching

## Pages

- **Home** (`index.html`): Main landing page with tool cards
- **UUID Generator** (`tools/uuid.html`): Generate UUIDs with encoding options
- **Word Counter** (`tools/wcc.html`): Count words, characters, and search text
- **JSON Formatter** (`tools/jsonFormatter.html`): Format and beautify JSON
- **Article** (`pages/article.html`): Sample article page

## Hosting Options

### Option 1: GitHub Pages (Recommended)

1. **Enable GitHub Pages**:
   - Go to your repository settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Choose `main` branch and `/` folder
   - Save

2. **Your site will be live at**:
   `https://gopalshenoy12.github.io/central-website`

### Option 2: Vercel

1. **Deploy to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Import your GitHub repository
   - Deploy automatically

### Option 3: Any Static Hosting

Since this is a static website, you can host it on any platform:
- **Firebase Hosting**
- **AWS S3 + CloudFront**
- **Cloudflare Pages**
- **Surge.sh**
- **Any web server**

## Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/GopalShenoy12/central-website.git
   cd central-website
   ```

2. **Open in browser**:
   - Simply open `index.html` in your browser
   - Or use a local server:
   ```bash
   python -m http.server 8000
   # Then visit http://localhost:8000
   ```

## Customization

### Colors
The dark theme uses these color variables:
- Background: `#1a1a2e` to `#16213e`
- Cards: `#2a2a3e` to `#1e3a5f`
- Text: `#e8e8e8`
- Accent: `#64b5f6`, `#4fc3f7`

### Adding New Tools
1. Create a new HTML file in the `tools/` directory
2. Include `../assets/css/common.css`
3. Use the dark theme color scheme
4. Add navigation link to `index.html`

## File Structure

```
central-website/
├── index.html                    # Home page
├── assets/
│   ├── css/
│   │   └── common.css            # Shared styles
│   ├── images/
│   │   └── logo.png              # Logo image
│   └── favicon.ico               # Favicon
├── tools/
│   ├── uuid.html                 # UUID Generator
│   ├── wcc.html                  # Word Counter
│   └── jsonFormatter.html        # JSON Formatter
├── pages/
│   └── article.html              # Article page
└── README.md                     # This file
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is open source and available under the MIT License. 