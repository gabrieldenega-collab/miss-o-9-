# Password Validator Microservice - Guardião Lógico

## Overview
A backend-focused microservice that implements robust password validation logic with a beautiful testing interface. This project demonstrates pure business logic implementation with comprehensive validation rules and detailed error responses.

**Mission**: Missão 9 – O Validador de Senhas (Lógica de Backend)

## Recent Changes
- **2025-10-23**: ✅ Enhanced with advanced features (ALL FEATURES COMPLETE)
  - Password Strength Scoring: 0-100 point system with weak/medium/strong classification
  - Configurable Rules: Environment variable-based validation customization
  - Rate Limiting: 100 requests per 15 minutes with proper headers
  - API Documentation: Comprehensive Swagger/OpenAPI docs at /api-docs
  - All E2E tests passing across all features
  - Architect review: PASS - Production ready with all enhancements
  - **Status**: Feature-complete microservice ready for deployment

- **2025-01-23**: ✅ Initial MVP implementation (PRODUCTION READY)
  - Created password validation schema with TypeScript types
  - Built stunning dark-mode frontend testing interface
  - Configured design tokens following Material Design principles
  - Implemented real-time validation feedback UI
  - Implemented POST /api/validar-senha endpoint with regex-based validation (bonus completed!)
  - All end-to-end tests passing (valid/invalid password scenarios)
  - Architect review: PASS - Production ready

## Project Architecture

### Backend (Node.js + Express)
- **POST /api/validar-senha**: Main validation endpoint
  - Receives: `{ senha: string }`
  - Returns: `{ valida: boolean, erros?: string[] }`
  - Validation rules implemented with regex:
    - Minimum 8 characters
    - At least 1 uppercase letter (A-Z)
    - At least 1 number (0-9)
    - At least 1 special character (!@#$%^&*)

### Frontend (React + TypeScript)
- Single-page application with focused testing interface
- Real-time validation feedback as user types
- Beautiful success/error state displays
- Technical details section showing JSON request/response
- Dark mode optimized design

### Data Model (`shared/schema.ts`)
```typescript
PasswordValidationRequest {
  senha: string
}

PasswordValidationResponse {
  valida: boolean
  erros?: string[]  // Array of Portuguese error messages
}
```

## Key Features
1. **Regex-based Validation**: All character type checks use regular expressions (bonus challenge completed)
2. **Detailed Error Messages**: Returns specific, actionable error messages in Portuguese
3. **Real-time Feedback**: UI updates as user types, showing which rules pass/fail
4. **Developer-friendly**: Expandable technical details showing exact API request/response
5. **Professional Design**: Material Design-inspired interface with excellent UX
6. **Password Strength Scoring**: 0-100 point system categorizing passwords as weak/medium/strong
7. **Configurable Rules**: Validation rules customizable via environment variables
8. **Rate Limiting**: Prevents brute force with 100 requests per 15 minutes per IP
9. **API Documentation**: Interactive Swagger/OpenAPI docs at /api-docs
10. **Configuration UI**: View active validation rules at /config

## Design System
- **Primary Font**: Inter (clean, technical)
- **Monospace Font**: Fira Code (for password input and code blocks)
- **Color Scheme**: Deep charcoal backgrounds with vibrant accent colors
- **Status Colors**:
  - Success: Green (142 76% 45%)
  - Error: Red (0 84% 60%)
  - Info: Blue (217 91% 60%)

## Running the Project
```bash
npm run dev
```
Server runs on port 5000 with Express backend and Vite frontend.

## API Endpoint Details

### POST /api/validar-senha
**Request Body:**
```json
{
  "senha": "Senha@123"
}
```

**Response (Valid):**
```json
{
  "valida": true,
  "forca": "forte",
  "pontuacao": 85
}
```

**Response (Invalid):**
```json
{
  "valida": false,
  "erros": [
    "A senha precisa ter no mínimo 8 caracteres",
    "A senha precisa ter um número"
  ],
  "forca": "fraca",
  "pontuacao": 25
}
```

### GET /api/config
Returns current validation configuration

### GET /api/rate-limit-info
Returns rate limiting information

### GET /api-docs
Interactive Swagger/OpenAPI documentation

## Gamification
- **Badge**: Guardião Lógico ⚔️
- **XP**: 100 points (base) + 15 points (regex bonus)
- **Achievement**: Backend validation logic mastery

## Why Backend Validation?
Even with frontend validation, backend validation is essential because:
1. **Security**: Frontend validation can be bypassed by malicious users
2. **Data Integrity**: Ensures all data entering the system meets requirements
3. **API Independence**: Backend can be used by multiple clients (web, mobile, etc.)
4. **Business Logic**: Centralized validation rules that can't be circumvented
5. **Audit Trail**: Server-side logging of validation attempts
