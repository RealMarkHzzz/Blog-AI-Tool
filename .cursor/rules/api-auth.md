# API and Authentication Guidelines

## Authentication Pattern
All protected API routes must follow this pattern:

```typescript
import { createServerComponentClient } from '@supabase/auth-helpers-nextjs'
import { cookies } from 'next/headers'
import { NextRequest, NextResponse } from 'next/server'

export async function GET(request: NextRequest) {
  const supabase = createServerComponentClient({ cookies })
  
  // Check authentication
  const { data: { session } } = await supabase.auth.getSession()
  if (!session) {
    return NextResponse.json({ error: 'Unauthorized' }, { status: 401 })
  }

  // Your API logic here
}
```

## Database Operations
Always use Row Level Security enabled operations:

```typescript
// Good: Automatically respects RLS
const { data, error } = await supabase
  .from('posts')
  .select('*')
  .eq('user_id', session.user.id)

// Bad: Direct database access without RLS

```

## Error Handling Pattern

```typescript
try {
  const { data, error } = await supabase
    .from('table_name')
    .operation()
  
  if (error) throw error
  
  return NextResponse.json({ data })
} catch (error) {
  console.error('Operation failed:', error)
  return NextResponse.json(
    { error: 'Internal server error' }, 
    { status: 500 }
  )
}
```

## Validation
Use Zod for all input validation:

```typescript
import { z } from 'zod'

const CreatePostSchema = z.object({
  title: z.string().min(1).max(200),
  content: z.string().min(1),
  published: z.boolean().default(false)
})

// In API route
const validatedData = CreatePostSchema.parse(await request.json())
```

## API Response Format
Standardize all API responses:

```typescript
// Success response
return NextResponse.json({
  success: true,
  data: result,
  message: 'Operation completed successfully'
})

// Error response
return NextResponse.json({
  success: false,
  error: 'Detailed error message',
  code: 'ERROR_CODE'
}, { status: 400 })
```