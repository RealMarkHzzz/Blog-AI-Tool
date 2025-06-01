# Project Structure Guidelines

## Directory Organization
/src
  /app                    # Next.js 14 App Router
    /blog                 # Blog-related pages
      /[slug]             # Dynamic blog post pages
      page.tsx            # Blog listing page
    /tools                # AI tools pages (can be static or dynamic)
    /api                  # API routes (only if tools need database)
    layout.tsx            # Root layout
    page.tsx              # Home page

  /components             # React components
    /ui                   # Shadcn/ui components
    /blog                 # Blog-specific components
    /tools                # Tool-specific components
    /layout               # Layout components

  /content                # MDX content (CRITICAL: This is your content source)
    /blog                 # Blog posts as MDX files
      /2024              # Organize by year or category
        post-slug.mdx
    /pages                # Static pages content

  /data                   # Static data files (if tools are static)
    tools.json            # AI tools data
    categories.json       # Tool categories

  /lib                    # Utility functions
    blog.ts               # Blog content processing utilities
    tools.ts              # Tool data processing
    utils.ts              # General utilities
    validations.ts        # Zod schemas (if needed)

  /types                  # TypeScript type definitions

  /hooks                  # Custom React hooks

/public                  # Static assets
  /images
    /blog                 # Blog post images
    /tools                # Tool screenshots/logos

## File Placement Rules - CRITICAL

### Blog Content (ALWAYS file-based)
- **Blog posts**: `/content/blog/[year]/[slug].mdx`
- **Blog components**: `/components/blog/`
- **Blog utilities**: `/lib/blog.ts`
- **Blog types**: `/types/blog.ts`

### AI Tools (Choose one approach)
- **Static approach**:  
  - `/data/tools.json`  
  - `/data/categories.json`
- **Dynamic approach**:  
  - Database + API routes in `/app/api/tools/`

### Content Processing
- **MDX processing**: All blog content processing in `/lib/blog.ts`
- **Static data processing**: Tool data processing in `/lib/tools.ts`
- **Search indexing**: Build-time search index generation

## Naming Conventions

- **MDX files**: kebab-case (e.g., `my-first-post.mdx`)
- **Components**: PascalCase (e.g., `BlogPost.tsx`)
- **Utilities**: camelCase (e.g., `getBlogPosts`)
- **Types**: PascalCase with descriptive suffixes (e.g., `BlogPostMetadata`)