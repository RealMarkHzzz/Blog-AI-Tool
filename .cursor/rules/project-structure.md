# Project Structure Guidelines

## Directory Organization
/src
│
├── /app                    # Next.js 14 App Router
│   ├── /(routes)          # Route groups
│   ├── /blog              # Blog-related pages
│   ├── /tools             # AI tools pages
│   ├── /api               # API routes
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
│
├── /components            # Reusable React components
│
├── /ui                    # Shadcn/ui components
│
├── /blog                  # Blog-specific components
│
├── /tools                 # Tool-specific components
│
├── /layout                # Layout components (e.g., Header, Footer)
│
├── /content               # MDX blog posts and content
│
├── /lib                   # Utility functions and app configurations
│   ├── supabase.ts        # Supabase client setup
│   ├── utils.ts           # General utility functions
│   ├── validations.ts     # Zod schema validations
│
├── /types                 # TypeScript type definitions
│
└── /hooks                 # Custom React hooks

## File Placement Rules

### Components
- **Reusable UI components**: `/components/ui/`
- **Blog components**: `/components/blog/`
- **Tool components**: `/components/tools/`
- **Layout components**: `/components/layout/`
- **Page-specific components**: Create in `/components/[feature]/`

### API Routes
- **Blog APIs**: `/app/api/blog/`
- **Tools APIs**: `/app/api/tools/`
- **Authentication**: `/app/api/auth/`

### Content
- **Blog posts**: `/content/blog/[slug].mdx`
- **Static pages**: `/content/pages/[slug].mdx`

### Utilities
- **Database functions**: `/lib/database/`
- **Validation schemas**: `/lib/validations/`
- **Type definitions**: `/types/`
- **Custom hooks**: `/hooks/`

## Naming Conventions
- **Components**: PascalCase (e.g., `BlogPost.tsx`)
- **Files**: kebab-case (e.g., `blog-post.tsx`)
- **Directories**: kebab-case (e.g., `blog-posts/`)
- **API routes**: kebab-case (e.g., `api/blog-posts/`)
- **Types**: PascalCase with descriptive suffixes (e.g., `BlogPostType`, `UserData`)