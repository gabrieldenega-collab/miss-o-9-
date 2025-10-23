# Design Guidelines: Password Validator Microservice Interface

## Design Approach: Functional Developer Tool
**Selected System**: Material Design with Stripe's clarity and Linear's typography precision

This is a utility-focused developer tool prioritizing clear visual feedback, readability, and professional aesthetics. The interface should feel like a polished testing console that developers would trust.

---

## Core Design Elements

### A. Color Palette

**Dark Mode (Primary)**
- Background Base: 222 25% 8% (deep charcoal)
- Surface: 222 20% 12% (elevated surface)
- Surface Elevated: 222 18% 16% (cards/inputs)
- Border: 222 15% 24% (subtle divisions)

**Status Colors**
- Success: 142 76% 45% (vibrant green)
- Error: 0 84% 60% (clear red)
- Warning: 38 92% 50% (amber/yellow)
- Info: 217 91% 60% (bright blue)

**Text**
- Primary: 0 0% 95% (high contrast white)
- Secondary: 0 0% 70% (muted gray)
- Tertiary: 0 0% 50% (subtle gray)

**Interactive**
- Primary Button: 217 91% 60% (blue)
- Primary Button Hover: 217 91% 55%
- Focus Ring: 217 91% 60% with 40% opacity

### B. Typography

**Font Stack**
- Primary: Inter (Google Fonts) - clean, technical
- Monospace: 'Fira Code' (Google Fonts) - for password display, code snippets

**Hierarchy**
- Hero Title: text-5xl font-bold tracking-tight
- Section Headers: text-3xl font-semibold
- Subsection Headers: text-xl font-medium
- Body: text-base font-normal leading-relaxed
- Small Text/Labels: text-sm font-medium
- Error Messages: text-sm font-medium
- Code/Input: text-base font-mono

### C. Layout System

**Spacing Units**: Tailwind 4, 6, 8, 12, 16, 24
- Component padding: p-6 to p-8
- Section spacing: space-y-6 to space-y-8
- Card gaps: gap-6
- Form element spacing: space-y-4

**Container Strategy**
- Max width: max-w-2xl (optimal for form-focused interface)
- Centered: mx-auto
- Viewport padding: px-6 on mobile, px-8 on desktop
- Vertical centering: min-h-screen with flex centering

---

## Component Library

### Navigation Header
Simple centered header with logo/title and GitHub link
- Subtle border-bottom with border color
- Padding: py-4
- Sticky positioning for single-page app

### Hero Section (Compact)
Centered content block introducing the validator
- Title with gradient text effect (blue to cyan)
- Brief description: 2-3 sentences explaining the API
- Compact height: py-12 to py-16 (not full viewport)
- Badge showing "API Status: Active" with green dot indicator

### Password Testing Card
Primary interface component - large, prominent card
- Background: Surface Elevated color
- Border: 1px subtle border
- Rounded corners: rounded-xl
- Shadow: soft elevation shadow
- Padding: p-8

**Input Section**
- Label: "Enter Password to Validate"
- Input field: Full-width, rounded-lg, monospace font
- Height: h-14 for comfortable interaction
- Focus state: blue ring with 2px width
- Background: slightly lighter than card background
- Clear icon button inside input (right side)

**Validation Rules Display**
Checklist showing all validation criteria before submission
- Icon + text for each rule
- Grayed out initially
- Updates to green checkmark (success) or red X (fail) after validation
- Rules: Minimum 8 characters, Uppercase letter, Number, Special character
- Spacing: space-y-3

**Submit Button**
- Full width
- Height: h-12
- Rounded: rounded-lg
- Primary blue background
- Text: "Validate Password" with loading spinner state
- Disabled state when input is empty

### Results Display Section
Appears dynamically after validation
- Success state: Green border-l-4 with success background tint
- Error state: Red border-l-4 with error background tint
- Padding: p-6
- Rounded: rounded-lg
- Margin-top: mt-6

**Success Message**
- Large green checkmark icon
- "Password is Valid!" headline (text-xl font-semibold)
- Subtext: "Meets all security requirements"

**Error Message**
- Red alert icon
- "Password Invalid" headline
- List of specific errors with bullet points
- Each error in red text with small warning icons

### Technical Details Section
Below the main card - expandable details
- Shows JSON request/response in formatted code blocks
- Dark code block background with syntax highlighting colors
- Copy to clipboard button
- Demonstrates API structure for developers

### Footer
Minimal footer with links to:
- GitHub repository
- Creator attribution
- API documentation toggle

---

## Visual Feedback & Interactions

**Real-time Validation Indicators**
- Each validation rule updates icon as user types
- Subtle green/red color transitions (not jarring)
- Smooth opacity transitions (duration-200)

**Loading States**
- Submit button shows spinner during API call
- Results section fades in smoothly

**Animations**: Minimal, purposeful only
- Checkmark/X icon scale-in animation on validation
- Results section slide-down entrance (translate-y-2 to 0)
- Focus ring smooth transition

---

## Layout Structure

**Single-Page Centered Layout**
```
- Header (fixed/sticky)
- Hero intro section (compact, py-16)
- Main testing card (max-w-2xl centered)
  - Password input
  - Rules checklist
  - Submit button
  - Results display (conditional)
- Technical details (expandable)
- Footer
```

**Responsive Behavior**
- Mobile: Full-width with px-4 padding
- Tablet/Desktop: Centered max-w-2xl container
- All components stack vertically (no multi-column)

---

## Key Design Principles

1. **Clarity Over Decoration**: Every element serves validation feedback purpose
2. **Immediate Feedback**: Visual indicators update as user interacts
3. **Developer-Friendly**: Show both UI and API perspectives
4. **Accessibility**: High contrast text, clear focus states, semantic HTML
5. **Professional Polish**: Refined spacing, subtle shadows, smooth transitions

This interface prioritizes function while maintaining visual excellence - a tool developers would confidently share in portfolios.