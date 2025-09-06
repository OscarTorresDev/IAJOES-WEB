# AI Joes Website - Multilingual Edition

A modern, flexible website for AI Joes built with Next.js 14, featuring easy content management through Markdown files and full Spanish language support for Latin American customers.

## 🌍 Features

- 🚀 **Modern Stack**: Next.js 14 with TypeScript and Tailwind CSS
- 📝 **Easy Content Management**: Add/edit content without touching code
- 🌐 **Multilingual Support**: English and Spanish with automatic language detection
- 📱 **Responsive Design**: Optimized for all devices
- ⚡ **Fast Performance**: Optimized builds and static generation
- 🐳 **Docker Ready**: Easy deployment with Docker
- 🔒 **SEO Optimized**: Built-in meta tags and structured data for both languages

## 🌐 Language Support

- 🇺🇸 **English** - Primary language
- 🇪🇸 **Spanish** - For Latin American customers

**URL Structure:**
- English: `/en/about`, `/en/services`, `/en/blog`
- Spanish: `/es/about`, `/es/services`, `/es/blog`

## Quick Start

### Local Development

1. **Clone and install dependencies:**
```bash
git clone <repository-url>
cd ai-joes-website
npm install
```

2. **Run the development server:**
```bash
npm run dev
```

3. **Open http://localhost:3000** in your browser

### Content Management

Content is managed through Markdown files organized by language:

```
content/
├── en/          # English content
│   ├── pages/   # Static pages
│   └── blog/    # Blog posts
└── es/          # Spanish content
    ├── pages/   # Páginas estáticas
    └── blog/    # Publicaciones del blog
```

See `content/MULTILINGUAL-GUIDE.md` for detailed multilingual content management instructions.

## 🌍 Multilingual Content Workflow

### Adding English Content
1. Create files in `content/en/pages/` or `content/en/blog/`
2. Use standard markdown format with front matter

### Adding Spanish Content
1. Create corresponding files in `content/es/pages/` or `content/es/blog/`
2. Translate content while maintaining the same structure
3. Use appropriate Spanish terminology and cultural context

### Example Structure:
```
content/en/pages/services.md    # English services page
content/es/pages/services.md    # Spanish services page (servicios)
```

## Docker Deployment

### Simple Docker Build

```bash
# Build the image
docker build -t ai-joes-website .

# Run the container
docker run -p 3000:3000 ai-joes-website
```

### Docker Compose (Recommended)

```bash
# Development
docker-compose up -d

# Production with nginx
docker-compose --profile production up -d
```

### Environment Variables

Create a `.env.local` file for environment-specific settings:

```env
# Optional analytics
NEXT_PUBLIC_GA_ID=your-google-analytics-id

# Contact form (if using external service)
CONTACT_FORM_ENDPOINT=your-contact-form-endpoint

# Default locale (optional - defaults to 'en')
DEFAULT_LOCALE=en
```

## Project Structure

```
ai-joes-website/
├── app/                          # Next.js app directory
│   ├── [locale]/                # Locale-specific pages
│   │   ├── page.tsx            # Home page
│   │   ├── [slug]/             # Dynamic pages
│   │   └── blog/               # Blog section
│   ├── components/             # Reusable components
│   │   ├── Header.tsx          # Navigation with language switcher
│   │   ├── Footer.tsx          # Localized footer
│   │   └── LanguageSwitcher.tsx # Language toggle component
│   └── globals.css             # Global styles
├── content/                    # Content management
│   ├── en/                    # English content
│   │   ├── pages/             # Static pages
│   │   └── blog/              # Blog posts
│   ├── es/                    # Spanish content
│   │   ├── pages/             # Páginas estáticas
│   │   └── blog/              # Publicaciones del blog
│   └── MULTILINGUAL-GUIDE.md  # Multilingual content guide
├── messages/                  # Translation files
│   ├── en.json               # English UI translations
│   └── es.json               # Spanish UI translations
├── lib/                      # Utilities
│   └── contentManager.ts     # Multilingual content processing
├── middleware.ts             # Language detection middleware
├── i18n.ts                  # Internationalization config
├── Dockerfile               # Docker configuration
├── docker-compose.yml       # Docker Compose setup
└── package.json            # Dependencies
```

## 🌐 Language Features

### Automatic Language Detection
- Detects user's browser language preference
- Falls back to English if Spanish content unavailable
- Remembers user's language choice

### Language Switcher
- Globe icon with current language flag
- Easy switching between English/Spanish
- Maintains current page context when switching

### Content Fallback
- Spanish content falls back to English if translation missing
- Ensures no broken pages due to missing translations

## Content Management Examples

### English Page (`content/en/pages/services.md`):
```markdown
---
title: "Our Services"
description: "AI solutions for modern business"
---

# Our Services
We offer comprehensive AI solutions...
```

### Spanish Page (`content/es/pages/services.md`):
```markdown
---
title: "Nuestros Servicios"
description: "Soluciones de IA para negocios modernos"
---

# Nuestros Servicios
Ofrecemos soluciones integrales de IA...
```

## Production Deployment

### Option 1: Simple Docker Deploy
```bash
# Build for production
docker build -t ai-joes-website .

# Run with restart policy
docker run -d --name ai-joes \
  --restart unless-stopped \
  -p 3000:3000 \
  ai-joes-website
```

### Option 2: Cloud Deployment
The application works with any Docker-compatible hosting:

- **Vercel**: Automatic deployment with Next.js optimization
- **AWS**: ECS, Elastic Beanstalk with multilingual support
- **Google Cloud**: Cloud Run with international routing
- **Azure**: Container Instances with global distribution
- **DigitalOcean**: App Platform with multi-region deployment

## SEO & International Features

- **Multilingual URLs**: `/en/about` vs `/es/about`
- **Language-specific meta tags**: Optimized for each language
- **Hreflang tags**: Automatic alternate language indicators
- **Sitemap generation**: Separate entries for each language
- **Cultural localization**: Date formats, number formats, etc.

## Maintenance

### Content Updates
- Edit files in `content/en/` or `content/es/` directories
- Both languages can be updated independently
- Changes reflect immediately after deployment

### Adding New Languages
1. Add locale to `middleware.ts`
2. Create translation files in `messages/`
3. Add content directory structure in `content/`
4. Update language switcher component

### Translation Workflow
1. Create English content first
2. Translate to Spanish (or hire professional translators)
3. Place translated content in `content/es/`
4. Test both language versions

## Performance Features

- ⚡ Static page generation for both languages
- 🖼️ Automatic image optimization
- 📦 Bundle optimization with tree shaking
- 🔄 Incremental static regeneration
- 🌐 CDN-ready for global distribution
- 📱 Mobile-first responsive design

## Support

For technical support:
1. Check the logs: `docker logs <container-name>`
2. Verify content format in `content/MULTILINGUAL-GUIDE.md`
3. Test locally with `npm run dev`
4. Check language-specific content paths

## License

Private - AI Joes Internal Use

---

¡Ahora tu sitio web está listo para servir a clientes en inglés y español! 🎉
