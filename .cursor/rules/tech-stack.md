# Technology Stack Configuration

## Core Framework
- **Next.js 14**: App Router with TypeScript and Static Generation
- **React 18**: Functional components with hooks
- **TypeScript**: Strict mode enabled

## Content Management (Static)
- **MDX**: For blog posts with React component support
- **Gray Matter**: Frontmatter parsing from MDX files
- **Reading Time**: Automatic reading time calculation
- **Remark/Rehype**: Markdown processing plugins

## Styling & UI
- **Tailwind CSS**: Utility-first CSS framework
- **Shadcn/ui**: Component library built on Radix UI
- **Lucide React**: Icon library
- **Class Variance Authority**: Component variant handling

## File System Structure
- **Content Storage**: Local `/content` directory
- **Static Generation**: Build-time content processing
- **Image Optimization**: Next.js Image with static imports

## Search & Utilities (Client-side)
- **Fuse.js**: Client-side fuzzy search for blog posts
- **Date-fns**: Date manipulation library
- **Clsx**: Conditional className utility

## Optional Dynamic Features (if needed for tools)
- **Supabase**: Only for AI tools database and user interactions
- **Row Level Security**: If user features are needed

## Development Tools
- **ESLint**: Code linting with Next.js config
- **Prettier**: Code formatting
- **TypeScript**: Type checking

## Key Usage Rules
- **Blog Content**: ALWAYS use MDX files in `/content/blog/`
- **Static Data**: Use JSON/YAML files for tool data if going fully static
- **Search**: Implement client-side search for blog posts
- **Images**: Store in `/public/images/` and use Next.js Image optimization
- **Never use database for blog content** - always file system