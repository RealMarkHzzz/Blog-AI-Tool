# Component Development Guidelines

## Component Structure Template

```typescript
'use client' // Only if client-side interactivity needed

import { cn } from '@/lib/utils'
import { forwardRef } from 'react'

interface ComponentProps {
  // Define props with TypeScript
  className?: string
  children?: React.ReactNode
}

/**
 * Brief description of the component's purpose
 * @param className - Additional CSS classes
 * @param children - Child elements
 */
export const Component = forwardRef<HTMLDivElement, ComponentProps>(
  ({ className, children, ...props }, ref) => {
    return (
      <div
        ref={ref}
        className={cn(
          "base-styles", // Default Tailwind classes
          className
        )}
        {...props}
      >
        {children}
      </div>
    )
  }
)

Component.displayName = "Component"
```

## Styling Guidelines
Use Tailwind CSS utility classes

Use cn() helper for conditional classes

Follow mobile-first responsive design

Use CSS variables for theme colors

## State Management
Use useState for local component state

Use custom hooks for reusable logic

Keep state as close to where it's used as possible

Use Zustand for global state if needed

## Performance Optimizations
Use React.memo() for expensive re-renders

Implement useMemo() for expensive calculations

Use dynamic imports for large components

Optimize images with Next.js Image component

## Accessibility
Always include proper ARIA labels

Ensure keyboard navigation works

Use semantic HTML elements

Test with screen readers

Maintain proper color contrast ratios