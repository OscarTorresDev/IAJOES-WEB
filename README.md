# AI Joes Website

A modern, bilingual website for AI Joes - bringing AI solutions to everyday businesses. Built with Astro, Tailwind CSS, and featuring a markdown-based content management system.

## 🌟 Features

- **Bilingual Support**: Full English and Spanish localization
- **Modern Design**: Clean, professional UI with smooth animations
- **Content Management**: Easy markdown-based blog system
- **Responsive**: Mobile-first design that works on all devices
- **SEO Optimized**: Built-in sitemap and meta tag management
- **Docker Ready**: Production-ready containerization

## 🚀 Quick Start

### Prerequisites

- Node.js 18 or higher
- npm or yarn
- Docker (for containerized deployment)

### Local Development

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the development server:**
   ```bash
   npm run dev
   ```

3. **Open your browser:**
   Navigate to `http://localhost:4321`

## 🐳 Docker Deployment

### Building the Docker Image

1. **Build the Docker image:**
   ```bash
   docker build -t ai-joes-website .
   ```

2. **Run the container:**
   ```bash
   docker run -p 80:80 ai-joes-website
   ```

3. **Access the website:**
   Open `http://localhost` in your browser

### Docker Compose (Optional)

Create a `docker-compose.yml` file for easier management:

```yaml
version: '3.8'
services:
  ai-joes-website:
    build: .
    ports:
      - "80:80"
    restart: unless-stopped
```

Then run:
```bash
docker-compose up -d
```

### Production Deployment

For production deployment, you might want to use a reverse proxy like Nginx or deploy to cloud platforms:

**AWS ECS/Fargate:**
```bash
# Tag for ECR
docker tag ai-joes-website:latest your-account.dkr.ecr.region.amazonaws.com/ai-joes-website:latest

# Push to ECR
docker push your-account.dkr.ecr.region.amazonaws.com/ai-joes-website:latest
```

**Google Cloud Run:**
```bash
# Tag for GCR
docker tag ai-joes-website:latest gcr.io/your-project/ai-joes-website:latest

# Push to GCR
docker push gcr.io/your-project/ai-joes-website:latest
```

## 📝 Content Management

### Adding Blog Posts

Your team can easily add new blog posts without technical knowledge:

1. **Create a new markdown file** in `src/content/blog/`
2. **Use this template:**

```markdown
---
title: 'Your Post Title'
description: 'Brief description of the post'
pubDate: 2024-01-15
heroImage: 'https://images.pexels.com/photos/example.jpg'
tags: ['AI', 'Business', 'Technology']
lang: 'en'  # Use 'es' for Spanish posts
featured: false  # Set to true for featured posts
---

# Your Content Here

Write your blog post using standard markdown formatting:

- **Bold text**
- *Italic text*
- [Links](https://example.com)
- Lists and more!

## Subheadings

Add images, code blocks, and any other markdown content.
```

3. **File naming convention:**
   - English posts: `your-post-title-en.md`
   - Spanish posts: `your-post-title-es.md`

### Supported Languages

- **English** (`en`): Default language, accessible at `/`
- **Spanish** (`es`): Accessible at `/es/`

## 🛠️ Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build locally |
| `npm run astro` | Run Astro CLI commands |

## 📁 Project Structure

```
/
├── public/                 # Static assets
├── src/
│   ├── components/        # Reusable UI components
│   ├── content/          # Markdown content (blogs)
│   ├── i18n/             # Translation files
│   ├── layouts/          # Page layouts
│   ├── pages/            # Route pages
│   ├── styles/           # Global styles
│   └── utils/            # Utility functions
├── Dockerfile            # Docker configuration
├── astro.config.mjs      # Astro configuration
└── tailwind.config.mjs   # Tailwind CSS configuration
```

## 🎨 Customization

### Colors

The website uses a professional color scheme defined in `tailwind.config.mjs`:

- **Primary Blue**: #0066CC (AI Joes brand color)
- **Accent Orange**: #FF6B35 (Call-to-action elements)
- **Neutral Grays**: Various shades for text and backgrounds

### Adding New Languages

1. Add language to `src/i18n/translations.ts`
2. Create new page routes in `src/pages/[lang]/`
3. Update navigation components

### Modifying Content

- **Homepage content**: Edit components in `src/components/`
- **Translations**: Update `src/i18n/translations.ts`
- **Styling**: Modify `src/styles/global.css` and Tailwind classes

## 🔧 Technical Details

- **Framework**: Astro 5.x
- **Styling**: Tailwind CSS 3.x
- **Content**: Markdown with frontmatter
- **Deployment**: Docker with Nginx
- **Node Version**: 18+ (Alpine Linux in container)

## 📞 Support

For technical support or questions about content management, contact the development team.

## 📄 License

This project is proprietary to AI Joes. All rights reserved.