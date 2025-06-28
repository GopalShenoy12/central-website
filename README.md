# Central Website - Dark Theme

A modern website with dark theme featuring various developer tools and a content management system.

## Features

- 🌙 **Dark Theme**: Modern dark color scheme with excellent contrast
- 🛠️ **Developer Tools**: 
  - UUID Generator
  - Word & Character Counter
  - JSON Formatter
- 📝 **Content Management**: Netlify CMS integration
- 📱 **Responsive Design**: Works on all devices
- ⚡ **Fast Loading**: Optimized assets and caching

## Pages

- **Home** (`index.html`): Main landing page with tool cards
- **Blog** (`blog.html`): Blog posts from CMS
- **UUID Generator** (`uuid.html`): Generate UUIDs with encoding options
- **Word Counter** (`wcc.html`): Count words, characters, and search text
- **JSON Formatter** (`jsonFormatter.html`): Format and beautify JSON
- **Admin** (`admin/`): Content management interface

## Hosting Options

### Option 1: Netlify (Recommended)

1. **Connect to GitHub**:
   - Go to [netlify.com](https://netlify.com)
   - Sign up/login with your GitHub account
   - Click "New site from Git"
   - Select your repository: `Anushenoy08/central-website`

2. **Configure Build Settings**:
   - Build command: (leave empty)
   - Publish directory: `.` (root directory)

3. **Deploy**:
   - Click "Deploy site"
   - Your site will be live at `https://your-site-name.netlify.app`

4. **Setup CMS**:
   - Go to `https://your-site-name.netlify.app/admin`
   - Authorize with GitHub
   - Start creating blog posts!

### Option 2: GitHub Pages

1. **Enable GitHub Pages**:
   - Go to your repository settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Choose `main` branch and `/` folder
   - Save

2. **Your site will be live at**:
   `https://anushenoy08.github.io/central-website`

### Option 3: Vercel

1. **Deploy to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Import your GitHub repository
   - Deploy automatically

## CMS Setup

The website uses **Netlify CMS** for content management:

### Accessing the CMS
- Navigate to `/admin` on your deployed site
- Authorize with GitHub
- Start creating and editing content

### Content Structure
- **Blog Posts**: Stored in `/posts` directory
- **Images**: Uploaded to `/images/uploads`
- **Configuration**: `admin/config.yml`

### Creating Blog Posts
1. Go to `/admin`
2. Click "New Blog"
3. Fill in:
   - Title
   - Date
   - Body (Markdown supported)
4. Click "Publish"

## Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Anushenoy08/central-website.git
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
1. Create a new HTML file
2. Include `common.css`
3. Use the dark theme color scheme
4. Add navigation link

## File Structure

```
central-website/
├── index.html              # Home page
├── blog.html               # Blog page
├── uuid.html               # UUID Generator
├── wcc.html                # Word Counter
├── jsonFormatter.html      # JSON Formatter
├── article.html            # Article page
├── common.css              # Shared styles
├── admin/
│   ├── index.html          # CMS interface
│   └── config.yml          # CMS configuration
├── posts/                  # Blog posts (CMS)
├── images/                 # Images and uploads
├── netlify.toml           # Netlify configuration
└── README.md              # This file
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is open source and available under the MIT License. 