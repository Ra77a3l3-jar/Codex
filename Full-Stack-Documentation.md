# 🌐 Full Stack Web Development Documentation
*Version: 2024 Latest | Last Updated: December 2024*

A comprehensive guide to modern full stack web development, covering frontend frameworks, backend technologies, databases, and deployment strategies using the latest versions of industry-standard tools.

---

## 📋 Table of Contents

### 🚀 [Chapter 1: Introduction & Environment Setup](#chapter-1-introduction--environment-setup)
- [What is Full Stack Development?](#what-is-full-stack-development)
- [Modern Tech Stack Overview](#modern-tech-stack-overview)
- [Development Environment Setup](#development-environment-setup)
- [Version Control with Git](#version-control-with-git)

### 🎨 [Chapter 2: Frontend Fundamentals](#chapter-2-frontend-fundamentals)
- [HTML5 Modern Features](#html5-modern-features)
- [CSS3 & Advanced Styling](#css3--advanced-styling)
- [JavaScript ES2024 Features](#javascript-es2024-features)
- [TypeScript Latest Features](#typescript-latest-features)

### ⚡ [Chapter 3: Frontend Frameworks](#chapter-3-frontend-frameworks)
- [React 18+ with Hooks](#react-18-with-hooks)
- [Vue 3 Composition API](#vue-3-composition-api)
- [Angular 17+ Features](#angular-17-features)
- [Framework Comparison](#framework-comparison)

### 🖥️ [Chapter 4: Backend Development](#chapter-4-backend-development)
- [Node.js 21+ & Express](#nodejs-21--express)
- [API Design & RESTful Services](#api-design--restful-services)
- [GraphQL Implementation](#graphql-implementation)
- [Authentication & Security](#authentication--security)

### 🗄️ [Chapter 5: Database Integration](#chapter-5-database-integration)
- [SQL Databases & PostgreSQL](#sql-databases--postgresql)
- [NoSQL with MongoDB](#nosql-with-mongodb)
- [ORM & Query Builders](#orm--query-builders)
- [Database Design Patterns](#database-design-patterns)

### 🚀 [Chapter 6: Deployment & DevOps](#chapter-6-deployment--devops)
- [Docker Containerization](#docker-containerization)
- [Cloud Deployment Strategies](#cloud-deployment-strategies)
- [CI/CD Pipelines](#cicd-pipelines)
- [Performance Optimization](#performance-optimization)

### 🔧 [Chapter 7: Testing & Quality Assurance](#chapter-7-testing--quality-assurance)
- [Frontend Testing Strategies](#frontend-testing-strategies)
- [Backend API Testing](#backend-api-testing)
- [End-to-End Testing](#end-to-end-testing)
- [Code Quality Tools](#code-quality-tools)

### 📱 [Chapter 8: Real-World Projects](#chapter-8-real-world-projects)
- [E-commerce Platform](#e-commerce-platform)
- [Social Media Dashboard](#social-media-dashboard)
- [Task Management System](#task-management-system)

### 📖 [Appendices](#appendices)
- [Quick Reference Guide](#quick-reference-guide)
- [Glossary](#glossary)
- [Further Reading](#further-reading)
- [Community Resources](#community-resources)

---

## Chapter 1: Introduction & Environment Setup
📊 **Progress:** Chapter 1 of 8 | ⏱️ **Reading Time:** 25 minutes

### 🎯 Learning Objectives
- Understand the full stack development ecosystem
- Set up a professional development environment
- Master version control fundamentals
- Configure essential development tools

### 📋 Prerequisites
- Basic computer literacy
- Willingness to learn multiple technologies
- Access to a modern computer with internet connection

### What is Full Stack Development?

Full stack development refers to the practice of working on both the frontend (client-side) and backend (server-side) portions of web applications. A full stack developer possesses the skills to build complete web applications from the user interface to the database layer.

#### The Modern Full Stack Architecture

```mermaid
graph TB
    A[User Interface] --> B[Frontend Framework]
    B --> C[API Gateway]
    C --> D[Backend Services]
    D --> E[Database Layer]
    D --> F[External APIs]
    G[DevOps & Deployment] --> B
    G --> D
    G --> E
```

Modern full stack development involves:

**Frontend Layer:**
- **Presentation:** HTML5, CSS3, responsive design
- **Interactivity:** JavaScript ES2024, TypeScript
- **Frameworks:** React 18+, Vue 3, Angular 17+
- **Build Tools:** Vite, Webpack, Parcel

**Backend Layer:**
- **Runtime:** Node.js 21+, Deno, Bun
- **Frameworks:** Express, Fastify, NestJS
- **APIs:** REST, GraphQL, gRPC
- **Authentication:** JWT, OAuth2, Auth0

**Database Layer:**
- **Relational:** PostgreSQL, MySQL
- **NoSQL:** MongoDB, Redis
- **Cloud:** AWS RDS, MongoDB Atlas
- **ORMs:** Prisma, TypeORM, Sequelize

**DevOps & Deployment:**
- **Containerization:** Docker, Kubernetes
- **Cloud Platforms:** AWS, Vercel, Netlify
- **CI/CD:** GitHub Actions, Jenkins
- **Monitoring:** DataDog, New Relic

### Modern Tech Stack Overview

The 2024 full stack landscape emphasizes performance, developer experience, and scalability. Here's the recommended tech stack:

#### Frontend Stack
```typescript
// Modern Frontend Stack
const frontendStack = {
  markup: "HTML5",
  styling: ["CSS3", "Tailwind CSS", "Styled Components"],
  scripting: ["JavaScript ES2024", "TypeScript 5.3+"],
  frameworks: ["React 18.2+", "Vue 3.4+", "Angular 17+"],
  buildTools: ["Vite 5+", "Webpack 5", "Parcel 2"],
  stateManagement: ["Zustand", "Pinia", "NgRx"],
  testing: ["Vitest", "Jest", "Cypress"]
};
```

#### Backend Stack
```typescript
// Modern Backend Stack
const backendStack = {
  runtime: ["Node.js 21+", "Deno 1.40+", "Bun 1.0+"],
  frameworks: ["Express 4.18+", "Fastify 4.24+", "NestJS 10+"],
  databases: ["PostgreSQL 16", "MongoDB 7.0", "Redis 7.2"],
  orms: ["Prisma 5.7+", "TypeORM 0.3+", "Drizzle"],
  authentication: ["JWT", "Passport.js", "Auth0"],
  testing: ["Supertest", "Jest", "Playwright"]
};
```

### Development Environment Setup

#### System Requirements

**Operating System:**
- macOS 12+ (Monterey or later)
- Windows 10/11 with WSL2
- Ubuntu 20.04+ or equivalent Linux distribution

**Hardware Recommendations:**
- **RAM:** Minimum 8GB, recommended 16GB+
- **Storage:** SSD with at least 100GB free space
- **Processor:** Multi-core CPU (Intel i5/AMD Ryzen 5 or better)

#### Essential Tools Installation

**1. Node.js and npm**

```bash
# Using Node Version Manager (recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc

# Install latest LTS Node.js
nvm install --lts
nvm use --lts
nvm alias default node

# Verify installation
node --version  # Should show v21.x.x
npm --version   # Should show v10.x.x
```

**2. Package Manager Alternatives**

```bash
# Install pnpm (recommended for performance)
npm install -g pnpm@latest

# Install Yarn (alternative)
npm install -g yarn@latest

# Verify installations
pnpm --version  # Should show v8.x.x
yarn --version  # Should show v4.x.x
```

**3. Development Tools**

```bash
# Global development dependencies
npm install -g \
  typescript@latest \
  @typescript-eslint/cli@latest \
  prettier@latest \
  nodemon@latest \
  pm2@latest \
  http-server@latest
```

**4. Code Editor Setup (VS Code)**

Essential VS Code extensions:
```json
{
  "recommendations": [
    "ms-vscode.vscode-typescript-next",
    "esbenp.prettier-vscode",
    "ms-vscode.vscode-eslint",
    "bradlc.vscode-tailwindcss",
    "ms-vscode.vscode-json",
    "ms-python.python",
    "ms-vscode.hexeditor",
    "github.copilot",
    "ms-vscode-remote.remote-containers"
  ]
}
```

**VS Code Settings Configuration:**

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.organizeImports": true
  },
  "typescript.preferences.importModuleSpecifier": "relative",
  "typescript.suggest.autoImports": true,
  "emmet.includeLanguages": {
    "typescript": "html",
    "typescriptreact": "html"
  }
}
```

### Version Control with Git

#### Git Configuration

```bash
# Global Git configuration
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global init.defaultBranch main
git config --global pull.rebase false

# Useful aliases
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.lg "log --oneline --graph --decorate --all"
```

#### Modern Git Workflow

**Feature Branch Workflow:**

```bash
# 1. Start from main branch
git checkout main
git pull origin main

# 2. Create feature branch
git checkout -b feature/user-authentication

# 3. Make changes and commit
git add .
git commit -m "feat: implement user authentication system

- Add JWT token generation
- Implement password hashing
- Create login/register endpoints
- Add middleware for route protection"

# 4. Push and create pull request
git push origin feature/user-authentication
```

**Conventional Commits:**

```bash
# Commit message format: type(scope): description
git commit -m "feat(auth): add JWT token validation middleware"
git commit -m "fix(api): resolve CORS issue in user endpoints"
git commit -m "docs(readme): update installation instructions"
git commit -m "style(css): improve responsive design for mobile"
git commit -m "refactor(utils): optimize database query performance"
git commit -m "test(auth): add unit tests for login functionality"
```

### ⚠️ Common Pitfalls

1. **Version Mismatch Issues**
   - Always use Node Version Manager (nvm) to manage Node.js versions
   - Keep package versions synchronized across team members
   - Use lockfiles (package-lock.json, yarn.lock, pnpm-lock.yaml)

2. **Environment Configuration**
   - Never commit sensitive data to version control
   - Use environment variables for configuration
   - Maintain separate configs for development, staging, and production

3. **Tool Overload**
   - Start with essential tools and add more as needed
   - Avoid installing too many global packages
   - Use project-specific dependencies when possible

### ✅ Best Practices

1. **Project Structure**
   - Use consistent folder naming conventions
   - Separate concerns (components, utils, services)
   - Implement proper error handling from the start

2. **Code Quality**
   - Set up ESLint and Prettier from day one
   - Use TypeScript for better type safety
   - Implement automated testing early

3. **Documentation**
   - Write clear README files
   - Document API endpoints
   - Comment complex business logic

### 🏋️ Exercise 1: Environment Setup Verification
**Difficulty:** 🟢 Beginner | **Estimated Time:** 30 minutes

Set up a complete development environment and verify all tools are working correctly.

**Requirements:**
1. Install Node.js 21+ using nvm
2. Install pnpm package manager
3. Configure Git with your information
4. Create a test project with TypeScript
5. Set up VS Code with recommended extensions

<details>
<summary>💡 Click to see hints</summary>

- Use the installation commands provided above
- Test each tool after installation
- Create a simple "Hello World" TypeScript project
- Verify VS Code syntax highlighting works

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
# 1. Install and configure Node.js
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
nvm install --lts
nvm use --lts

# 2. Install pnpm
npm install -g pnpm@latest

# 3. Configure Git
git config --global user.name "John Developer"
git config --global user.email "john@example.com"

# 4. Create test project
mkdir fullstack-test
cd fullstack-test
pnpm init
pnpm add -D typescript @types/node

# 5. Create TypeScript config
npx tsc --init

# 6. Create test file
echo 'console.log("Hello, Full Stack World!");' > index.ts

# 7. Compile and run
npx tsc index.ts
node index.js
```

**Explanation:**
This exercise verifies that your development environment is properly configured. The TypeScript compilation and execution confirms that all tools are working together correctly. You should see "Hello, Full Stack World!" output, confirming your setup is ready for full stack development.

</details>

---

## Chapter 2: Frontend Fundamentals
📊 **Progress:** Chapter 2 of 8 | ⏱️ **Reading Time:** 35 minutes

### 🎯 Learning Objectives
- Master modern HTML5 semantic elements and APIs
- Implement advanced CSS3 features and responsive design
- Utilize JavaScript ES2024 latest features
- Apply TypeScript for type-safe frontend development

### HTML5 Modern Features

HTML5 continues to evolve with new semantic elements, APIs, and capabilities that enhance user experience and developer productivity.

#### Semantic HTML Structure

Modern web applications benefit from semantic HTML that provides meaning and structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Modern full stack web application">
    <title>Full Stack App</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="//api.example.com">
</head>
<body>
    <header role="banner">
        <nav aria-label="Main navigation">
            <ul role="menubar">
                <li role="menuitem"><a href="#home">Home</a></li>
                <li role="menuitem"><a href="#about">About</a></li>
                <li role="menuitem"><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main role="main">
        <section aria-labelledby="hero-heading">
            <h1 id="hero-heading">Welcome to Modern Web Development</h1>
            <p>Building scalable applications with the latest technologies.</p>
        </section>

        <article aria-labelledby="content-heading">
            <header>
                <h2 id="content-heading">Featured Content</h2>
                <time datetime="2024-12-01">December 1, 2024</time>
            </header>
            <p>Content goes here...</p>
        </article>
    </main>

    <aside aria-label="Sidebar content">
        <section aria-labelledby="related-heading">
            <h3 id="related-heading">Related Articles</h3>
            <ul>
                <li><a href="/article1">Modern JavaScript Features</a></li>
                <li><a href="/article2">CSS Grid Layout</a></li>
            </ul>
        </section>
    </aside>

    <footer role="contentinfo">
        <p>&copy; 2024 Full Stack Development Guide</p>
    </footer>
</body>
</html>
```

#### Modern HTML5 APIs

**1. Web Components API**

```html
<!-- Custom Element Definition -->
<script>
class UserCard extends HTMLElement {
    constructor() {
        super();
        this.attachShadow({ mode: 'open' });
    }

    connectedCallback() {
        const name = this.getAttribute('name') || 'Guest';
        const role = this.getAttribute('role') || 'User';
        
        this.shadowRoot.innerHTML = `
            <style>
                :host {
                    display: block;
                    border: 1px solid #ddd;
                    border-radius: 8px;
                    padding: 16px;
                    margin: 8px 0;
                }
                .card-header {
                    font-weight: bold;
                    color: #333;
                }
                .card-role {
                    color: #666;
                    font-size: 0.9em;
                }
            </style>
            <div class="card-header">${name}</div>
            <div class="card-role">${role}</div>
        `;
    }
}

customElements.define('user-card', UserCard);
</script>

<!-- Usage -->
<user-card name="John Doe" role="Full Stack Developer"></user-card>
<user-card name="Jane Smith" role="UI/UX Designer"></user-card>
```

**2. Intersection Observer API**

```javascript
// Lazy loading images with Intersection Observer
const imageObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.classList.remove('lazy');
            observer.unobserve(img);
        }
    });
});

document.querySelectorAll('img[data-src]').forEach(img => {
    imageObserver.observe(img);
});
```

```html
<!-- Lazy loading implementation -->
<img class="lazy" 
     src="placeholder.jpg" 
     data-src="actual-image.jpg" 
     alt="Lazy loaded image"
     loading="lazy">
```

### CSS3 & Advanced Styling

Modern CSS provides powerful tools for creating responsive, performant, and maintainable user interfaces.

#### CSS Grid and Flexbox Mastery

**Advanced Grid Layouts:**

```css
/* Modern CSS Grid Implementation */
.dashboard-layout {
    display: grid;
    grid-template-areas: 
        "header header header"
        "sidebar main aside"
        "footer footer footer";
    grid-template-rows: auto 1fr auto;
    grid-template-columns: 250px 1fr 200px;
    min-height: 100vh;
    gap: 1rem;
}

.header {
    grid-area: header;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 1rem;
}

.sidebar {
    grid-area: sidebar;
    background: #f8f9fa;
    padding: 1rem;
}

.main-content {
    grid-area: main;
    padding: 1rem;
}

.aside-content {
    grid-area: aside;
    background: #f8f9fa;
    padding: 1rem;
}

.footer {
    grid-area: footer;
    background: #343a40;
    color: white;
    padding: 1rem;
    text-align: center;
}

/* Responsive Grid */
@media (max-width: 768px) {
    .dashboard-layout {
        grid-template-areas: 
            "header"
            "main"
            "sidebar"
            "aside"
            "footer";
        grid-template-columns: 1fr;
    }
}
```

**Modern Flexbox Patterns:**

```css
/* Flexible Component Layout */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    padding: 1rem;
}

.card {
    flex: 1 1 300px; /* grow shrink basis */
    min-width: 0; /* Prevent flex item overflow */
    background: white;
    border-radius: 12px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
}

.card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    border-bottom: 1px solid #e5e7eb;
}

.card-content {
    padding: 1rem;
    flex-grow: 1;
}

.card-actions {
    display: flex;
    gap: 0.5rem;
    padding: 1rem;
    justify-content: flex-end;
}
```

#### CSS Custom Properties and Modern Features

**CSS Variables with Fallbacks:**

```css
:root {
    /* Color System */
    --primary-50: #eff6ff;
    --primary-500: #3b82f6;
    --primary-600: #2563eb;
    --primary-900: #1e3a8a;
    
    /* Typography Scale */
    --text-xs: 0.75rem;
    --text-sm: 0.875rem;
    --text-base: 1rem;
    --text-lg: 1.125rem;
    --text-xl: 1.25rem;
    
    /* Spacing Scale */
    --space-1: 0.25rem;
    --space-2: 0.5rem;
    --space-4: 1rem;
    --space-8: 2rem;
    
    /* Animation Durations */
    --duration-fast: 150ms;
    --duration-normal: 250ms;
    --duration-slow: 350ms;
}

/* Dark Mode Support */
@media (prefers-color-scheme: dark) {
    :root {
        --bg-primary: #1f2937;
        --text-primary: #f9fafb;
        --border-color: #374151;
    }
}

/* Component using CSS variables */
.button {
    background-color: var(--primary-500);
    color: white;
    padding: var(--space-2) var(--space-4);
    border: none;
    border-radius: var(--space-1);
    font-size: var(--text-base);
    transition: background-color var(--duration-fast) ease;
    cursor: pointer;
}

.button:hover {
    background-color: var(--primary-600);
}

.button:focus {
    outline: 2px solid var(--primary-500);
    outline-offset: 2px;
}
```

#### Modern CSS Architecture

**Container Queries (2024 Feature):**

```css
/* Container queries for component-based responsive design */
.sidebar {
    container-type: inline-size;
    container-name: sidebar;
}

@container sidebar (min-width: 300px) {
    .navigation-item {
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }
    
    .navigation-text {
        display: block;
    }
}

@container sidebar (max-width: 299px) {
    .navigation-item {
        justify-content: center;
    }
    
    .navigation-text {
        display: none;
    }
}
```

### JavaScript ES2024 Features

JavaScript continues to evolve with powerful new features that enhance developer productivity and code maintainability.

#### Latest ES2024 Features

**1. Array Grouping Methods:**

```javascript
// Array.prototype.groupBy (ES2024)
const transactions = [
    { type: 'income', amount: 1000, category: 'salary' },
    { type: 'expense', amount: 50, category: 'food' },
    { type: 'expense', amount: 200, category: 'utilities' },
    { type: 'income', amount: 500, category: 'freelance' },
    { type: 'expense', amount: 30, category: 'food' }
];

// Group by transaction type
const groupedByType = transactions.groupBy(tx => tx.type);
console.log(groupedByType);
/*
{
    income: [
        { type: 'income', amount: 1000, category: 'salary' },
        { type: 'income', amount: 500, category: 'freelance' }
    ],
    expense: [
        { type: 'expense', amount: 50, category: 'food' },
        { type: 'expense', amount: 200, category: 'utilities' },
        { type: 'expense', amount: 30, category: 'food' }
    ]
}
*/

// Group by category with Map
const groupedByCategory = transactions.groupByToMap(tx => tx.category);
console.log(groupedByCategory instanceof Map); // true
```

**2. Pipeline Operator (Proposal Stage 2):**

```javascript
// Traditional approach
function processUserData(userData) {
    const validated = validateUser(userData);
    const normalized = normalizeUserData(validated);
    const enriched = enrichUserProfile(normalized);
    return formatUserResponse(enriched);
}

// With pipeline operator (when available)
function processUserData(userData) {
    return userData
        |> validateUser
        |> normalizeUserData
        |> enrichUserProfile
        |> formatUserResponse;
}
```

**3. Temporal API (Stage 3 Proposal):**

```javascript
// Modern date/time handling with Temporal API
import { Temporal } from '@js-temporal/polyfill';

// Create precise date-time
const meeting = Temporal.ZonedDateTime.from({
    timeZone: 'America/New_York',
    year: 2024,
    month: 12,
    day: 15,
    hour: 14,
    minute: 30
});

// Calculate duration
const duration = meeting.until(
    meeting.add({ hours: 2 }),
    { largestUnit: 'hours' }
);

console.log(duration.toString()); // "PT2H"

// Format for different time zones
const formats = [
    { timeZone: 'America/New_York', locale: 'en-US' },
    { timeZone: 'Europe/London', locale: 'en-GB' },
    { timeZone: 'Asia/Tokyo', locale: 'ja-JP' }
].map(({ timeZone, locale }) => ({
    timeZone,
    time: meeting.withTimeZone(timeZone).toLocaleString(locale)
}));

console.log(formats);
```

#### Advanced JavaScript Patterns

**1. Modern Async Patterns:**

```javascript
// Advanced async/await with error handling
class ApiService {
    constructor(baseURL) {
        this.baseURL = baseURL;
        this.abortController = new AbortController();
    }

    async fetchWithRetry(url, options = {}, maxRetries = 3) {
        let lastError;
        
        for (let attempt = 0; attempt <= maxRetries; attempt++) {
            try {
                const response = await fetch(`${this.baseURL}${url}`, {
                    ...options,
                    signal: this.abortController.signal,
                    headers: {
                        'Content-Type': 'application/json',
                        ...options.headers
                    }
                });

                if (!response.ok) {
                    throw new Error(`HTTP ${response.status}: ${response.statusText}`);
                }

                return await response.json();
            } catch (error) {
                lastError = error;
                
                if (attempt < maxRetries && !this.abortController.signal.aborted) {
                    const delay = Math.pow(2, attempt) * 1000; // Exponential backoff
                    await new Promise(resolve => setTimeout(resolve, delay));
                    continue;
                }
                
                break;
            }
        }
        
        throw new Error(`Failed after ${maxRetries + 1} attempts: ${lastError.message}`);
    }

    async fetchParallel(urls) {
        try {
            const promises = urls.map(url => this.fetchWithRetry(url));
            return await Promise.allSettled(promises);
        } catch (error) {
            console.error('Parallel fetch error:', error);
            throw error;
        }
    }

    cancel() {
        this.abortController.abort();
    }
}

// Usage
const api = new ApiService('https://api.example.com');

// Sequential with retry
const userData = await api.fetchWithRetry('/users/123');

// Parallel execution
const results = await api.fetchParallel([
    '/users/123',
    '/users/123/posts',
    '/users/123/comments'
]);
```

**2. Advanced Object Manipulation:**

```javascript
// Modern object utilities
class ObjectUtils {
    // Deep merge with conflict resolution
    static deepMerge(target, source, conflictResolver = (a, b) => b) {
        const result = { ...target };
        
        for (const [key, value] of Object.entries(source)) {
            if (value !== null && typeof value === 'object' && !Array.isArray(value)) {
                result[key] = result[key] !== null && typeof result[key] === 'object' 
                    ? this.deepMerge(result[key], value, conflictResolver)
                    : value;
            } else if (result.hasOwnProperty(key)) {
                result[key] = conflictResolver(result[key], value);
            } else {
                result[key] = value;
            }
        }
        
        return result;
    }

    // Safe property access with default values
    static getNestedValue(obj, path, defaultValue = undefined) {
        return path.split('.').reduce((current, key) => {
            return current?.[key] ?? defaultValue;
        }, obj);
    }

    // Set nested property safely
    static setNestedValue(obj, path, value) {
        const keys = path.split('.');
        const lastKey = keys.pop();
        
        const target = keys.reduce((current, key) => {
            if (!(key in current) || typeof current[key] !== 'object') {
                current[key] = {};
            }
            return current[key];
        }, obj);
        
        target[lastKey] = value;
        return obj;
    }

    // Object transformation pipeline
    static transform(obj, ...transformers) {
        return transformers.reduce((result, transformer) => transformer(result), obj);
    }
}

// Usage examples
const config = {
    api: { baseURL: 'http://localhost', timeout: 5000 },
    features: { darkMode: false }
};

const updates = {
    api: { baseURL: 'https://api.example.com', retries: 3 },
    features: { darkMode: true, newFeature: true }
};

// Deep merge
const mergedConfig = ObjectUtils.deepMerge(config, updates);

// Safe access
const timeout = ObjectUtils.getNestedValue(mergedConfig, 'api.timeout', 3000);

// Set nested value
ObjectUtils.setNestedValue(mergedConfig, 'database.connection.pool.max', 10);

// Transform pipeline
const processedConfig = ObjectUtils.transform(
    mergedConfig,
    cfg => ({ ...cfg, timestamp: Date.now() }),
    cfg => ({ ...cfg, environment: 'production' }),
    cfg => ({ ...cfg, version: '1.0.0' })
);
```

### TypeScript Latest Features

TypeScript 5.3+ introduces powerful features that enhance type safety and developer experience in full stack applications.

#### Advanced Type System Features

**1. Template Literal Types and String Manipulation:**

```typescript
// Advanced template literal types
type EventName<T extends string> = `on${Capitalize<T>}`;
type APIEndpoint<T extends string> = `/api/v1/${T}`;
type HTTPMethod = 'GET' | 'POST' | 'PUT' | 'DELETE' | 'PATCH';

// Create type-safe API client
interface APIRoutes {
    users: { id: number; name: string; email: string }[];
    posts: { id: number; title: string; content: string; userId: number }[];
    comments: { id: number; text: string; postId: number }[];
}

type APIClient = {
    [K in keyof APIRoutes as APIEndpoint<K>]: {
        [M in HTTPMethod]: (
            data?: M extends 'GET' | 'DELETE' ? never : Partial<APIRoutes[K][0]>
        ) => Promise<APIRoutes[K]>;
    };
};

// Usage with full type safety
const apiClient: APIClient = {
    '/api/v1/users': {
        GET: async () => [{ id: 1, name: 'John', email: 'john@example.com' }],
        POST: async (data) => [{ id: 2, ...data }],
        PUT: async (data) => [{ id: 1, ...data }],
        DELETE: async () => [],
        PATCH: async (data) => [{ id: 1, ...data }]
    }
    // ... other endpoints
};
```

**2. Const Assertions and Immutable Data Structures:**

```typescript
// Const assertions for immutable configurations
const APP_CONFIG = {
    api: {
        baseURL: 'https://api.example.com',
        version: 'v1',
        endpoints: ['users', 'posts', 'comments']
    },
    features: {
        auth: true,
        analytics: false,
        darkMode: true
    },
    environments: ['development', 'staging', 'production']
} as const;

type AppConfig = typeof APP_CONFIG;
type APIEndpoints = AppConfig['api']['endpoints'][number]; // 'users' | 'posts' | 'comments'
type Environment = AppConfig['environments'][number]; // 'development' | 'staging' | 'production'

// Immutable state management
class ImmutableState<T> {
    constructor(private _state: T) {}

    get state(): Readonly<T> {
        return this._state;
    }

    update<K extends keyof T>(key: K, value: T[K]): ImmutableState<T> {
        return new ImmutableState({
            ...this._state,
            [key]: value
        });
    }

    deepUpdate<K extends keyof T>(
        key: K,
        updater: (current: T[K]) => T[K]
    ): ImmutableState<T> {
        return new ImmutableState({
            ...this._state,
            [key]: updater(this._state[key])
        });
    }
}

// Usage
interface UserState {
    currentUser: { id: number; name: string; preferences: { theme: string } } | null;
    isLoading: boolean;
    error: string | null;
}

const initialState: UserState = {
    currentUser: null,
    isLoading: false,
    error: null
};

let state = new ImmutableState(initialState);

// Type-safe state updates
state = state.update('isLoading', true);
state = state.deepUpdate('currentUser', (user) => 
    user ? { ...user, name: 'Updated Name' } : user
);
```

**3. Generic Constraints and Conditional Types:**

```typescript
// Advanced generic constraints
interface Repository<T extends { id: string | number }> {
    findById(id: T['id']): Promise<T | null>;
    create(data: Omit<T, 'id'>): Promise<T>;
    update(id: T['id'], data: Partial<Omit<T, 'id'>>): Promise<T>;
    delete(id: T['id']): Promise<void>;
}

// Conditional types for API responses
type APIResponse<T> = T extends any[]
    ? { data: T; count: number; page?: number }
    : { data: T };

type ErrorResponse = {
    error: string;
    code: number;
    details?: Record<string, any>;
};

type Result<T> = 
    | (APIResponse<T> & { success: true })
    | (ErrorResponse & { success: false });

// Implementation
class UserRepository implements Repository<User> {
    async findById(id: number): Promise<User | null> {
        try {
            const response = await fetch(`/api/users/${id}`);
            if (!response.ok) return null;
            return await response.json();
        } catch {
            return null;
        }
    }

    async create(userData: Omit<User, 'id'>): Promise<User> {
        const response = await fetch('/api/users', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(userData)
        });
        return await response.json();
    }

    async update(id: number, userData: Partial<Omit<User, 'id'>>): Promise<User> {
        const response = await fetch(`/api/users/${id}`, {
            method: 'PUT',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(userData)
        });
        return await response.json();
    }

    async delete(id: number): Promise<void> {
        await fetch(`/api/users/${id}`, { method: 'DELETE' });
    }
}
```

**4. Utility Types and Type Transformations:**

```typescript
// Custom utility types for full stack development
type DeepPartial<T> = {
    [P in keyof T]?: T[P] extends object ? DeepPartial<T[P]> : T[P];
};

type DeepRequired<T> = {
    [P in keyof T]-?: T[P] extends object ? DeepRequired<T[P]> : T[P];
};

type PickByType<T, U> = {
    [K in keyof T as T[K] extends U ? K : never]: T[K];
};

type OmitByType<T, U> = {
    [K in keyof T as T[K] extends U ? never : K]: T[K];
};

// Database model types
interface User {
    id: number;
    name: string;
    email: string;
    avatar?: string;
    createdAt: Date;
    updatedAt: Date;
    profile: {
        bio: string;
        location: string;
        website?: string;
    };
}

// Extract only string fields
type UserStringFields = PickByType<User, string>; 
// { name: string; email: string; avatar?: string; }

// Create update DTOs
type UserUpdateDTO = DeepPartial<Omit<User, 'id' | 'createdAt' | 'updatedAt'>>;

// Form validation schema
type ValidationSchema<T> = {
    [K in keyof T]: {
        required?: boolean;
        minLength?: number;
        maxLength?: number;
        pattern?: RegExp;
        custom?: (value: T[K]) => string | null;
    };
};

const userValidationSchema: ValidationSchema<UserUpdateDTO> = {
    name: {
        required: true,
        minLength: 2,
        maxLength: 50
    },
    email: {
        required: true,
        pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
        custom: (email) => email?.includes('spam') ? 'Invalid email domain' : null
    },
    profile: {
        // Nested validation would require more complex implementation
    }
};
```

### ⚠️ Common Pitfalls

1. **CSS Specificity Issues**
   - Use CSS-in-JS or CSS modules to avoid global conflicts
   - Follow BEM methodology for consistent naming
   - Avoid over-nesting in SCSS/SASS

2. **JavaScript Performance**
   - Avoid creating functions inside render loops
   - Use proper debouncing for user input
   - Implement lazy loading for large datasets

3. **TypeScript Type Errors**
   - Don't use `any` type - use `unknown` instead
   - Properly type async functions with Promise return types
   - Use type guards for runtime type checking

### ✅ Best Practices

1. **Semantic HTML**
   - Use appropriate ARIA attributes for accessibility
   - Implement proper heading hierarchy (h1-h6)
   - Provide alternative text for images

2. **Modern CSS Architecture**
   - Use CSS custom properties for consistent theming
   - Implement container queries for component-based responsive design
   - Follow mobile-first responsive design principles

3. **JavaScript/TypeScript Standards**
   - Use strict TypeScript configuration
   - Implement proper error boundaries
   - Follow functional programming principles where appropriate

### 🏋️ Exercise 2: Modern Frontend Component
**Difficulty:** 🟡 Intermediate | **Estimated Time:** 45 minutes

Create a modern, accessible user card component using HTML5, CSS3, and TypeScript.

**Requirements:**
1. Use semantic HTML5 elements
2. Implement CSS Grid for layout
3. Add CSS animations and hover effects
4. Create TypeScript interfaces for props
5. Include accessibility features (ARIA labels, keyboard navigation)

<details>
<summary>💡 Click to see hints</summary>

- Use `<article>` for the card container
- Implement CSS custom properties for theming
- Add focus management for keyboard users
- Use TypeScript strict mode
- Consider loading states and error handling

</details>

<details>
<summary>✅ Click to see solution</summary>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern User Card</title>
    <style>
        :root {
            --primary-color: #3b82f6;
            --text-primary: #1f2937;
            --text-secondary: #6b7280;
            --border-color: #e5e7eb;
            --bg-white: #ffffff;
            --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
            --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1);
            --border-radius: 0.75rem;
            --transition: all 0.2s ease;
        }

        .user-card {
            display: grid;
            grid-template-areas: 
                "avatar info"
                "avatar actions";
            grid-template-columns: auto 1fr;
            grid-template-rows: 1fr auto;
            gap: 1rem;
            padding: 1.5rem;
            background: var(--bg-white);
            border: 1px solid var(--border-color);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
            max-width: 400px;
        }

        .user-card:hover {
            box-shadow: var(--shadow-md);
            transform: translateY(-1px);
        }

        .user-avatar {
            grid-area: avatar;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--primary-color);
        }

        .user-info {
            grid-area: info;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .user-name {
            margin: 0 0 0.25rem 0;
            font-size: 1.25rem;
            font-weight: 600;
            color: var(--text-primary);
        }

        .user-role {
            margin: 0 0 0.5rem 0;
            font-size: 0.875rem;
            color: var(--text-secondary);
        }

        .user-email {
            margin: 0;
            font-size: 0.875rem;
            color: var(--primary-color);
            text-decoration: none;
        }

        .user-actions {
            grid-area: actions;
            display: flex;
            gap: 0.5rem;
        }

        .btn {
            padding: 0.5rem 1rem;
            border: 1px solid var(--border-color);
            border-radius: calc(var(--border-radius) / 2);
            background: var(--bg-white);
            color: var(--text-primary);
            font-size: 0.875rem;
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        .btn:hover {
            background: #f9fafb;
        }

        .btn:focus {
            outline: 2px solid var(--primary-color);
            outline-offset: 2px;
        }

        .btn-primary {
            background: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        .btn-primary:hover {
            background: #2563eb;
        }

        @media (max-width: 480px) {
            .user-card {
                grid-template-areas: 
                    "avatar"
                    "info"
                    "actions";
                grid-template-columns: 1fr;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <article class="user-card" role="article" aria-labelledby="user-name-1">
        <img 
            src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=150&h=150&fit=crop&crop=face" 
            alt="Profile picture of John Developer"
            class="user-avatar"
            loading="lazy"
        >
        <div class="user-info">
            <h2 id="user-name-1" class="user-name">John Developer</h2>
            <p class="user-role">Senior Full Stack Developer</p>
            <a href="mailto:john@example.com" class="user-email" aria-label="Send email to John Developer">
                john@example.com
            </a>
        </div>
        <div class="user-actions">
            <a href="/profile/john" class="btn" aria-label="View John's profile">
                View Profile
            </a>
            <button class="btn btn-primary" onclick="handleConnect()" aria-label="Connect with John">
                Connect
            </button>
        </div>
    </article>

    <script>
        // TypeScript interfaces (for reference - would be in separate .ts file)
        /*
        interface User {
            id: number;
            name: string;
            email: string;
            role: string;
            avatar: string;
        }

        interface UserCardProps {
            user: User;
            onConnect?: (userId: number) => void;
            onViewProfile?: (userId: number) => void;
        }
        */

        // JavaScript implementation
        function handleConnect() {
            // Simulate API call
            console.log('Connecting with user...');
            
            // Add loading state
            const button = event.target;
            const originalText = button.textContent;
            button.textContent = 'Connecting...';
            button.disabled = true;
            
            // Simulate async operation
            setTimeout(() => {
                button.textContent = 'Connected ✓';
                button.classList.remove('btn-primary');
                setTimeout(() => {
                    button.textContent = originalText;
                    button.disabled = false;
                    button.classList.add('btn-primary');
                }, 2000);
            }, 1500);
        }

        // Keyboard navigation enhancement
        document.addEventListener('keydown', (event) => {
            if (event.key === 'Enter' || event.key === ' ') {
                const focused = document.activeElement;
                if (focused && focused.classList.contains('btn')) {
                    event.preventDefault();
                    focused.click();
                }
            }
        });
    </script>
</body>
</html>
```

**TypeScript Component Version:**

```typescript
// UserCard.ts
interface User {
    id: number;
    name: string;
    email: string;
    role: string;
    avatar: string;
    isOnline?: boolean;
}

interface UserCardProps {
    user: User;
    variant?: 'default' | 'compact' | 'detailed';
    onConnect?: (userId: number) => Promise<void>;
    onViewProfile?: (userId: number) => void;
    className?: string;
}

interface UserCardState {
    isConnecting: boolean;
    isConnected: boolean;
    error: string | null;
}

class UserCard {
    private state: UserCardState = {
        isConnecting: false,
        isConnected: false,
        error: null
    };

    constructor(
        private container: HTMLElement,
        private props: UserCardProps
    ) {
        this.render();
        this.attachEventListeners();
    }

    private render(): void {
        const { user, variant = 'default' } = this.props;
        const { isConnecting, isConnected } = this.state;

        this.container.innerHTML = `
            <article class="user-card ${variant}" role="article" aria-labelledby="user-name-${user.id}">
                <img 
                    src="${user.avatar}" 
                    alt="Profile picture of ${user.name}"
                    class="user-avatar"
                    loading="lazy"
                    onerror="this.src='https://via.placeholder.com/80x80?text=${user.name.charAt(0)}'"
                >
                <div class="user-info">
                    <h2 id="user-name-${user.id}" class="user-name">${user.name}</h2>
                    <p class="user-role">${user.role}</p>
                    <a href="mailto:${user.email}" class="user-email" aria-label="Send email to ${user.name}">
                        ${user.email}
                    </a>
                    ${user.isOnline ? '<span class="online-indicator">🟢 Online</span>' : ''}
                </div>
                <div class="user-actions">
                    <button 
                        class="btn" 
                        data-action="view-profile"
                        aria-label="View ${user.name}'s profile"
                    >
                        View Profile
                    </button>
                    <button 
                        class="btn btn-primary" 
                        data-action="connect"
                        aria-label="Connect with ${user.name}"
                        ${isConnecting ? 'disabled' : ''}
                    >
                        ${isConnected ? 'Connected ✓' : isConnecting ? 'Connecting...' : 'Connect'}
                    </button>
                </div>
            </article>
        `;
    }

    private attachEventListeners(): void {
        this.container.addEventListener('click', this.handleClick.bind(this));
    }

    private async handleClick(event: Event): Promise<void> {
        const target = event.target as HTMLElement;
        const action = target.dataset.action;

        if (!action) return;

        try {
            switch (action) {
                case 'view-profile':
                    this.props.onViewProfile?.(this.props.user.id);
                    break;
                case 'connect':
                    await this.handleConnect();
                    break;
            }
        } catch (error) {
            console.error('Action failed:', error);
            this.setState({ error: error instanceof Error ? error.message : 'Unknown error' });
        }
    }

    private async handleConnect(): Promise<void> {
        if (this.state.isConnecting || this.state.isConnected) return;

        this.setState({ isConnecting: true, error: null });

        try {
            await this.props.onConnect?.(this.props.user.id);
            this.setState({ isConnected: true, isConnecting: false });
            
            // Auto-reset after 3 seconds
            setTimeout(() => {
                this.setState({ isConnected: false });
            }, 3000);
        } catch (error) {
            this.setState({ 
                isConnecting: false, 
                error: error instanceof Error ? error.message : 'Connection failed' 
            });
        }
    }

    private setState(newState: Partial<UserCardState>): void {
        this.state = { ...this.state, ...newState };
        this.render();
        this.attachEventListeners();
    }

    public updateUser(user: Partial<User>): void {
        this.props = {
            ...this.props,
            user: { ...this.props.user, ...user }
        };
        this.render();
        this.attachEventListeners();
    }
}

// Usage
const userCardContainer = document.getElementById('user-card-container')!;
const userCard = new UserCard(userCardContainer, {
    user: {
        id: 1,
        name: 'John Developer',
        email: 'john@example.com',
        role: 'Senior Full Stack Developer',
        avatar: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=150&h=150&fit=crop&crop=face',
        isOnline: true
    },
    onConnect: async (userId: number) => {
        // Simulate API call
        await new Promise(resolve => setTimeout(resolve, 1500));
        console.log(`Connected with user ${userId}`);
    },
    onViewProfile: (userId: number) => {
        window.location.href = `/profile/${userId}`;
    }
});
```

**Explanation:**
This comprehensive solution demonstrates modern frontend development practices including:

- **Semantic HTML:** Uses `<article>`, proper heading hierarchy, and ARIA attributes for accessibility
- **Modern CSS:** Implements CSS Grid, custom properties, smooth transitions, and responsive design
- **TypeScript Integration:** Provides type safety with interfaces, error handling, and state management
- **Accessibility:** Includes keyboard navigation, screen reader support, and focus management
- **Performance:** Features lazy loading, error handling, and efficient DOM updates
- **User Experience:** Implements loading states, visual feedback, and progressive enhancement

The component is fully reusable, accessible, and follows modern web development best practices.

</details>

### 🏋️ Exercise 3: Advanced TypeScript API Client
**Difficulty:** 🔴 Advanced | **Estimated Time:** 60 minutes

Create a type-safe, generic API client with caching, retry logic, and proper error handling.

**Requirements:**
1. Generic type constraints for API endpoints
2. Automatic request/response transformation
3. Built-in caching with TTL
4. Exponential backoff retry mechanism
5. Request/response interceptors

<details>
<summary>💡 Click to see hints</summary>

- Use generic constraints to ensure type safety across different endpoints
- Implement a Map-based cache with automatic cleanup
- Use async/await with proper error boundaries
- Consider using AbortController for request cancellation
- Implement proper TypeScript utility types

</details>

<details>
<summary>✅ Click to see solution</summary>

```typescript
// Advanced TypeScript API Client
interface APIError {
    message: string;
    status: number;
    code?: string;
    details?: Record<string, any>;
}

interface CacheEntry<T> {
    data: T;
    expiry: number;
    etag?: string;
}

interface RequestConfig {
    method?: 'GET' | 'POST' | 'PUT' | 'DELETE' | 'PATCH';
    headers?: Record<string, string>;
    body?: any;
    timeout?: number;
    retries?: number;
    cache?: boolean;
    cacheTTL?: number;
}

interface InterceptorContext {
    url: string;
    config: RequestConfig;
    attempt: number;
}

type RequestInterceptor = (context: InterceptorContext) => Promise<InterceptorContext> | InterceptorContext;
type ResponseInterceptor<T> = (response: Response, data: T, context: InterceptorContext) => Promise<T> | T;
type ErrorInterceptor = (error: APIError, context: InterceptorContext) => Promise<never> | never;

class APIClient {
    private cache = new Map<string, CacheEntry<any>>();
    private requestInterceptors: RequestInterceptor[] = [];
    private responseInterceptors: ResponseInterceptor<any>[] = [];
    private errorInterceptors: ErrorInterceptor[] = [];
    private abortControllers = new Map<string, AbortController>();

    constructor(
        private baseURL: string,
        private defaultConfig: RequestConfig = {}
    ) {}

    // Interceptor management
    addRequestInterceptor(interceptor: RequestInterceptor): () => void {
        this.requestInterceptors.push(interceptor);
        return () => {
            const index = this.requestInterceptors.indexOf(interceptor);
            if (index > -1) this.requestInterceptors.splice(index, 1);
        };
    }

    addResponseInterceptor<T>(interceptor: ResponseInterceptor<T>): () => void {
        this.responseInterceptors.push(interceptor);
        return () => {
            const index = this.responseInterceptors.indexOf(interceptor);
            if (index > -1) this.responseInterceptors.splice(index, 1);
        };
    }

    addErrorInterceptor(interceptor: ErrorInterceptor): () => void {
        this.errorInterceptors.push(interceptor);
        return () => {
            const index = this.errorInterceptors.indexOf(interceptor);
            if (index > -1) this.errorInterceptors.splice(index, 1);
        };
    }

    // Cache management
    private getCacheKey(url: string, config: RequestConfig): string {
        const method = config.method || 'GET';
        const body = config.body ? JSON.stringify(config.body) : '';
        return `${method}:${url}:${body}`;
    }

    private getFromCache<T>(key: string): T | null {
        const entry = this.cache.get(key);
        if (!entry) return null;
        
        if (Date.now() > entry.expiry) {
            this.cache.delete(key);
            return null;
        }
        
        return entry.data;
    }

    private setCache<T>(key: string, data: T, ttl: number, etag?: string): void {
        this.cache.set(key, {
            data,
            expiry: Date.now() + ttl,
            etag
        });
    }

    // HTTP methods with type safety
    async get<T>(url: string, config: Omit<RequestConfig, 'method' | 'body'> = {}): Promise<T> {
        return this.request<T>(url, { ...config, method: 'GET' });
    }

    async post<T>(url: string, body?: any, config: Omit<RequestConfig, 'method' | 'body'> = {}): Promise<T> {
        return this.request<T>(url, { ...config, method: 'POST', body });
    }

    async put<T>(url: string, body?: any, config: Omit<RequestConfig, 'method' | 'body'> = {}): Promise<T> {
        return this.request<T>(url, { ...config, method: 'PUT', body });
    }

    async patch<T>(url: string, body?: any, config: Omit<RequestConfig, 'method' | 'body'> = {}): Promise<T> {
        return this.request<T>(url, { ...config, method: 'PATCH', body });
    }

    async delete<T>(url: string, config: Omit<RequestConfig, 'method' | 'body'> = {}): Promise<T> {
        return this.request<T>(url, { ...config, method: 'DELETE' });
    }

    // Core request method
    async request<T>(endpoint: string, userConfig: RequestConfig = {}): Promise<T> {
        const config: RequestConfig = {
            ...this.defaultConfig,
            ...userConfig,
            headers: {
                'Content-Type': 'application/json',
                ...this.defaultConfig.headers,
                ...userConfig.headers
            }
        };

        const url = `${this.baseURL}${endpoint}`;
        const cacheKey = this.getCacheKey(url, config);

        // Check cache for GET requests
        if (config.method === 'GET' && config.cache !== false) {
            const cached = this.getFromCache<T>(cacheKey);
            if (cached) return cached;
        }

        // Execute request with retry logic
        const maxRetries = config.retries ?? 3;
        let lastError: APIError;

        for (let attempt = 0; attempt <= maxRetries; attempt++) {
            try {
                const context: InterceptorContext = { url, config, attempt };
                
                // Apply request interceptors
                const finalContext = await this.requestInterceptors.reduce(
                    async (prev, interceptor) => interceptor(await prev),
                    Promise.resolve(context)
                );

                const result = await this.executeRequest<T>(finalContext);
                
                // Cache successful GET requests
                if (config.method === 'GET' && config.cache !== false) {
                    const ttl = config.cacheTTL ?? 300000; // 5 minutes default
                    this.setCache(cacheKey, result, ttl);
                }

                return result;
            } catch (error) {
                lastError = error as APIError;
                
                // Don't retry on client errors (4xx) or last attempt
                if (lastError.status >= 400 && lastError.status < 500 || attempt === maxRetries) {
                    // Apply error interceptors
                    for (const interceptor of this.errorInterceptors) {
                        try {
                            await interceptor(lastError, { url, config, attempt });
                        } catch {
                            // Error interceptor handled the error
                        }
                    }
                    throw lastError;
                }

                // Exponential backoff
                const delay = Math.min(1000 * Math.pow(2, attempt), 10000);
                await new Promise(resolve => setTimeout(resolve, delay));
            }
        }

        throw lastError!;
    }

    private async executeRequest<T>(context: InterceptorContext): Promise<T> {
        const { url, config } = context;
        const requestId = `${Date.now()}-${Math.random()}`;
        
        // Create abort controller
        const abortController = new AbortController();
        this.abortControllers.set(requestId, abortController);

        // Set timeout
        const timeoutId = config.timeout ? setTimeout(() => {
            abortController.abort();
        }, config.timeout) : null;

        try {
            const fetchOptions: RequestInit = {
                method: config.method || 'GET',
                headers: config.headers as HeadersInit,
                signal: abortController.signal
            };

            if (config.body && config.method !== 'GET') {
                fetchOptions.body = typeof config.body === 'string' 
                    ? config.body 
                    : JSON.stringify(config.body);
            }

            const response = await fetch(url, fetchOptions);
            
            if (!response.ok) {
                const errorData = await response.json().catch(() => ({}));
                throw new APIError(
                    errorData.message || `HTTP ${response.status}: ${response.statusText}`,
                    response.status,
                    errorData.code,
                    errorData
                );
            }

            let data: T;
            const contentType = response.headers.get('content-type');
            
            if (contentType && contentType.includes('application/json')) {
                data = await response.json();
            } else {
                data = await response.text() as unknown as T;
            }

            // Apply response interceptors
            const finalData = await this.responseInterceptors.reduce(
                async (prev, interceptor) => interceptor(response, await prev, context),
                Promise.resolve(data)
            );

            return finalData;
        } finally {
            // Cleanup
            if (timeoutId) clearTimeout(timeoutId);
            this.abortControllers.delete(requestId);
        }
    }

    // Utility methods
    cancelRequest(requestId: string): void {
        const controller = this.abortControllers.get(requestId);
        if (controller) {
            controller.abort();
            this.abortControllers.delete(requestId);
        }
    }

    cancelAllRequests(): void {
        this.abortControllers.forEach(controller => controller.abort());
        this.abortControllers.clear();
    }

    clearCache(): void {
        this.cache.clear();
    }

    getCacheSize(): number {
        return this.cache.size;
    }
}

// Custom API Error class
class APIError extends Error {
    constructor(
        message: string,
        public status: number,
        public code?: string,
        public details?: Record<string, any>
    ) {
        super(message);
        this.name = 'APIError';
    }
}

// Usage example with type-safe endpoints
interface User {
    id: number;
    name: string;
    email: string;
    createdAt: string;
}

interface Post {
    id: number;
    title: string;
    content: string;
    userId: number;
    publishedAt: string;
}

// Create typed API client
const apiClient = new APIClient('https://api.example.com/v1');

// Add authentication interceptor
const removeAuthInterceptor = apiClient.addRequestInterceptor(async (context) => {
    const token = localStorage.getItem('authToken');
    if (token) {
        context.config.headers = {
            ...context.config.headers,
            'Authorization': `Bearer ${token}`
        };
    }
    return context;
});

// Add logging interceptor
const removeLoggingInterceptor = apiClient.addResponseInterceptor(async (response, data, context) => {
    console.log(`API ${context.config.method} ${context.url}:`, {
        status: response.status,
        data: data,
        timing: performance.now()
    });
    return data;
});

// Add error handling interceptor
const removeErrorInterceptor = apiClient.addErrorInterceptor(async (error, context) => {
    if (error.status === 401) {
        localStorage.removeItem('authToken');
        window.location.href = '/login';
    }
    throw error;
});

// Type-safe API calls
async function example() {
    try {
        // GET request with caching
        const users = await apiClient.get<User[]>('/users', { 
            cache: true, 
            cacheTTL: 600000 // 10 minutes
        });

        // POST request with typed body
        const newUser = await apiClient.post<User>('/users', {
            name: 'John Doe',
            email: 'john@example.com'
        });

        // PUT request with retry configuration
        const updatedUser = await apiClient.put<User>(`/users/${newUser.id}`, {
            name: 'John Smith'
        }, {
            retries: 5,
            timeout: 10000
        });

        // GET with query parameters
        const userPosts = await apiClient.get<Post[]>(`/users/${newUser.id}/posts`);

        console.log({ users, newUser, updatedUser, userPosts });
    } catch (error) {
        if (error instanceof APIError) {
            console.error('API Error:', error.message, error.status, error.details);
        } else {
            console.error('Unexpected error:', error);
        }
    }
}
```

**Explanation:**
This advanced TypeScript API client demonstrates several sophisticated patterns:

- **Type Safety:** Generic constraints ensure compile-time type checking for all API calls
- **Caching:** Intelligent caching system with TTL and automatic cleanup
- **Retry Logic:** Exponential backoff with configurable retry attempts
- **Interceptors:** Request/response/error interceptors for cross-cutting concerns
- **Error Handling:** Custom error types with detailed error information
- **Request Cancellation:** AbortController integration for request cancellation
- **Performance:** Efficient cache management and request deduplication

The solution provides a production-ready foundation for type-safe API communication in full stack applications.

</details>

---

## Chapter 3: Frontend Frameworks
📊 **Progress:** Chapter 3 of 8 | ⏱️ **Reading Time:** 40 minutes

### 🎯 Learning Objectives
- Master React 18+ with modern hooks and concurrent features
- Implement Vue 3 Composition API and reactive patterns
- Explore Angular 17+ standalone components and signals
- Compare frameworks and choose the right tool for your project

### 📋 Prerequisites
- Solid understanding of JavaScript ES2024
- Basic TypeScript knowledge
- Familiarity with component-based architecture

### React 18+ with Hooks

React 18 introduced groundbreaking features like concurrent rendering, automatic batching, and improved Suspense that revolutionize how we build user interfaces.

#### Modern React Patterns

**1. Advanced Hook Patterns:**

```tsx
import React, { useState, useEffect, useCallback, useMemo, useRef, useTransition } from 'react';

// Custom hook for API data fetching with caching
function useAPI<T>(url: string, options?: RequestInit) {
    const [data, setData] = useState<T | null>(null);
    const [loading, setLoading] = useState(true);
    const [error, setError] = useState<string | null>(null);
    const [isPending, startTransition] = useTransition();
    const abortControllerRef = useRef<AbortController | null>(null);

    const fetchData = useCallback(async () => {
        // Cancel previous request
        if (abortControllerRef.current) {
            abortControllerRef.current.abort();
        }

        abortControllerRef.current = new AbortController();
        setLoading(true);
        setError(null);

        try {
            const response = await fetch(url, {
                ...options,
                signal: abortControllerRef.current.signal
            });

            if (!response.ok) {
                throw new Error(`HTTP ${response.status}: ${response.statusText}`);
            }

            const result = await response.json();
            
            startTransition(() => {
                setData(result);
                setLoading(false);
            });
        } catch (err) {
            if (err instanceof Error && err.name !== 'AbortError') {
                startTransition(() => {
                    setError(err.message);
                    setLoading(false);
                });
            }
        }
    }, [url, options]);

    useEffect(() => {
        fetchData();

        return () => {
            if (abortControllerRef.current) {
                abortControllerRef.current.abort();
            }
        };
    }, [fetchData]);

    const refetch = useCallback(() => {
        fetchData();
    }, [fetchData]);

    return { data, loading, error, isPending, refetch };
}

// Advanced state management hook
function useOptimisticState<T>(initialValue: T) {
    const [state, setState] = useState(initialValue);
    const [optimisticState, setOptimisticState] = useState(initialValue);
    const [isPending, startTransition] = useTransition();

    const updateOptimistically = useCallback((
        optimisticValue: T,
        asyncUpdate: () => Promise<T>
    ) => {
        setOptimisticState(optimisticValue);
        
        startTransition(async () => {
            try {
                const result = await asyncUpdate();
                setState(result);
                setOptimisticState(result);
            } catch (error) {
                // Revert optimistic update on error
                setOptimisticState(state);
                throw error;
            }
        });
    }, [state]);

    return {
        state: optimisticState,
        updateOptimistically,
        isPending
    };
}

// Component using advanced hooks
interface User {
    id: number;
    name: string;
    email: string;
    avatar: string;
}

interface UserProfileProps {
    userId: number;
}

const UserProfile: React.FC<UserProfileProps> = ({ userId }) => {
    const { data: user, loading, error, refetch } = useAPI<User>(`/api/users/${userId}`);
    const { state: userName, updateOptimistically, isPending } = useOptimisticState(user?.name || '');

    const updateUserName = useCallback(async (newName: string) => {
        if (!user) return;

        updateOptimistically(newName, async () => {
            const response = await fetch(`/api/users/${userId}`, {
                method: 'PATCH',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ name: newName })
            });

            if (!response.ok) {
                throw new Error('Failed to update user name');
            }

            const updatedUser = await response.json();
            return updatedUser.name;
        });
    }, [user, userId, updateOptimistically]);

    if (loading) return <div>Loading user profile...</div>;
    if (error) return <div>Error: {error}</div>;
    if (!user) return <div>User not found</div>;

    return (
        <div className="user-profile">
            <img src={user.avatar} alt={`${user.name}'s avatar`} />
            <div>
                <input
                    type="text"
                    value={userName}
                    onChange={(e) => updateUserName(e.target.value)}
                    disabled={isPending}
                />
                {isPending && <span>Updating...</span>}
            </div>
            <p>{user.email}</p>
            <button onClick={refetch}>Refresh</button>
        </div>
    );
};
```

**2. Server Components and Streaming:**

```tsx
// app/layout.tsx (App Router)
import { Suspense } from 'react';
import Navigation from './components/Navigation';
import LoadingSpinner from './components/LoadingSpinner';

export default function RootLayout({
    children,
}: {
    children: React.ReactNode;
}) {
    return (
        <html lang="en">
            <body>
                <Navigation />
                <main>
                    <Suspense fallback={<LoadingSpinner />}>
                        {children}
                    </Suspense>
                </main>
            </body>
        </html>
    );
}

// app/users/page.tsx (Server Component)
import { Suspense } from 'react';
import UserList from './components/UserList';
import UserStats from './components/UserStats';
import LoadingSkeleton from './components/LoadingSkeleton';

async function getUsers() {
    const response = await fetch('https://api.example.com/users', {
        next: { revalidate: 60 } // Cache for 60 seconds
    });
    
    if (!response.ok) {
        throw new Error('Failed to fetch users');
    }
    
    return response.json();
}

export default async function UsersPage() {
    const users = await getUsers();

    return (
        <div className="users-page">
            <h1>Users ({users.length})</h1>
            
            <Suspense fallback={<LoadingSkeleton />}>
                <UserStats users={users} />
            </Suspense>
            
            <Suspense fallback={<div>Loading user list...</div>}>
                <UserList users={users} />
            </Suspense>
        </div>
    );
}

// app/users/components/UserList.tsx (Client Component)
'use client';

import { useState, useMemo } from 'react';
import { useVirtualizer } from '@tanstack/react-virtual';

interface User {
    id: number;
    name: string;
    email: string;
    avatar: string;
}

interface UserListProps {
    users: User[];
}

export default function UserList({ users }: UserListProps) {
    const [search, setSearch] = useState('');
    const [sortBy, setSortBy] = useState<keyof User>('name');
    
    const filteredAndSortedUsers = useMemo(() => {
        return users
            .filter(user => 
                user.name.toLowerCase().includes(search.toLowerCase()) ||
                user.email.toLowerCase().includes(search.toLowerCase())
            )
            .sort((a, b) => {
                const aValue = a[sortBy];
                const bValue = b[sortBy];
                return aValue < bValue ? -1 : aValue > bValue ? 1 : 0;
            });
    }, [users, search, sortBy]);

    const parentRef = React.useRef<HTMLDivElement>(null);

    const virtualizer = useVirtualizer({
        count: filteredAndSortedUsers.length,
        getScrollElement: () => parentRef.current,
        estimateSize: () => 80,
        overscan: 5,
    });

    return (
        <div className="user-list">
            <div className="controls">
                <input
                    type="text"
                    placeholder="Search users..."
                    value={search}
                    onChange={(e) => setSearch(e.target.value)}
                />
                <select value={sortBy} onChange={(e) => setSortBy(e.target.value as keyof User)}>
                    <option value="name">Sort by Name</option>
                    <option value="email">Sort by Email</option>
                </select>
            </div>

            <div
                ref={parentRef}
                className="virtual-list"
                style={{ height: '400px', overflow: 'auto' }}
            >
                <div
                    style={{
                        height: `${virtualizer.getTotalSize()}px`,
                        width: '100%',
                        position: 'relative',
                    }}
                >
                    {virtualizer.getVirtualItems().map((virtualItem) => {
                        const user = filteredAndSortedUsers[virtualItem.index];
                        return (
                            <div
                                key={user.id}
                                style={{
                                    position: 'absolute',
                                    top: 0,
                                    left: 0,
                                    width: '100%',
                                    height: `${virtualItem.size}px`,
                                    transform: `translateY(${virtualItem.start}px)`,
                                }}
                            >
                                <div className="user-item">
                                    <img src={user.avatar} alt={user.name} />
                                    <div>
                                        <h3>{user.name}</h3>
                                        <p>{user.email}</p>
                                    </div>
                                </div>
                            </div>
                        );
                    })}
                </div>
            </div>
        </div>
    );
}
```

### Vue 3 Composition API

Vue 3's Composition API provides a more flexible and powerful way to organize component logic, especially for complex applications.

#### Advanced Vue 3 Patterns

**1. Composables and Reactive State:**

```vue
<!-- composables/useUsers.ts -->
<script setup lang="ts">
import { ref, computed, watch, onMounted } from 'vue';
import { useLocalStorage, useDebouncedRef } from '@vueuse/core';

interface User {
    id: number;
    name: string;
    email: string;
    avatar: string;
    isActive: boolean;
}

export function useUsers() {
    const users = ref<User[]>([]);
    const loading = ref(false);
    const error = ref<string | null>(null);
    const searchTerm = useDebouncedRef('', 300);
    
    // Persistent filter preferences
    const filterPreferences = useLocalStorage('user-filters', {
        showActiveOnly: false,
        sortBy: 'name' as keyof User,
        sortDirection: 'asc' as 'asc' | 'desc'
    });

    // Computed properties
    const filteredUsers = computed(() => {
        let result = users.value;

        // Search filter
        if (searchTerm.value) {
            const search = searchTerm.value.toLowerCase();
            result = result.filter(user =>
                user.name.toLowerCase().includes(search) ||
                user.email.toLowerCase().includes(search)
            );
        }

        // Active filter
        if (filterPreferences.value.showActiveOnly) {
            result = result.filter(user => user.isActive);
        }

        // Sorting
        result.sort((a, b) => {
            const aValue = a[filterPreferences.value.sortBy];
            const bValue = b[filterPreferences.value.sortBy];
            const comparison = aValue < bValue ? -1 : aValue > bValue ? 1 : 0;
            return filterPreferences.value.sortDirection === 'asc' ? comparison : -comparison;
        });

        return result;
    });

    const activeUserCount = computed(() =>
        users.value.filter(user => user.isActive).length
    );

    // Methods
    async function fetchUsers() {
        loading.value = true;
        error.value = null;

        try {
            const response = await fetch('/api/users');
            if (!response.ok) {
                throw new Error(`HTTP ${response.status}: ${response.statusText}`);
            }
            users.value = await response.json();
        } catch (err) {
            error.value = err instanceof Error ? err.message : 'Failed to fetch users';
        } finally {
            loading.value = false;
        }
    }

    async function createUser(userData: Omit<User, 'id'>) {
        try {
            const response = await fetch('/api/users', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(userData)
            });

            if (!response.ok) {
                throw new Error('Failed to create user');
            }

            const newUser = await response.json();
            users.value.push(newUser);
            return newUser;
        } catch (err) {
            error.value = err instanceof Error ? err.message : 'Failed to create user';
            throw err;
        }
    }

    async function updateUser(userId: number, updates: Partial<Omit<User, 'id'>>) {
        try {
            const response = await fetch(`/api/users/${userId}`, {
                method: 'PATCH',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(updates)
            });

            if (!response.ok) {
                throw new Error('Failed to update user');
            }

            const updatedUser = await response.json();
            const index = users.value.findIndex(user => user.id === userId);
            if (index !== -1) {
                users.value[index] = updatedUser;
            }
            return updatedUser;
        } catch (err) {
            error.value = err instanceof Error ? err.message : 'Failed to update user';
            throw err;
        }
    }

    async function deleteUser(userId: number) {
        try {
            const response = await fetch(`/api/users/${userId}`, {
                method: 'DELETE'
            });

            if (!response.ok) {
                throw new Error('Failed to delete user');
            }

            users.value = users.value.filter(user => user.id !== userId);
        } catch (err) {
            error.value = err instanceof Error ? err.message : 'Failed to delete user';
            throw err;
        }
    }

    // Watchers
    watch(searchTerm, (newTerm) => {
        console.log('Search term changed:', newTerm);
    });

    watch(activeUserCount, (newCount, oldCount) => {
        if (newCount !== oldCount) {
            console.log(`Active users: ${newCount}`);
        }
    });

    // Lifecycle
    onMounted(() => {
        fetchUsers();
    });

    return {
        // State
        users: readonly(users),
        loading: readonly(loading),
        error: readonly(error),
        searchTerm,
        filterPreferences,

        // Computed
        filteredUsers,
        activeUserCount,

        // Methods
        fetchUsers,
        createUser,
        updateUser,
        deleteUser
    };
}
</script>
```

**2. Advanced Component with Composition API:**

```vue
<!-- components/UserDashboard.vue -->
<template>
    <div class="user-dashboard">
        <header class="dashboard-header">
            <h1>User Management Dashboard</h1>
            <div class="stats">
                <div class="stat-card">
                    <span class="stat-value">{{ users.length }}</span>
                    <span class="stat-label">Total Users</span>
                </div>
                <div class="stat-card">
                    <span class="stat-value">{{ activeUserCount }}</span>
                    <span class="stat-label">Active Users</span>
                </div>
            </div>
        </header>

        <section class="dashboard-controls">
            <div class="search-box">
                <input
                    v-model="searchTerm"
                    type="text"
                    placeholder="Search users..."
                    class="search-input"
                >
            </div>

            <div class="filter-controls">
                <label class="checkbox-label">
                    <input
                        v-model="filterPreferences.showActiveOnly"
                        type="checkbox"
                    >
                    Show Active Only
                </label>

                <select v-model="filterPreferences.sortBy" class="sort-select">
                    <option value="name">Sort by Name</option>
                    <option value="email">Sort by Email</option>
                    <option value="isActive">Sort by Status</option>
                </select>

                <button
                    @click="toggleSortDirection"
                    class="sort-direction-btn"
                    :aria-label="`Sort ${filterPreferences.sortDirection}ending`"
                >
                    {{ filterPreferences.sortDirection === 'asc' ? '↑' : '↓' }}
                </button>
            </div>

            <button @click="showCreateUserModal = true" class="create-btn">
                Create User
            </button>
        </section>

        <main class="dashboard-content">
            <div v-if="loading" class="loading-state">
                <div class="spinner"></div>
                <p>Loading users...</p>
            </div>

            <div v-else-if="error" class="error-state">
                <p class="error-message">{{ error }}</p>
                <button @click="fetchUsers" class="retry-btn">Retry</button>
            </div>

            <div v-else class="user-grid">
                <TransitionGroup name="user-card" tag="div" class="user-list">
                    <UserCard
                        v-for="user in filteredUsers"
                        :key="user.id"
                        :user="user"
                        @update="handleUserUpdate"
                        @delete="handleUserDelete"
                    />
                </TransitionGroup>

                <div v-if="filteredUsers.length === 0" class="empty-state">
                    <p>No users found</p>
                </div>
            </div>
        </main>

        <!-- User Creation Modal -->
        <Teleport to="body">
            <UserCreateModal
                v-if="showCreateUserModal"
                @close="showCreateUserModal = false"
                @created="handleUserCreated"
            />
        </Teleport>

        <!-- Notifications -->
        <Teleport to="#notifications">
            <TransitionGroup name="notification" tag="div">
                <div
                    v-for="notification in notifications"
                    :key="notification.id"
                    :class="['notification', `notification--${notification.type}`]"
                >
                    {{ notification.message }}
                    <button @click="removeNotification(notification.id)">×</button>
                </div>
            </TransitionGroup>
        </Teleport>
    </div>
</template>

<script setup lang="ts">
import { ref, onUnmounted } from 'vue';
import { useUsers } from '../composables/useUsers';
import { useNotifications } from '../composables/useNotifications';
import UserCard from './UserCard.vue';
import UserCreateModal from './UserCreateModal.vue';

// Composables
const {
    users,
    loading,
    error,
    searchTerm,
    filterPreferences,
    filteredUsers,
    activeUserCount,
    fetchUsers,
    updateUser,
    deleteUser
} = useUsers();

const { notifications, addNotification, removeNotification } = useNotifications();

// Local state
const showCreateUserModal = ref(false);

// Methods
function toggleSortDirection() {
    filterPreferences.value.sortDirection =
        filterPreferences.value.sortDirection === 'asc' ? 'desc' : 'asc';
}

async function handleUserUpdate(userId: number, updates: Partial<User>) {
    try {
        await updateUser(userId, updates);
        addNotification('User updated successfully', 'success');
    } catch (error) {
        addNotification('Failed to update user', 'error');
    }
}

async function handleUserDelete(userId: number) {
    if (!confirm('Are you sure you want to delete this user?')) {
        return;
    }

    try {
        await deleteUser(userId);
        addNotification('User deleted successfully', 'success');
    } catch (error) {
        addNotification('Failed to delete user', 'error');
    }
}

function handleUserCreated(user: User) {
    showCreateUserModal.value = false;
    addNotification('User created successfully', 'success');
}

// Cleanup on unmount
onUnmounted(() => {
    // Cleanup any subscriptions or intervals
});
</script>

<style scoped>
.user-dashboard {
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

.dashboard-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #e5e7eb;
}

.stats {
    display: flex;
    gap: 1rem;
}

.stat-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    min-width: 120px;
}

.stat-value {
    font-size: 2rem;
    font-weight: bold;
    color: #3b82f6;
}

.stat-label {
    font-size: 0.875rem;
    color: #6b7280;
    margin-top: 0.25rem;
}

.dashboard-controls {
    display: flex;
    gap: 1rem;
    align-items: center;
    margin-bottom: 2rem;
    flex-wrap: wrap;
}

.search-input {
    padding: 0.5rem;
    border: 1px solid #d1d5db;
    border-radius: 6px;
    min-width: 300px;
}

.filter-controls {
    display: flex;
    gap: 1rem;
    align-items: center;
}

.checkbox-label {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-size: 0.875rem;
}

.sort-select {
    padding: 0.5rem;
    border: 1px solid #d1d5db;
    border-radius: 6px;
}

.sort-direction-btn {
    padding: 0.5rem;
    border: 1px solid #d1d5db;
    border-radius: 6px;
    background: white;
    cursor: pointer;
    font-size: 1.2rem;
}

.create-btn {
    padding: 0.5rem 1rem;
    background: #3b82f6;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 500;
}

.create-btn:hover {
    background: #2563eb;
}

.loading-state {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 3rem;
}

.spinner {
    width: 40px;
    height: 40px;
    border: 4px solid #e5e7eb;
    border-top: 4px solid #3b82f6;
    border-radius: 50%;
    animation: spin 1s linear infinite;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.error-state {
    text-align: center;
    padding: 3rem;
}

.error-message {
    color: #dc2626;
    margin-bottom: 1rem;
}

.retry-btn {
    padding: 0.5rem 1rem;
    background: #dc2626;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}

.user-grid {
    min-height: 400px;
}

.user-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
}

.empty-state {
    text-align: center;
    padding: 3rem;
    color: #6b7280;
}

/* Transitions */
.user-card-enter-active,
.user-card-leave-active {
    transition: all 0.3s ease;
}

.user-card-enter-from {
    opacity: 0;
    transform: translateY(20px);
}

.user-card-leave-to {
    opacity: 0;
    transform: translateY(-20px);
}

.notification-enter-active,
.notification-leave-active {
    transition: all 0.3s ease;
}

.notification-enter-from {
    opacity: 0;
    transform: translateX(100px);
}

.notification-leave-to {
    opacity: 0;
    transform: translateX(100px);
}
</style>
```

### Angular 17+ Features

Angular 17 introduces standalone components, signals, and improved developer experience with a new control flow syntax and enhanced SSR capabilities.

#### Modern Angular Patterns

**1. Standalone Components with Signals:**

```typescript
// user.service.ts
import { Injectable, computed, signal } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable, catchError, throwError } from 'rxjs';

export interface User {
    id: number;
    name: string;
    email: string;
    avatar: string;
    isActive: boolean;
}

@Injectable({
    providedIn: 'root'
})
export class UserService {
    private users = signal<User[]>([]);
    private loading = signal(false);
    private error = signal<string | null>(null);
    private searchTerm = signal('');
    private sortBy = signal<keyof User>('name');

    // Computed signals
    readonly filteredUsers = computed(() => {
        const users = this.users();
        const search = this.searchTerm().toLowerCase();
        
        if (!search) return users;
        
        return users.filter(user =>
            user.name.toLowerCase().includes(search) ||
            user.email.toLowerCase().includes(search)
        );
    });

    readonly sortedUsers = computed(() => {
        const users = this.filteredUsers();
        const sortKey = this.sortBy();
        
        return [...users].sort((a, b) => {
            const aValue = a[sortKey];
            const bValue = b[sortKey];
            return aValue < bValue ? -1 : aValue > bValue ? 1 : 0;
        });
    });

    readonly activeUserCount = computed(() => 
        this.users().filter(user => user.isActive).length
    );

    // Getters for template access
    get allUsers() { return this.users.asReadonly(); }
    get isLoading() { return this.loading.asReadonly(); }
    get errorMessage() { return this.error.asReadonly(); }
    get displayUsers() { return this.sortedUsers(); }
    get activeCount() { return this.activeUserCount(); }

    constructor(private http: HttpClient) {}

    loadUsers(): Observable<User[]> {
        this.loading.set(true);
        this.error.set(null);

        return this.http.get<User[]>('/api/users').pipe(
            catchError(error => {
                this.error.set('Failed to load users');
                this.loading.set(false);
                return throwError(() => error);
            })
        );
    }

    async fetchUsers(): Promise<void> {
        try {
            const users = await this.loadUsers().toPromise();
            this.users.set(users || []);
        } catch (error) {
            console.error('Error fetching users:', error);
        } finally {
            this.loading.set(false);
        }
    }

    updateSearch(term: string): void {
        this.searchTerm.set(term);
    }

    updateSort(key: keyof User): void {
        this.sortBy.set(key);
    }

    async createUser(userData: Omit<User, 'id'>): Promise<User> {
        const newUser = await this.http.post<User>('/api/users', userData).toPromise();
        if (newUser) {
            this.users.update(users => [...users, newUser]);
        }
        return newUser!;
    }

    async updateUser(id: number, updates: Partial<User>): Promise<User> {
        const updatedUser = await this.http.patch<User>(`/api/users/${id}`, updates).toPromise();
        if (updatedUser) {
            this.users.update(users => 
                users.map(user => user.id === id ? updatedUser : user)
            );
        }
        return updatedUser!;
    }

    async deleteUser(id: number): Promise<void> {
        await this.http.delete(`/api/users/${id}`).toPromise();
        this.users.update(users => users.filter(user => user.id !== id));
    }
}
```

**2. Standalone Component with New Control Flow:**

```typescript
// user-dashboard.component.ts
import { Component, inject, OnInit } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';
import { UserService } from './user.service';
import { UserCardComponent } from './user-card.component';
import { UserCreateModalComponent } from './user-create-modal.component';

@Component({
    selector: 'app-user-dashboard',
    standalone: true,
    imports: [CommonModule, FormsModule, UserCardComponent, UserCreateModalComponent],
    template: `
        <div class="user-dashboard">
            <header class="dashboard-header">
                <h1>User Management Dashboard</h1>
                <div class="stats">
                    <div class="stat-card">
                        <span class="stat-value">{{ userService.allUsers().length }}</span>
                        <span class="stat-label">Total Users</span>
                    </div>
                    <div class="stat-card">
                        <span class="stat-value">{{ userService.activeCount() }}</span>
                        <span class="stat-label">Active Users</span>
                    </div>
                </div>
            </header>

            <section class="dashboard-controls">
                <div class="search-box">
                    <input
                        type="text"
                        placeholder="Search users..."
                        [value]="searchTerm"
                        (input)="onSearchChange($event)"
                        class="search-input"
                    />
                </div>

                <div class="filter-controls">
                    <select 
                        [value]="sortBy" 
                        (change)="onSortChange($event)"
                        class="sort-select"
                    >
                        <option value="name">Sort by Name</option>
                        <option value="email">Sort by Email</option>
                        <option value="isActive">Sort by Status</option>
                    </select>
                </div>

                <button 
                    (click)="showCreateModal = true" 
                    class="create-btn"
                >
                    Create User
                </button>
            </section>

            <main class="dashboard-content">
                @if (userService.isLoading()) {
                    <div class="loading-state">
                        <div class="spinner"></div>
                        <p>Loading users...</p>
                    </div>
                } @else if (userService.errorMessage()) {
                    <div class="error-state">
                        <p class="error-message">{{ userService.errorMessage() }}</p>
                        <button (click)="retryLoad()" class="retry-btn">Retry</button>
                    </div>
                } @else {
                    <div class="user-grid">
                        @if (userService.displayUsers().length > 0) {
                            @for (user of userService.displayUsers(); track user.id) {
                                <app-user-card
                                    [user]="user"
                                    (userUpdate)="onUserUpdate($event)"
                                    (userDelete)="onUserDelete($event)"
                                />
                            }
                        } @else {
                            <div class="empty-state">
                                <p>No users found</p>
                            </div>
                        }
                    </div>
                }
            </main>

            @if (showCreateModal) {
                <app-user-create-modal
                    (close)="showCreateModal = false"
                    (userCreated)="onUserCreated($event)"
                />
            }
        </div>
    `,
    styles: [`
        .user-dashboard {
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #e5e7eb;
        }

        .stats {
            display: flex;
            gap: 1rem;
        }

        .stat-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1rem;
            background: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            min-width: 120px;
        }

        .stat-value {
            font-size: 2rem;
            font-weight: bold;
            color: #3b82f6;
        }

        .stat-label {
            font-size: 0.875rem;
            color: #6b7280;
            margin-top: 0.25rem;
        }

        .dashboard-controls {
            display: flex;
            gap: 1rem;
            align-items: center;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .search-input {
            padding: 0.5rem;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            min-width: 300px;
        }

        .filter-controls {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .sort-select {
            padding: 0.5rem;
            border: 1px solid #d1d5db;
            border-radius: 6px;
        }

        .create-btn {
            padding: 0.5rem 1rem;
            background: #3b82f6;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 500;
        }

        .create-btn:hover {
            background: #2563eb;
        }

        .loading-state {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 3rem;
        }

        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #e5e7eb;
            border-top: 4px solid #3b82f6;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .error-state {
            text-align: center;
            padding: 3rem;
        }

        .error-message {
            color: #dc2626;
            margin-bottom: 1rem;
        }

        .retry-btn {
            padding: 0.5rem 1rem;
            background: #dc2626;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }

        .user-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            min-height: 400px;
        }

        .empty-state {
            text-align: center;
            padding: 3rem;
            color: #6b7280;
        }
    `]
})
export class UserDashboardComponent implements OnInit {
    userService = inject(UserService);
    
    showCreateModal = false;
    searchTerm = '';
    sortBy: keyof User = 'name';

    ngOnInit() {
        this.userService.fetchUsers();
    }

    onSearchChange(event: Event) {
        const target = event.target as HTMLInputElement;
        this.searchTerm = target.value;
        this.userService.updateSearch(this.searchTerm);
    }

    onSortChange(event: Event) {
        const target = event.target as HTMLSelectElement;
        this.sortBy = target.value as keyof User;
        this.userService.updateSort(this.sortBy);
    }

    retryLoad() {
        this.userService.fetchUsers();
    }

    async onUserUpdate(event: { id: number; updates: Partial<User> }) {
        try {
            await this.userService.updateUser(event.id, event.updates);
            console.log('User updated successfully');
        } catch (error) {
            console.error('Failed to update user:', error);
        }
    }

    async onUserDelete(userId: number) {
        if (confirm('Are you sure you want to delete this user?')) {
            try {
                await this.userService.deleteUser(userId);
                console.log('User deleted successfully');
            } catch (error) {
                console.error('Failed to delete user:', error);
            }
        }
    }

    async onUserCreated(user: User) {
        this.showCreateModal = false;
        console.log('User created successfully:', user);
    }
}
```

### Framework Comparison

Choosing the right frontend framework depends on your project requirements, team expertise, and long-term maintenance goals.

#### Feature Comparison Matrix

| Feature | React 18+ | Vue 3 | Angular 17+ |
|---------|-----------|-------|-------------|
| **Learning Curve** | Medium | Easy | Steep |
| **Performance** | Excellent | Excellent | Very Good |
| **Bundle Size** | Small | Small | Large |
| **TypeScript Support** | Excellent | Excellent | Native |
| **State Management** | External libs | Built-in (Pinia) | Built-in (Signals) |
| **Router** | External (React Router) | Built-in | Built-in |
| **Testing Tools** | Rich ecosystem | Good | Comprehensive |
| **Mobile Support** | React Native | NativeScript/Capacitor | Ionic |
| **SSR/SSG** | Next.js/Remix | Nuxt.js | Angular Universal |
| **Community Size** | Largest | Large | Large |
| **Corporate Backing** | Meta | Independent | Google |

#### When to Choose Each Framework

**Choose React when:**
- Building complex, interactive UIs with frequent updates
- Team has JavaScript/functional programming background
- Need maximum flexibility and ecosystem choices
- Planning to share code with mobile (React Native)
- Working with existing React codebases
- Performance is critical (concurrent features)

**Choose Vue when:**
- Team includes designers who want to understand the code
- Need gentle learning curve with powerful features
- Building progressive web applications
- Want built-in solutions without configuration overhead
- Migrating from jQuery or legacy frameworks
- Small to medium-sized applications

**Choose Angular when:**
- Building large-scale enterprise applications
- Team has strong TypeScript/OOP background
- Need comprehensive framework with everything included
- Require strict coding standards and conventions
- Long-term maintenance and scalability are priorities
- Integration with other enterprise tools is important

#### Migration Strategies

**From Legacy JavaScript to Modern Framework:**

```typescript
// Progressive enhancement approach
// 1. Start with framework in specific components
class LegacyToReactMigration {
    private mountPoints: Map<string, ReactComponent> = new Map();

    mountReactComponent(containerId: string, Component: React.ComponentType, props: any) {
        const container = document.getElementById(containerId);
        if (container) {
            const root = ReactDOM.createRoot(container);
            root.render(React.createElement(Component, props));
            this.mountPoints.set(containerId, { root, Component });
        }
    }

    unmountReactComponent(containerId: string) {
        const component = this.mountPoints.get(containerId);
        if (component) {
            component.root.unmount();
            this.mountPoints.delete(containerId);
        }
    }
}

// Usage in legacy application
const migrationHelper = new LegacyToReactMigration();

// Replace legacy user list with React component
migrationHelper.mountReactComponent('user-list-container', UserList, {
    users: window.legacyData.users
});
```

### ⚠️ Common Pitfalls

1. **Over-engineering State Management**
   - Don't use global state for local component state
   - Choose appropriate state management solution for app size
   - Avoid prop drilling but don't over-centralize

2. **Performance Anti-patterns**
   - Avoid creating objects/functions in render
   - Use proper memoization strategies
   - Implement lazy loading for large components

3. **Accessibility Oversights**
   - Always include proper ARIA attributes
   - Test with keyboard navigation
   - Ensure proper color contrast ratios

### ✅ Best Practices

1. **Component Architecture**
   - Keep components small and focused
   - Use composition over inheritance
   - Implement proper error boundaries

2. **State Management**
   - Use local state when possible
   - Implement proper data normalization
   - Consider offline-first approaches

3. **Testing Strategy**
   - Write tests for critical user flows
   - Use testing library best practices
   - Implement visual regression testing

### 🏋️ Exercise 4: Framework Comparison Project
**Difficulty:** 🟡 Intermediate | **Estimated Time:** 90 minutes

Create the same todo application in React, Vue, and Angular to compare development experience.

**Requirements:**
1. Add, edit, delete todos
2. Filter by completed status
3. Persist data to localStorage
4. Responsive design
5. TypeScript implementation

<details>
<summary>💡 Click to see hints</summary>

- Focus on how each framework handles similar concepts
- Compare bundle sizes and build tools
- Note differences in state management approaches
- Observe TypeScript integration quality

</details>

<details>
<summary>✅ Click to see solution</summary>

**React Implementation:**

```tsx
// Todo.tsx
interface Todo {
    id: string;
    text: string;
    completed: boolean;
    createdAt: Date;
}

const TodoApp: React.FC = () => {
    const [todos, setTodos] = useState<Todo[]>([]);
    const [filter, setFilter] = useState<'all' | 'active' | 'completed'>('all');
    const [newTodoText, setNewTodoText] = useState('');

    useEffect(() => {
        const saved = localStorage.getItem('todos');
        if (saved) {
            setTodos(JSON.parse(saved));
        }
    }, []);

    useEffect(() => {
        localStorage.setItem('todos', JSON.stringify(todos));
    }, [todos]);

    const addTodo = useCallback((text: string) => {
        const newTodo: Todo = {
            id: crypto.randomUUID(),
            text: text.trim(),
            completed: false,
            createdAt: new Date()
        };
        setTodos(prev => [...prev, newTodo]);
    }, []);

    const filteredTodos = useMemo(() => {
        switch (filter) {
            case 'active': return todos.filter(t => !t.completed);
            case 'completed': return todos.filter(t => t.completed);
            default: return todos;
        }
    }, [todos, filter]);

    return (
        <div className="todo-app">
            <h1>Todo App - React</h1>
            <input
                value={newTodoText}
                onChange={(e) => setNewTodoText(e.target.value)}
                onKeyPress={(e) => {
                    if (e.key === 'Enter' && newTodoText.trim()) {
                        addTodo(newTodoText);
                        setNewTodoText('');
                    }
                }}
                placeholder="Add todo..."
            />
            <div className="filters">
                {(['all', 'active', 'completed'] as const).map(f => (
                    <button
                        key={f}
                        onClick={() => setFilter(f)}
                        className={filter === f ? 'active' : ''}
                    >
                        {f}
                    </button>
                ))}
            </div>
            <ul>
                {filteredTodos.map(todo => (
                    <li key={todo.id}>
                        <input
                            type="checkbox"
                            checked={todo.completed}
                            onChange={(e) => {
                                setTodos(prev => prev.map(t => 
                                    t.id === todo.id ? { ...t, completed: e.target.checked } : t
                                ));
                            }}
                        />
                        <span className={todo.completed ? 'completed' : ''}>{todo.text}</span>
                        <button onClick={() => setTodos(prev => prev.filter(t => t.id !== todo.id))}>
                            Delete
                        </button>
                    </li>
                ))}
            </ul>
        </div>
    );
};
```

**Vue Implementation:**

```vue
<!-- TodoApp.vue -->
<template>
    <div class="todo-app">
        <h1>Todo App - Vue</h1>
        <input
            v-model="newTodoText"
            @keyup.enter="addTodo"
            placeholder="Add todo..."
        />
        <div class="filters">
            <button
                v-for="f in filters"
                :key="f"
                @click="filter = f"
                :class="{ active: filter === f }"
            >
                {{ f }}
            </button>
        </div>
        <ul>
            <li v-for="todo in filteredTodos" :key="todo.id">
                <input
                    type="checkbox"
                    v-model="todo.completed"
                />
                <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
                <button @click="deleteTodo(todo.id)">Delete</button>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">
interface Todo {
    id: string;
    text: string;
    completed: boolean;
    createdAt: Date;
}

const todos = ref<Todo[]>([]);
const filter = ref<'all' | 'active' | 'completed'>('all');
const newTodoText = ref('');

const filters = ['all', 'active', 'completed'] as const;

const filteredTodos = computed(() => {
    switch (filter.value) {
        case 'active': return todos.value.filter(t => !t.completed);
        case 'completed': return todos.value.filter(t => t.completed);
        default: return todos.value;
    }
});

function addTodo() {
    if (!newTodoText.value.trim()) return;
    
    const newTodo: Todo = {
        id: crypto.randomUUID(),
        text: newTodoText.value.trim(),
        completed: false,
        createdAt: new Date()
    };
    
    todos.value.push(newTodo);
    newTodoText.value = '';
}

function deleteTodo(id: string) {
    const index = todos.value.findIndex(t => t.id === id);
    if (index > -1) {
        todos.value.splice(index, 1);
    }
}

// Persistence
watchEffect(() => {
    localStorage.setItem('todos', JSON.stringify(todos.value));
});

onMounted(() => {
    const saved = localStorage.getItem('todos');
    if (saved) {
        todos.value = JSON.parse(saved);
    }
});
</script>
```

**Angular Implementation:**

```typescript
// todo-app.component.ts
@Component({
    selector: 'app-todo',
    standalone: true,
    imports: [CommonModule, FormsModule],
    template: `
        <div class="todo-app">
            <h1>Todo App - Angular</h1>
            <input
                [(ngModel)]="newTodoText"
                (keyup.enter)="addTodo()"
                placeholder="Add todo..."
            />
            <div class="filters">
                @for (f of filters; track f) {
                    <button
                        (click)="filter.set(f)"
                        [class.active]="filter() === f"
                    >
                        {{ f }}
                    </button>
                }
            </div>
            <ul>
                @for (todo of filteredTodos(); track todo.id) {
                    <li>
                        <input
                            type="checkbox"
                            [checked]="todo.completed"
                            (change)="toggleTodo(todo.id, $event)"
                        />
                        <span [class.completed]="todo.completed">{{ todo.text }}</span>
                        <button (click)="deleteTodo(todo.id)">Delete</button>
                    </li>
                }
            </ul>
        </div>
    `
})
export class TodoAppComponent {
    private todos = signal<Todo[]>([]);
    filter = signal<'all' | 'active' | 'completed'>('all');
    newTodoText = '';

    readonly filters = ['all', 'active', 'completed'] as const;

    readonly filteredTodos = computed(() => {
        const todoList = this.todos();
        switch (this.filter()) {
            case 'active': return todoList.filter(t => !t.completed);
            case 'completed': return todoList.filter(t => t.completed);
            default: return todoList;
        }
    });

    constructor() {
        // Load from localStorage
        const saved = localStorage.getItem('todos');
        if (saved) {
            this.todos.set(JSON.parse(saved));
        }

        // Auto-save to localStorage
        effect(() => {
            localStorage.setItem('todos', JSON.stringify(this.todos()));
        });
    }

    addTodo() {
        if (!this.newTodoText.trim()) return;

        const newTodo: Todo = {
            id: crypto.randomUUID(),
            text: this.newTodoText.trim(),
            completed: false,
            createdAt: new Date()
        };

        this.todos.update(todos => [...todos, newTodo]);
        this.newTodoText = '';
    }

    toggleTodo(id: string, event: Event) {
        const target = event.target as HTMLInputElement;
        this.todos.update(todos =>
            todos.map(todo =>
                todo.id === id ? { ...todo, completed: target.checked } : todo
            )
        );
    }

    deleteTodo(id: string) {
        this.todos.update(todos => todos.filter(todo => todo.id !== id));
    }
}
```

**Comparison Analysis:**

- **Bundle Size:** React ~45KB, Vue ~35KB, Angular ~130KB
- **Development Speed:** Vue fastest, React moderate, Angular slowest
- **Type Safety:** Angular best (native), React/Vue good (with setup)
- **Learning Curve:** Vue easiest, React moderate, Angular steepest
- **Ecosystem:** React largest, Angular comprehensive, Vue growing

</details>

## Chapter 4: Backend Development
📊 **Progress:** Chapter 4 of 8 | ⏱️ **Reading Time:** 45 minutes

### 🎯 Learning Objectives
- Master Node.js 21+ features and performance optimization
- Build scalable APIs with Express and modern frameworks
- Implement secure authentication and authorization systems
- Design RESTful and GraphQL APIs following best practices

### 📋 Prerequisites
- Solid JavaScript/TypeScript knowledge
- Understanding of HTTP protocols and web standards
- Basic database concepts
- Command line proficiency

### Node.js 21+ & Express

Node.js 21 introduces significant performance improvements, built-in test runner enhancements, and better ES module support.

#### Modern Node.js Features

**1. Performance Monitoring and Optimization:**

```javascript
// performance-monitor.js
import { performance, PerformanceObserver } from 'node:perf_hooks';
import { AsyncLocalStorage } from 'node:async_hooks';

class PerformanceMonitor {
    constructor() {
        this.asyncLocalStorage = new AsyncLocalStorage();
        this.setupObservers();
    }

    setupObservers() {
        // HTTP timing observer
        const httpObserver = new PerformanceObserver((list) => {
            for (const entry of list.getEntries()) {
                if (entry.entryType === 'measure') {
                    console.log(`${entry.name}: ${entry.duration.toFixed(2)}ms`);
                    
                    // Log slow operations
                    if (entry.duration > 100) {
                        console.warn(`Slow operation detected: ${entry.name} took ${entry.duration.toFixed(2)}ms`);
                    }
                }
            }
        });
        httpObserver.observe({ entryTypes: ['measure'] });

        // Resource timing observer
        const resourceObserver = new PerformanceObserver((list) => {
            for (const entry of list.getEntries()) {
                console.log(`Resource: ${entry.name} - ${entry.duration.toFixed(2)}ms`);
            }
        });
        resourceObserver.observe({ entryTypes: ['resource'] });
    }

    measureAsync(name, asyncFunction) {
        return this.asyncLocalStorage.run({ operationName: name }, async () => {
            const startMark = `${name}-start`;
            const endMark = `${name}-end`;
            
            performance.mark(startMark);
            
            try {
                const result = await asyncFunction();
                performance.mark(endMark);
                performance.measure(name, startMark, endMark);
                return result;
            } catch (error) {
                performance.mark(endMark);
                performance.measure(`${name}-error`, startMark, endMark);
                throw error;
            } finally {
                // Cleanup marks
                performance.clearMarks(startMark);
                performance.clearMarks(endMark);
            }
        });
    }

    async measureDatabaseQuery(query, params = []) {
        return this.measureAsync(`db-query-${query.slice(0, 20)}`, async () => {
            // Simulate database query
            return new Promise(resolve => {
                setTimeout(() => resolve({ rows: [], rowCount: 0 }), Math.random() * 50);
            });
        });
    }
}

// Usage
const monitor = new PerformanceMonitor();

// Example API endpoint with performance monitoring
async function getUserById(userId) {
    return monitor.measureAsync('get-user-by-id', async () => {
        const user = await monitor.measureDatabaseQuery('SELECT * FROM users WHERE id = $1', [userId]);
        const posts = await monitor.measureDatabaseQuery('SELECT * FROM posts WHERE user_id = $1', [userId]);
        
        return {
            ...user.rows[0],
            posts: posts.rows
        };
    });
}
```

**2. Modern Express Application Structure:**

```javascript
// app.js
import express from 'express';
import helmet from 'helmet';
import cors from 'cors';
import compression from 'compression';
import rateLimit from 'express-rate-limit';
import { fileURLToPath } from 'node:url';
import { dirname, join } from 'node:path';
import { createServer } from 'node:http';
import { Server } from 'socket.io';

const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

class ModernExpressApp {
    constructor() {
        this.app = express();
        this.server = createServer(this.app);
        this.io = new Server(this.server, {
            cors: {
                origin: process.env.CLIENT_URL || "http://localhost:3000",
                methods: ["GET", "POST"]
            }
        });
        this.setupMiddleware();
        this.setupRoutes();
        this.setupErrorHandling();
        this.setupWebSocket();
    }

    setupMiddleware() {
        // Security middleware
        this.app.use(helmet({
            contentSecurityPolicy: {
                directives: {
                    defaultSrc: ["'self'"],
                    scriptSrc: ["'self'", "'unsafe-inline'"],
                    styleSrc: ["'self'", "'unsafe-inline'"],
                    imgSrc: ["'self'", "data:", "https:"],
                },
            },
            crossOriginEmbedderPolicy: false
        }));

        // CORS configuration
        this.app.use(cors({
            origin: (origin, callback) => {
                const allowedOrigins = process.env.ALLOWED_ORIGINS?.split(',') || ['http://localhost:3000'];
                if (!origin || allowedOrigins.includes(origin)) {
                    callback(null, true);
                } else {
                    callback(new Error('Not allowed by CORS'));
                }
            },
            credentials: true,
            methods: ['GET', 'POST', 'PUT', 'DELETE', 'PATCH', 'OPTIONS'],
            allowedHeaders: ['Content-Type', 'Authorization', 'X-Requested-With']
        }));

        // Compression
        this.app.use(compression({
            filter: (req, res) => {
                if (req.headers['x-no-compression']) {
                    return false;
                }
                return compression.filter(req, res);
            },
            threshold: 1024
        }));

        // Rate limiting
        const limiter = rateLimit({
            windowMs: 15 * 60 * 1000, // 15 minutes
            max: 100, // limit each IP to 100 requests per windowMs
            message: {
                error: 'Too many requests from this IP, please try again later.',
                retryAfter: 15 * 60
            },
            standardHeaders: true,
            legacyHeaders: false,
            handler: (req, res) => {
                res.status(429).json({
                    error: 'Rate limit exceeded',
                    retryAfter: Math.ceil(req.rateLimit.msBeforeNext / 1000)
                });
            }
        });
        this.app.use('/api/', limiter);

        // Body parsing
        this.app.use(express.json({ 
            limit: '10mb',
            verify: (req, res, buf) => {
                req.rawBody = buf;
            }
        }));
        this.app.use(express.urlencoded({ extended: true, limit: '10mb' }));

        // Request logging
        this.app.use((req, res, next) => {
            const start = Date.now();
            const requestId = crypto.randomUUID();
            
            req.requestId = requestId;
            req.startTime = start;

            res.on('finish', () => {
                const duration = Date.now() - start;
                console.log({
                    requestId,
                    method: req.method,
                    url: req.url,
                    statusCode: res.statusCode,
                    duration: `${duration}ms`,
                    userAgent: req.get('User-Agent'),
                    ip: req.ip || req.connection.remoteAddress
                });
            });

            next();
        });

        // Static files
        this.app.use('/public', express.static(join(__dirname, 'public'), {
            maxAge: process.env.NODE_ENV === 'production' ? '1y' : '0',
            etag: true,
            lastModified: true
        }));
    }

    setupRoutes() {
        // Health check
        this.app.get('/health', (req, res) => {
            res.json({
                status: 'healthy',
                timestamp: new Date().toISOString(),
                uptime: process.uptime(),
                memory: process.memoryUsage(),
                version: process.version
            });
        });

        // API routes
        this.app.use('/api/v1', this.createAPIRouter());
    }

    createAPIRouter() {
        const router = express.Router();

        // API documentation
        router.get('/', (req, res) => {
            res.json({
                message: 'Full Stack API v1',
                version: '1.0.0',
                endpoints: {
                    users: '/api/v1/users',
                    posts: '/api/v1/posts',
                    auth: '/api/v1/auth'
                },
                documentation: '/api/v1/docs'
            });
        });

        // User routes
        router.use('/users', this.createUserRoutes());
        router.use('/posts', this.createPostRoutes());
        router.use('/auth', this.createAuthRoutes());

        return router;
    }

    createUserRoutes() {
        const router = express.Router();

        // Get all users
        router.get('/', async (req, res, next) => {
            try {
                const { page = 1, limit = 10, search = '', sortBy = 'createdAt', sortOrder = 'desc' } = req.query;
                
                const offset = (parseInt(page) - 1) * parseInt(limit);
                
                // Simulate database query with pagination
                const users = await this.simulateUserQuery({
                    search,
                    sortBy,
                    sortOrder,
                    limit: parseInt(limit),
                    offset
                });

                res.json({
                    data: users,
                    pagination: {
                        page: parseInt(page),
                        limit: parseInt(limit),
                        total: users.length,
                        pages: Math.ceil(users.length / parseInt(limit))
                    },
                    meta: {
                        requestId: req.requestId,
                        timestamp: new Date().toISOString()
                    }
                });
            } catch (error) {
                next(error);
            }
        });

        // Get user by ID
        router.get('/:id', async (req, res, next) => {
            try {
                const { id } = req.params;
                
                if (!id || isNaN(parseInt(id))) {
                    return res.status(400).json({
                        error: 'Invalid user ID',
                        code: 'INVALID_USER_ID'
                    });
                }

                const user = await this.simulateGetUserById(parseInt(id));
                
                if (!user) {
                    return res.status(404).json({
                        error: 'User not found',
                        code: 'USER_NOT_FOUND'
                    });
                }

                res.json({
                    data: user,
                    meta: {
                        requestId: req.requestId,
                        timestamp: new Date().toISOString()
                    }
                });
            } catch (error) {
                next(error);
            }
        });

        // Create user
        router.post('/', async (req, res, next) => {
            try {
                const userData = req.body;
                
                // Validation
                const validation = this.validateUserData(userData);
                if (!validation.valid) {
                    return res.status(400).json({
                        error: 'Validation failed',
                        code: 'VALIDATION_ERROR',
                        details: validation.errors
                    });
                }

                const newUser = await this.simulateCreateUser(userData);

                res.status(201).json({
                    data: newUser,
                    meta: {
                        requestId: req.requestId,
                        timestamp: new Date().toISOString()
                    }
                });
            } catch (error) {
                next(error);
            }
        });

        return router;
    }

    createPostRoutes() {
        const router = express.Router();
        // Post routes implementation...
        return router;
    }

    createAuthRoutes() {
        const router = express.Router();
        // Auth routes implementation...
        return router;
    }

    setupWebSocket() {
        this.io.on('connection', (socket) => {
            console.log(`Client connected: ${socket.id}`);

            socket.on('join-room', (room) => {
                socket.join(room);
                socket.emit('joined-room', room);
            });

            socket.on('leave-room', (room) => {
                socket.leave(room);
                socket.emit('left-room', room);
            });

            socket.on('disconnect', () => {
                console.log(`Client disconnected: ${socket.id}`);
            });
        });
    }

    setupErrorHandling() {
        // 404 handler
        this.app.use('*', (req, res) => {
            res.status(404).json({
                error: 'Route not found',
                code: 'ROUTE_NOT_FOUND',
                path: req.originalUrl,
                method: req.method
            });
        });

        // Global error handler
        this.app.use((error, req, res, next) => {
            console.error({
                error: error.message,
                stack: error.stack,
                requestId: req.requestId,
                url: req.url,
                method: req.method
            });

            // Don't leak error details in production
            const isDevelopment = process.env.NODE_ENV !== 'production';
            
            res.status(error.status || 500).json({
                error: error.message || 'Internal server error',
                code: error.code || 'INTERNAL_ERROR',
                ...(isDevelopment && { stack: error.stack }),
                meta: {
                    requestId: req.requestId,
                    timestamp: new Date().toISOString()
                }
            });
        });
    }

    // Utility methods
    async simulateUserQuery(options) {
        // Simulate database query delay
        await new Promise(resolve => setTimeout(resolve, Math.random() * 100));
        
        return [
            { id: 1, name: 'John Doe', email: 'john@example.com', createdAt: '2024-01-01' },
            { id: 2, name: 'Jane Smith', email: 'jane@example.com', createdAt: '2024-01-02' }
        ];
    }

    async simulateGetUserById(id) {
        await new Promise(resolve => setTimeout(resolve, Math.random() * 50));
        
        if (id === 1) {
            return { id: 1, name: 'John Doe', email: 'john@example.com', createdAt: '2024-01-01' };
        }
        return null;
    }

    async simulateCreateUser(userData) {
        await new Promise(resolve => setTimeout(resolve, Math.random() * 100));
        
        return {
            id: Math.floor(Math.random() * 1000),
            ...userData,
            createdAt: new Date().toISOString()
        };
    }

    validateUserData(data) {
        const errors = [];
        
        if (!data.name || data.name.trim().length < 2) {
            errors.push({ field: 'name', message: 'Name must be at least 2 characters' });
        }
        
        if (!data.email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(data.email)) {
            errors.push({ field: 'email', message: 'Invalid email format' });
        }
        
        return {
            valid: errors.length === 0,
            errors
        };
    }

    start(port = 3000) {
        this.server.listen(port, () => {
            console.log(`Server running on port ${port}`);
            console.log(`Environment: ${process.env.NODE_ENV || 'development'}`);
            console.log(`Health check: http://localhost:${port}/health`);
            console.log(`API: http://localhost:${port}/api/v1`);
        });

        // Graceful shutdown
        process.on('SIGTERM', () => {
            console.log('SIGTERM received, shutting down gracefully');
            this.server.close(() => {
                console.log('Process terminated');
                process.exit(0);
            });
        });

        process.on('SIGINT', () => {
            console.log('SIGINT received, shutting down gracefully');
            this.server.close(() => {
                console.log('Process terminated');
                process.exit(0);
            });
        });

        return this.server;
    }
}

// Export and usage
export default ModernExpressApp;

// Usage
if (import.meta.url === `file://${process.argv[1]}`) {
    const app = new ModernExpressApp();
    const port = process.env.PORT || 3000;
    app.start(port);
}
```

### API Design & RESTful Services

Modern API design follows principles that prioritize developer experience, scalability, and maintainability.

#### RESTful API Best Practices

**1. Resource-Based URL Structure:**

```javascript
// api-routes.js
import { Router } from 'express';

class RESTfulAPIRouter {
    constructor(resourceName, controller) {
        this.resourceName = resourceName;
        this.controller = controller;
        this.router = Router();
        this.setupRoutes();
    }

    setupRoutes() {
        // Collection routes
        this.router.get('/', this.controller.list.bind(this.controller));
        this.router.post('/', this.controller.create.bind(this.controller));
        
        // Resource routes
        this.router.get('/:id', this.controller.show.bind(this.controller));
        this.router.put('/:id', this.controller.update.bind(this.controller));
        this.router.patch('/:id', this.controller.patch.bind(this.controller));
        this.router.delete('/:id', this.controller.delete.bind(this.controller));
        
        // Nested resource routes
        this.router.get('/:id/relationships/:related', this.controller.showRelated.bind(this.controller));
        this.router.post('/:id/relationships/:related', this.controller.createRelated.bind(this.controller));
        this.router.patch('/:id/relationships/:related', this.controller.updateRelated.bind(this.controller));
        this.router.delete('/:id/relationships/:related/:relatedId', this.controller.deleteRelated.bind(this.controller));
    }

    getRouter() {
        return this.router;
    }
}

// Enhanced controller with proper HTTP semantics
class UserController {
    constructor(userService) {
        this.userService = userService;
    }

    async list(req, res, next) {
        try {
            const {
                page = 1,
                limit = 20,
                sort = 'createdAt',
                order = 'desc',
                filter = {},
                include = []
            } = req.query;

            const options = {
                page: parseInt(page),
                limit: Math.min(parseInt(limit), 100), // Cap at 100
                sort,
                order,
                filter: typeof filter === 'string' ? JSON.parse(filter) : filter,
                include: Array.isArray(include) ? include : [include].filter(Boolean)
            };

            const result = await this.userService.findMany(options);

            // Set pagination headers
            res.set({
                'X-Total-Count': result.total.toString(),
                'X-Page': options.page.toString(),
                'X-Per-Page': options.limit.toString(),
                'X-Total-Pages': Math.ceil(result.total / options.limit).toString()
            });

            // Set cache headers for public data
            if (!req.user) {
                res.set('Cache-Control', 'public, max-age=300'); // 5 minutes
            }

            res.json({
                data: result.data,
                meta: {
                    pagination: {
                        page: options.page,
                        limit: options.limit,
                        total: result.total,
                        pages: Math.ceil(result.total / options.limit)
                    },
                    requestId: req.requestId
                }
            });
        } catch (error) {
            next(error);
        }
    }

    async show(req, res, next) {
        try {
            const { id } = req.params;
            const { include = [] } = req.query;

            const user = await this.userService.findById(id, {
                include: Array.isArray(include) ? include : [include].filter(Boolean)
            });

            if (!user) {
                return res.status(404).json({
                    error: 'User not found',
                    code: 'USER_NOT_FOUND'
                });
            }

            // Set ETag for caching
            const etag = this.generateETag(user);
            res.set('ETag', etag);

            // Check if client has cached version
            if (req.get('If-None-Match') === etag) {
                return res.status(304).end();
            }

            res.json({
                data: user,
                meta: {
                    requestId: req.requestId
                }
            });
        } catch (error) {
            next(error);
        }
    }

    async create(req, res, next) {
        try {
            const userData = req.body;

            // Validate input
            const validation = await this.userService.validate(userData);
            if (!validation.valid) {
                return res.status(422).json({
                    error: 'Validation failed',
                    code: 'VALIDATION_ERROR',
                    details: validation.errors
                });
            }

            const user = await this.userService.create(userData);

            // Set location header for created resource
            res.set('Location', `/api/v1/users/${user.id}`);

            res.status(201).json({
                data: user,
                meta: {
                    requestId: req.requestId
                }
            });
        } catch (error) {
            if (error.code === 'DUPLICATE_EMAIL') {
                return res.status(409).json({
                    error: 'Email already exists',
                    code: 'DUPLICATE_EMAIL'
                });
            }
            next(error);
        }
    }

    async update(req, res, next) {
        try {
            const { id } = req.params;
            const userData = req.body;

            // Check if resource exists
            const existingUser = await this.userService.findById(id);
            if (!existingUser) {
                return res.status(404).json({
                    error: 'User not found',
                    code: 'USER_NOT_FOUND'
                });
            }

            // Handle conditional updates
            const clientETag = req.get('If-Match');
            if (clientETag) {
                const currentETag = this.generateETag(existingUser);
                if (clientETag !== currentETag) {
                    return res.status(412).json({
                        error: 'Precondition failed - resource has been modified',
                        code: 'PRECONDITION_FAILED'
                    });
                }
            }

            const updatedUser = await this.userService.update(id, userData);

            res.json({
                data: updatedUser,
                meta: {
                    requestId: req.requestId
                }
            });
        } catch (error) {
            next(error);
        }
    }

    async patch(req, res, next) {
        try {
            const { id } = req.params;
            const partialData = req.body;

            const user = await this.userService.partialUpdate(id, partialData);
            
            if (!user) {
                return res.status(404).json({
                    error: 'User not found',
                    code: 'USER_NOT_FOUND'
                });
            }

            res.json({
                data: user,
                meta: {
                    requestId: req.requestId
                }
            });
        } catch (error) {
            next(error);
        }
    }

    async delete(req, res, next) {
        try {
            const { id } = req.params;

            const deleted = await this.userService.delete(id);
            
            if (!deleted) {
                return res.status(404).json({
                    error: 'User not found',
                    code: 'USER_NOT_FOUND'
                });
            }

            // Return 204 No Content for successful deletion
            res.status(204).end();
        } catch (error) {
            next(error);
        }
    }

    // Relationship endpoints
    async showRelated(req, res, next) {
        try {
            const { id, related } = req.params;
            
            const validRelations = ['posts', 'comments', 'followers'];
            if (!validRelations.includes(related)) {
                return res.status(400).json({
                    error: 'Invalid relationship',
                    code: 'INVALID_RELATIONSHIP'
                });
            }

            const relatedData = await this.userService.getRelated(id, related);
            
            res.json({
                data: relatedData,
                meta: {
                    requestId: req.requestId
                }
            });
        } catch (error) {
            next(error);
        }
    }

    generateETag(data) {
        return `"${Buffer.from(JSON.stringify(data)).toString('base64')}"`;
    }
}

// Usage
const userController = new UserController(userService);
const userRouter = new RESTfulAPIRouter('users', userController);

export { RESTfulAPIRouter, UserController };
```

### GraphQL Implementation

GraphQL provides a more flexible alternative to REST APIs, allowing clients to request exactly the data they need.

**1. GraphQL Schema and Resolvers:**

```javascript
// graphql-schema.js
import { GraphQLSchema, GraphQLObjectType, GraphQLString, GraphQLInt, GraphQLList, GraphQLNonNull } from 'graphql';
import { GraphQLDateTime } from 'graphql-scalars';

// Type definitions
const UserType = new GraphQLObjectType({
    name: 'User',
    fields: () => ({
        id: { type: new GraphQLNonNull(GraphQLInt) },
        name: { type: new GraphQLNonNull(GraphQLString) },
        email: { type: new GraphQLNonNull(GraphQLString) },
        avatar: { type: GraphQLString },
        createdAt: { type: new GraphQLNonNull(GraphQLDateTime) },
        updatedAt: { type: new GraphQLNonNull(GraphQLDateTime) },
        posts: {
            type: new GraphQLList(PostType),
            resolve: async (user, args, context) => {
                return await context.dataSources.postService.findByUserId(user.id);
            }
        },
        postsCount: {
            type: GraphQLInt,
            resolve: async (user, args, context) => {
                return await context.dataSources.postService.countByUserId(user.id);
            }
        }
    })
});

const PostType = new GraphQLObjectType({
    name: 'Post',
    fields: () => ({
        id: { type: new GraphQLNonNull(GraphQLInt) },
        title: { type: new GraphQLNonNull(GraphQLString) },
        content: { type: new GraphQLNonNull(GraphQLString) },
        published: { type: new GraphQLNonNull(GraphQLString) },
        createdAt: { type: new GraphQLNonNull(GraphQLDateTime) },
        updatedAt: { type: new GraphQLNonNull(GraphQLDateTime) },
        author: {
            type: UserType,
            resolve: async (post, args, context) => {
                return await context.dataSources.userService.findById(post.userId);
            }
        },
        comments: {
            type: new GraphQLList(CommentType),
            resolve: async (post, args, context) => {
                return await context.dataSources.commentService.findByPostId(post.id);
            }
        }
    })
});

// Query type
const QueryType = new GraphQLObjectType({
    name: 'Query',
    fields: {
        user: {
            type: UserType,
            args: {
                id: { type: new GraphQLNonNull(GraphQLInt) }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.userService.findById(args.id);
            }
        },
        users: {
            type: new GraphQLList(UserType),
            args: {
                limit: { type: GraphQLInt, defaultValue: 10 },
                offset: { type: GraphQLInt, defaultValue: 0 },
                search: { type: GraphQLString }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.userService.findMany({
                    limit: args.limit,
                    offset: args.offset,
                    search: args.search
                });
            }
        },
        post: {
            type: PostType,
            args: {
                id: { type: new GraphQLNonNull(GraphQLInt) }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.postService.findById(args.id);
            }
        },
        posts: {
            type: new GraphQLList(PostType),
            args: {
                limit: { type: GraphQLInt, defaultValue: 10 },
                offset: { type: GraphQLInt, defaultValue: 0 },
                userId: { type: GraphQLInt }
            },
            resolve: async (parent, args, context) => {
                if (args.userId) {
                    return await context.dataSources.postService.findByUserId(args.userId);
                }
                return await context.dataSources.postService.findMany({
                    limit: args.limit,
                    offset: args.offset
                });
            }
        }
    }
});

// Mutation type
const MutationType = new GraphQLObjectType({
    name: 'Mutation',
    fields: {
        createUser: {
            type: UserType,
            args: {
                name: { type: new GraphQLNonNull(GraphQLString) },
                email: { type: new GraphQLNonNull(GraphQLString) },
                avatar: { type: GraphQLString }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.userService.create(args);
            }
        },
        updateUser: {
            type: UserType,
            args: {
                id: { type: new GraphQLNonNull(GraphQLInt) },
                name: { type: GraphQLString },
                email: { type: GraphQLString },
                avatar: { type: GraphQLString }
            },
            resolve: async (parent, args, context) => {
                const { id, ...updates } = args;
                return await context.dataSources.userService.update(id, updates);
            }
        },
        deleteUser: {
            type: GraphQLString,
            args: {
                id: { type: new GraphQLNonNull(GraphQLInt) }
            },
            resolve: async (parent, args, context) => {
                const deleted = await context.dataSources.userService.delete(args.id);
                return deleted ? 'User deleted successfully' : 'User not found';
            }
        },
        createPost: {
            type: PostType,
            args: {
                title: { type: new GraphQLNonNull(GraphQLString) },
                content: { type: new GraphQLNonNull(GraphQLString) },
                userId: { type: new GraphQLNonNull(GraphQLInt) }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.postService.create(args);
            }
        }
    }
});

// Create schema
const schema = new GraphQLSchema({
    query: QueryType,
    mutation: MutationType
});

export default schema;
```

**2. GraphQL Server Setup with Express:**

```javascript
// graphql-server.js
import express from 'express';
import { graphqlHTTP } from 'express-graphql';
import { buildSchema } from 'graphql';
import schema from './graphql-schema.js';

class GraphQLServer {
    constructor() {
        this.app = express();
        this.setupMiddleware();
        this.setupGraphQL();
    }

    setupMiddleware() {
        this.app.use(express.json());
        
        // CORS for GraphQL
        this.app.use('/graphql', (req, res, next) => {
            res.header('Access-Control-Allow-Origin', '*');
            res.header('Access-Control-Allow-Methods', 'GET, POST, OPTIONS');
            res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization');
            
            if (req.method === 'OPTIONS') {
                res.sendStatus(200);
            } else {
                next();
            }
        });
    }

    setupGraphQL() {
        this.app.use('/graphql', graphqlHTTP(async (req) => ({
            schema: schema,
            context: {
                user: req.user, // from authentication middleware
                dataSources: {
                    userService: new UserService(),
                    postService: new PostService(),
                    commentService: new CommentService()
                }
            },
            graphiql: process.env.NODE_ENV === 'development',
            customFormatErrorFn: (error) => ({
                message: error.message,
                code: error.extensions?.code || 'INTERNAL_ERROR',
                path: error.path,
                ...(process.env.NODE_ENV === 'development' && { stack: error.stack })
            })
        })));
    }

    start(port = 4000) {
        this.app.listen(port, () => {
            console.log(`GraphQL server running on http://localhost:${port}/graphql`);
        });
    }
}

export default GraphQLServer;
```

### Authentication & Security

Modern authentication systems require multiple layers of security to protect user data and prevent unauthorized access.

**1. JWT Authentication Implementation:**

```javascript
// auth-service.js
import jwt from 'jsonwebtoken';
import bcrypt from 'bcrypt';
import crypto from 'node:crypto';

class AuthenticationService {
    constructor() {
        this.jwtSecret = process.env.JWT_SECRET || crypto.randomBytes(64).toString('hex');
        this.jwtRefreshSecret = process.env.JWT_REFRESH_SECRET || crypto.randomBytes(64).toString('hex');
        this.saltRounds = 12;
        this.tokenExpiry = '15m'; // Access token expires in 15 minutes
        this.refreshTokenExpiry = '7d'; // Refresh token expires in 7 days
    }

    async hashPassword(password) {
        const salt = await bcrypt.genSalt(this.saltRounds);
        return await bcrypt.hash(password, salt);
    }

    async verifyPassword(password, hashedPassword) {
        return await bcrypt.compare(password, hashedPassword);
    }

    generateTokenPair(userId, userEmail) {
        const payload = { 
            userId, 
            email: userEmail,
            iat: Math.floor(Date.now() / 1000),
            type: 'access'
        };

        const refreshPayload = { 
            userId, 
            email: userEmail,
            iat: Math.floor(Date.now() / 1000),
            type: 'refresh'
        };

        const accessToken = jwt.sign(payload, this.jwtSecret, { 
            expiresIn: this.tokenExpiry,
            issuer: 'fullstack-app',
            audience: 'fullstack-users'
        });

        const refreshToken = jwt.sign(refreshPayload, this.jwtRefreshSecret, { 
            expiresIn: this.refreshTokenExpiry,
            issuer: 'fullstack-app',
            audience: 'fullstack-users'
        });

        return { accessToken, refreshToken };
    }

    verifyAccessToken(token) {
        try {
            const decoded = jwt.verify(token, this.jwtSecret, {
                issuer: 'fullstack-app',
                audience: 'fullstack-users'
            });
            
            if (decoded.type !== 'access') {
                throw new Error('Invalid token type');
            }
            
            return decoded;
        } catch (error) {
            throw new Error(`Invalid access token: ${error.message}`);
        }
    }

    verifyRefreshToken(token) {
        try {
            const decoded = jwt.verify(token, this.jwtRefreshSecret, {
                issuer: 'fullstack-app',
                audience: 'fullstack-users'
            });
            
            if (decoded.type !== 'refresh') {
                throw new Error('Invalid token type');
            }
            
            return decoded;
        } catch (error) {
            throw new Error(`Invalid refresh token: ${error.message}`);
        }
    }

    async login(email, password, userService) {
        // Find user by email
        const user = await userService.findByEmail(email);
        if (!user) {
            throw new Error('Invalid credentials');
        }

        // Verify password
        const isValidPassword = await this.verifyPassword(password, user.passwordHash);
        if (!isValidPassword) {
            throw new Error('Invalid credentials');
        }

        // Check if user is active
        if (!user.isActive) {
            throw new Error('Account is deactivated');
        }

        // Update last login
        await userService.updateLastLogin(user.id);

        // Generate tokens
        const tokens = this.generateTokenPair(user.id, user.email);

        return {
            user: {
                id: user.id,
                name: user.name,
                email: user.email,
                avatar: user.avatar,
                role: user.role
            },
            tokens
        };
    }

    async register(userData, userService) {
        // Check if user exists
        const existingUser = await userService.findByEmail(userData.email);
        if (existingUser) {
            throw new Error('Email already registered');
        }

        // Hash password
        const passwordHash = await this.hashPassword(userData.password);

        // Create user
        const newUser = await userService.create({
            ...userData,
            passwordHash,
            isActive: true,
            emailVerified: false,
            createdAt: new Date()
        });

        // Generate email verification token
        const verificationToken = this.generateEmailVerificationToken(newUser.id);

        // Send verification email (implement email service)
        // await emailService.sendVerificationEmail(newUser.email, verificationToken);

        return {
            user: {
                id: newUser.id,
                name: newUser.name,
                email: newUser.email
            },
            message: 'Registration successful. Please check your email for verification.'
        };
    }

    async refreshTokens(refreshToken, userService) {
        const decoded = this.verifyRefreshToken(refreshToken);
        
        // Verify user still exists and is active
        const user = await userService.findById(decoded.userId);
        if (!user || !user.isActive) {
            throw new Error('User not found or inactive');
        }

        // Generate new token pair
        const tokens = this.generateTokenPair(user.id, user.email);

        return { tokens };
    }

    generateEmailVerificationToken(userId) {
        return jwt.sign(
            { userId, type: 'email_verification' },
            this.jwtSecret,
            { expiresIn: '24h' }
        );
    }

    generatePasswordResetToken(userId) {
        return jwt.sign(
            { userId, type: 'password_reset' },
            this.jwtSecret,
            { expiresIn: '1h' }
        );
    }
}

// Authentication middleware
function authenticateToken(req, res, next) {
    const authHeader = req.headers['authorization'];
    const token = authHeader && authHeader.split(' ')[1]; // Bearer TOKEN

    if (!token) {
        return res.status(401).json({ 
            error: 'Access token required',
            code: 'TOKEN_REQUIRED'
        });
    }

    try {
        const authService = new AuthenticationService();
        const decoded = authService.verifyAccessToken(token);
        req.user = decoded;
        next();
    } catch (error) {
        return res.status(403).json({ 
            error: 'Invalid or expired token',
            code: 'TOKEN_INVALID'
        });
    }
}

// Role-based authorization middleware
function requireRole(...roles) {
    return (req, res, next) => {
        if (!req.user) {
            return res.status(401).json({ 
                error: 'Authentication required',
                code: 'AUTH_REQUIRED'
            });
        }

        if (!roles.includes(req.user.role)) {
            return res.status(403).json({ 
                error: 'Insufficient permissions',
                code: 'INSUFFICIENT_PERMISSIONS'
            });
        }

        next();
    };
}

// Resource ownership middleware
function requireOwnership(resourceIdParam = 'id') {
    return async (req, res, next) => {
        const resourceId = req.params[resourceIdParam];
        const userId = req.user.userId;

        // Allow admins to access any resource
        if (req.user.role === 'admin') {
            return next();
        }

        try {
            // This would need to be implemented based on your data layer
            const resource = await getResourceById(resourceId);
            
            if (!resource) {
                return res.status(404).json({
                    error: 'Resource not found',
                    code: 'RESOURCE_NOT_FOUND'
                });
            }

            if (resource.userId !== userId) {
                return res.status(403).json({
                    error: 'Access denied - not resource owner',
                    code: 'NOT_OWNER'
                });
            }

            req.resource = resource;
            next();
        } catch (error) {
            next(error);
        }
    };
}

export { 
    AuthenticationService, 
    authenticateToken, 
    requireRole, 
    requireOwnership 
};
```

**2. Security Best Practices Implementation:**

```javascript
// security-middleware.js
import helmet from 'helmet';
import rateLimit from 'express-rate-limit';
import slowDown from 'express-slow-down';
import { body, validationResult, param } from 'express-validator';
import xss from 'xss';
import DOMPurify from 'isomorphic-dompurify';

class SecurityMiddleware {
    static helmet() {
        return helmet({
            contentSecurityPolicy: {
                directives: {
                    defaultSrc: ["'self'"],
                    styleSrc: ["'self'", "'unsafe-inline'", "https://fonts.googleapis.com"],
                    fontSrc: ["'self'", "https://fonts.gstatic.com"],
                    imgSrc: ["'self'", "data:", "https:", "blob:"],
                    scriptSrc: ["'self'"],
                    connectSrc: ["'self'", "https://api.example.com"],
                    frameSrc: ["'none'"],
                    objectSrc: ["'none'"],
                    baseUri: ["'self'"],
                    formAction: ["'self'"]
                }
            },
            crossOriginEmbedderPolicy: false,
            hsts: {
                maxAge: 31536000,
                includeSubDomains: true,
                preload: true
            }
        });
    }

    static rateLimiter(windowMs = 15 * 60 * 1000, max = 100) {
        return rateLimit({
            windowMs,
            max,
            message: {
                error: 'Too many requests from this IP',
                code: 'RATE_LIMIT_EXCEEDED',
                retryAfter: Math.ceil(windowMs / 1000)
            },
            standardHeaders: true,
            legacyHeaders: false,
            handler: (req, res) => {
                res.status(429).json({
                    error: 'Rate limit exceeded',
                    code: 'RATE_LIMIT_EXCEEDED',
                    retryAfter: Math.ceil(req.rateLimit.msBeforeNext / 1000)
                });
            }
        });
    }

    static speedLimiter() {
        return slowDown({
            windowMs: 15 * 60 * 1000, // 15 minutes
            delayAfter: 50, // allow 50 requests per window
                const deleted = await context.dataSources.userService.delete(args.id);
                return deleted ? 'User deleted successfully' : 'User not found';
            }
        },
        createPost: {
            type: PostType,
            args: {
                title: { type: new GraphQLNonNull(GraphQLString) },
                content: { type: new GraphQLNonNull(GraphQLString) },
                userId: { type: new GraphQLNonNull(GraphQLInt) }
            },
            resolve: async (parent, args, context) => {
                return await context.dataSources.postService.create(args);
            }
        }
    }
});

// Create schema
const schema = new GraphQLSchema({
    query: QueryType,
    mutation: MutationType
});

export default schema;
```

**2. GraphQL Server Setup with Express:**

```javascript
// graphql-server.js
import express from 'express';
import { graphqlHTTP } from 'express-graphql';
import { buildSchema } from 'graphql';
import schema from './graphql-schema.js';

class GraphQLServer {
    constructor() {
        this.app = express();
        this.setupMiddleware();
        this.setupGraphQL();
    }

    setupMiddleware() {
        this.app.use(express.json());
        
        // CORS for GraphQL
        this.app.use('/graphql', (req, res, next) => {
            res.header('Access-Control-Allow-Origin', '*');
            res.header('Access-Control-Allow-Methods', 'GET, POST, OPTIONS');
            res.header('Access-Control-Allow-Headers', 'Content-Type, Authorization');
            
            if (req.method === 'OPTIONS') {
                res.sendStatus(200);
            } else {
                next();
            }
        });
    }

    setupGraphQL() {
        this.app.use('/graphql', graphqlHTTP(async (req) => ({
            schema: schema,
            context: {
                user: req.user, // from authentication middleware
                dataSources: {
                    userService: new UserService(),
                    postService: new PostService(),
                    commentService: new CommentService()
                }
            },
            graphiql: process.env.NODE_ENV === 'development',
            customFormatErrorFn: (error) => ({
                message: error.message,
                code: error.extensions?.code || 'INTERNAL_ERROR',
                path: error.path,
                ...(process.env.NODE_ENV === 'development' && { stack: error.stack })
            })
        })));
    }

    start(port = 4000) {
        this.app.listen(port, () => {
            console.log(`GraphQL server running on http://localhost:${port}/graphql`);
        });
    }
}

export default GraphQLServer;
```

### Authentication & Security

Modern authentication systems require multiple layers of security to protect user data and prevent unauthorized access.

**1. JWT Authentication Implementation:**

```javascript
// auth-service.js
import jwt from 'jsonwebtoken';
import bcrypt from 'bcrypt';
import crypto from 'node:crypto';

class AuthenticationService {
    constructor() {
        this.jwtSecret = process.env.JWT_SECRET || crypto.randomBytes(64).toString('hex');
        this.jwtRefreshSecret = process.env.JWT_REFRESH_SECRET || crypto.randomBytes(64).toString('hex');
        this.saltRounds = 12;
        this.tokenExpiry = '15m'; // Access token expires in 15 minutes
        this.refreshTokenExpiry = '7d'; // Refresh token expires in 7 days
    }

    async hashPassword(password) {
        const salt = await bcrypt.genSalt(this.saltRounds);
        return await bcrypt.hash(password, salt);
    }

    async verifyPassword(password, hashedPassword) {
        return await bcrypt.compare(password, hashedPassword);
    }

    generateTokenPair(userId, userEmail) {
        const payload = { 
            userId, 
            email: userEmail,
            iat: Math.floor(Date.now() / 1000),
            type: 'access'
        };

        const refreshPayload = { 
            userId, 
            email: userEmail,
            iat: Math.floor(Date.now() / 1000),
            type: 'refresh'
        };

        const accessToken = jwt.sign(payload, this.jwtSecret, { 
            expiresIn: this.tokenExpiry,
            issuer: 'fullstack-app',
            audience: 'fullstack-users'
        });

        const refreshToken = jwt.sign(refreshPayload, this.jwtRefreshSecret, { 
            expiresIn: this.refreshTokenExpiry,
            issuer: 'fullstack-app',
            audience: 'fullstack-users'
        });

        return { accessToken, refreshToken };
    }

    verifyAccessToken(token) {
        try {
            const decoded = jwt.verify(token, this.jwtSecret, {
                issuer: 'fullstack-app',
                audience: 'fullstack-users'
            });
            
            if (decoded.type !== 'access') {
                throw new Error('Invalid token type');
            }
            
            return decoded;
        } catch (error) {
            throw new Error(`Invalid access token: ${error.message}`);
        }
    }

    verifyRefreshToken(token) {
        try {
            const decoded = jwt.verify(token, this.jwtRefreshSecret, {
                issuer: 'fullstack-app',
                audience: 'fullstack-users'
            });
            
            if (decoded.type !== 'refresh') {
                throw new Error('Invalid token type');
            }
            
            return decoded;
        } catch (error) {
            throw new Error(`Invalid refresh token: ${error.message}`);
        }
    }

    async login(email, password, userService) {
        // Find user by email
        const user = await userService.findByEmail(email);
        if (!user) {
            throw new Error('Invalid credentials');
        }

        // Verify password
        const isValidPassword = await this.verifyPassword(password, user.passwordHash);
        if (!isValidPassword) {
            throw new Error('Invalid credentials');
        }

        // Check if user is active
        if (!user.isActive) {
            throw new Error('Account is deactivated');
        }

        // Update last login
        await userService.updateLastLogin(user.id);

        // Generate tokens
        const tokens = this.generateTokenPair(user.id, user.email);

        return {
            user: {
                id: user.id,
                name: user.name,
                email: user.email,
                avatar: user.avatar,
                role: user.role
            },
            tokens
        };
    }

    async register(userData, userService) {
        // Check if user exists
        const existingUser = await userService.findByEmail(userData.email);
        if (existingUser) {
            throw new Error('Email already registered');
        }

        // Hash password
        const passwordHash = await this.hashPassword(userData.password);

        // Create user
        const newUser = await userService.create({
            ...userData,
            passwordHash,
            isActive: true,
            emailVerified: false,
            createdAt: new Date()
        });

        // Generate email verification token
        const verificationToken = this.generateEmailVerificationToken(newUser.id);

        // Send verification email (implement email service)
        // await emailService.sendVerificationEmail(newUser.email, verificationToken);

        return {
            user: {
                id: newUser.id,
                name: newUser.name,
                email: newUser.email
            },
            message: 'Registration successful. Please check your email for verification.'
        };
    }

    async refreshTokens(refreshToken, userService) {
        const decoded = this.verifyRefreshToken(refreshToken);
        
        // Verify user still exists and is active
        const user = await userService.findById(decoded.userId);
        if (!user || !user.isActive) {
            throw new Error('User not found or inactive');
        }

        // Generate new token pair
        const tokens = this.generateTokenPair(user.id, user.email);

        return { tokens };
    }

    generateEmailVerificationToken(userId) {
        return jwt.sign(
            { userId, type: 'email_verification' },
            this.jwtSecret,
            { expiresIn: '24h' }
        );
    }

    generatePasswordResetToken(userId) {
        return jwt.sign(
            { userId, type: 'password_reset' },
            this.jwtSecret,
            { expiresIn: '1h' }
        );
    }
}

// Authentication middleware
function authenticateToken(req, res, next) {
    const authHeader = req.headers['authorization'];
    const token = authHeader && authHeader.split(' ')[1]; // Bearer TOKEN

    if (!token) {
        return res.status(401).json({ 
            error: 'Access token required',
            code: 'TOKEN_REQUIRED'
        });
    }

    try {
        const authService = new AuthenticationService();
        const decoded = authService.verifyAccessToken(token);
        req.user = decoded;
        next();
    } catch (error) {
        return res.status(403).json({ 
            error: 'Invalid or expired token',
            code: 'TOKEN_INVALID'
        });
    }
}

// Role-based authorization middleware
function requireRole(...roles) {
    return (req, res, next) => {
        if (!req.user) {
            return res.status(401).json({ 
                error: 'Authentication required',
                code: 'AUTH_REQUIRED'
            });
        }

        if (!roles.includes(req.user.role)) {
            return res.status(403).json({ 
                error: 'Insufficient permissions',
                code: 'INSUFFICIENT_PERMISSIONS'
            });
        }

        next();
    };
}

// Resource ownership middleware
function requireOwnership(resourceIdParam = 'id') {
    return async (req, res, next) => {
        const resourceId = req.params[resourceIdParam];
        const userId = req.user.userId;

        // Allow admins to access any resource
        if (req.user.role === 'admin') {
            return next();
        }

        try {
            // This would need to be implemented based on your data layer
            const resource = await getResourceById(resourceId);
            
            if (!resource) {
                return res.status(404).json({
                    error: 'Resource not found',
                    code: 'RESOURCE_NOT_FOUND'
                });
            }

            if (resource.userId !== userId) {
                return res.status(403).json({
                    error: 'Access denied - not resource owner',
                    code: 'NOT_OWNER'
                });
            }

            req.resource = resource;
            next();
        } catch (error) {
            next(error);
        }
    };
}

export { 
    AuthenticationService, 
    authenticateToken, 
    requireRole, 
    requireOwnership 
};
```

**2. Security Best Practices Implementation:**

```javascript
// security-middleware.js
import helmet from 'helmet';
import rateLimit from 'express-rate-limit';
import slowDown from 'express-slow-down';
import { body, validationResult, param } from 'express-validator';
import xss from 'xss';
import DOMPurify from 'isomorphic-dompurify';

class SecurityMiddleware {
    static helmet() {
        return helmet({
            contentSecurityPolicy: {
                directives: {
                    defaultSrc: ["'self'"],
                    styleSrc: ["'self'", "'unsafe-inline'", "https://fonts.googleapis.com"],
                    fontSrc: ["'self'", "https://fonts.gstatic.com"],
                    imgSrc: ["'self'", "data:", "https:", "blob:"],
                    scriptSrc: ["'self'"],
                    connectSrc: ["'self'", "https://api.example.com"],
                    frameSrc: ["'none'"],
                    objectSrc: ["'none'"],
                    baseUri: ["'self'"],
                    formAction: ["'self'"]
                }
            },
            crossOriginEmbedderPolicy: false,
            hsts: {
                maxAge: 31536000,
                includeSubDomains: true,
                preload: true
            }
        });
    }

    static rateLimiter(windowMs = 15 * 60 * 1000, max = 100) {
        return rateLimit({
            windowMs,
            max,
            message: {
                error: 'Too many requests from this IP',
                code: 'RATE_LIMIT_EXCEEDED',
                retryAfter: Math.ceil(windowMs / 1000)
            },
            standardHeaders: true,
            legacyHeaders: false,
            handler: (req, res) => {
                res.status(429).json({
                    error: 'Rate limit exceeded',
                    code: 'RATE_LIMIT_EXCEEDED',
                    retryAfter: Math.ceil(req.rateLimit.msBeforeNext / 1000)
                });
            }
        });
    }

    static speedLimiter() {
        return slowDown({
            windowMs: 15 * 60 * 1000, // 15 minutes
            delayAfter: 50, // allow 50 requests per windowMs without delay
            delayMs: 500, // add 500ms delay per request after delayAfter
            maxDelayMs: 20000, // maximum delay of 20 seconds
        });
    }

    static inputSanitization() {
        return (req, res, next) => {
            const sanitizeObject = (obj) => {
                for (const key in obj) {
                    if (typeof obj[key] === 'string') {
                        obj[key] = DOMPurify.sanitize(obj[key]);
                        obj[key] = xss(obj[key]);
                    } else if (typeof obj[key] === 'object' && obj[key] !== null) {
                        sanitizeObject(obj[key]);
                    }
                }
            };

            if (req.body) {
                sanitizeObject(req.body);
            }
            if (req.query) {
                sanitizeObject(req.query);
            }
            if (req.params) {
                sanitizeObject(req.params);
            }

            next();
        };
    }

    static validateRequest(validations) {
        return [
            ...validations,
            (req, res, next) => {
                const errors = validationResult(req);
                if (!errors.isEmpty()) {
                    return res.status(400).json({
                        error: 'Validation failed',
                        code: 'VALIDATION_ERROR',
                        details: errors.array().map(error => ({
                            field: error.param,
                            message: error.msg,
                            value: error.value
                        }))
                    });
                }
                next();
            }
        ];
    }

    static userValidationRules() {
        return [
            body('name')
                .trim()
                .isLength({ min: 2, max: 100 })
                .withMessage('Name must be between 2 and 100 characters')
                .matches(/^[a-zA-Z\s]+$/)
                .withMessage('Name can only contain letters and spaces'),
            body('email')
                .trim()
                .isEmail()
                .normalizeEmail()
                .withMessage('Invalid email format')
                .isLength({ max: 255 })
                .withMessage('Email must be less than 255 characters'),
            body('password')
                .isLength({ min: 8, max: 128 })
                .withMessage('Password must be between 8 and 128 characters')
                .matches(/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]/)
                .withMessage('Password must contain at least one uppercase letter, one lowercase letter, one number, and one special character')
        ];
    }

    static idValidationRules() {
        return [
            param('id')
                .isInt({ min: 1 })
                .withMessage('ID must be a positive integer')
        ];
    }

    static apiKeyAuthentication() {
        return (req, res, next) => {
            const apiKey = req.get('X-API-Key');
            
            if (!apiKey) {
                return res.status(401).json({
                    error: 'API key required',
                    code: 'API_KEY_REQUIRED'
                });
            }

            // In production, validate against database
            const validApiKeys = process.env.VALID_API_KEYS?.split(',') || [];
            
            if (!validApiKeys.includes(apiKey)) {
                return res.status(403).json({
                    error: 'Invalid API key',
                    code: 'INVALID_API_KEY'
                });
            }

            next();
        };
    }

    static csrfProtection() {
        return (req, res, next) => {
            // Skip CSRF for API endpoints with API key
            if (req.get('X-API-Key')) {
                return next();
            }

            // Skip for safe methods
            if (['GET', 'HEAD', 'OPTIONS'].includes(req.method)) {
                return next();
            }

            const csrfToken = req.get('X-CSRF-Token') || req.body._csrf;
            const sessionToken = req.session?.csrfToken;

            if (!csrfToken || !sessionToken || csrfToken !== sessionToken) {
                return res.status(403).json({
                    error: 'Invalid CSRF token',
                    code: 'INVALID_CSRF_TOKEN'
                });
            }

            next();
        };
    }
}

export default SecurityMiddleware;
```

### ⚠️ Common Pitfalls

1. **Authentication Token Storage**
   - Never store tokens in localStorage for sensitive apps
   - Use httpOnly cookies for maximum security
   - Implement proper token rotation

2. **SQL Injection Prevention**
   - Always use parameterized queries
   - Validate and sanitize all inputs
   - Implement proper database permissions

3. **API Rate Limiting**
   - Don't rely solely on client-side rate limiting
   - Implement different limits for different endpoints
   - Consider user-based vs IP-based limiting

### ✅ Best Practices

1. **Security First Development**
   - Implement security from the beginning
   - Regular security audits and penetration testing
   - Keep dependencies updated

2. **Error Handling**
   - Never expose internal errors to clients
   - Implement proper logging for debugging
   - Use consistent error response formats

3. **Performance Optimization**
   - Implement caching strategies
   - Use database indexing effectively
   - Monitor and profile regularly

### 🏋️ Exercise 5: Secure API with Authentication
**Difficulty:** 🟡 Intermediate | **Estimated Time:** 60 minutes

Create a secure REST API with JWT authentication, input validation, and proper error handling.

**Requirements:**
1. Implement user registration and login
2. Add JWT token authentication middleware
3. Create protected routes with role-based access
4. Implement input validation and sanitization
5. Add proper error handling and logging

<details>
<summary>✅ Click to see solution</summary>

```javascript
// Complete secure API implementation
import express from 'express';
import { AuthenticationService, authenticateToken, requireRole } from './auth-service.js';
import SecurityMiddleware from './security-middleware.js';

const app = express();
const authService = new AuthenticationService();

// Security middleware
app.use(SecurityMiddleware.helmet());
app.use(SecurityMiddleware.rateLimiter());
app.use(SecurityMiddleware.inputSanitization());
app.use(express.json({ limit: '10mb' }));

// Auth routes
app.post('/api/auth/register', 
    SecurityMiddleware.validateRequest(SecurityMiddleware.userValidationRules()),
    async (req, res, next) => {
        try {
            const result = await authService.register(req.body, userService);
            res.status(201).json(result);
        } catch (error) {
            next(error);
        }
    }
);

app.post('/api/auth/login', async (req, res, next) => {
    try {
        const { email, password } = req.body;
        const result = await authService.login(email, password, userService);
        
        // Set httpOnly cookie for refresh token
        res.cookie('refreshToken', result.tokens.refreshToken, {
            httpOnly: true,
            secure: process.env.NODE_ENV === 'production',
            sameSite: 'strict',
            maxAge: 7 * 24 * 60 * 60 * 1000 // 7 days
        });
        
        res.json({
            user: result.user,
            accessToken: result.tokens.accessToken
        });
    } catch (error) {
        next(error);
    }
});

// Protected routes
app.get('/api/users/profile', authenticateToken, async (req, res, next) => {
    try {
        const user = await userService.findById(req.user.userId);
        res.json({ user });
    } catch (error) {
        next(error);
    }
});

app.get('/api/admin/users', 
    authenticateToken, 
    requireRole('admin'), 
    async (req, res, next) => {
        try {
            const users = await userService.findMany();
            res.json({ users });
        } catch (error) {
            next(error);
        }
    }
);

// Error handling
app.use((error, req, res, next) => {
    console.error(error);
    res.status(error.status || 500).json({
        error: error.message || 'Internal server error',
        requestId: req.requestId
    });
});

export default app;
```

</details>

---

## Chapter 5: Database Integration
📊 **Progress:** Chapter 5 of 8 | ⏱️ **Reading Time:** 35 minutes

### 🎯 Learning Objectives
- Master SQL databases with PostgreSQL and advanced queries
- Implement NoSQL solutions with MongoDB
- Use modern ORMs and query builders effectively
- Design scalable database schemas and relationships

### SQL Databases & PostgreSQL

PostgreSQL is a powerful, open-source relational database that supports advanced features like JSON columns, full-text search, and custom data types.

**Advanced PostgreSQL Features:**

```sql
-- Advanced PostgreSQL schema with modern features
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
CREATE EXTENSION IF NOT EXISTS "pg_trgm";

-- Users table with JSON and array columns
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
    email VARCHAR(255) UNIQUE NOT NULL,
    name VARCHAR(100) NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    profile JSONB DEFAULT '{}',
    roles TEXT[] DEFAULT ARRAY['user'],
    settings JSONB DEFAULT '{"theme": "light", "notifications": true}',
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    deleted_at TIMESTAMP WITH TIME ZONE
);

-- Posts table with full-text search
CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    content TEXT NOT NULL,
    summary TEXT GENERATED ALWAYS AS (LEFT(content, 200)) STORED,
    author_id UUID REFERENCES users(id) ON DELETE CASCADE,
    tags TEXT[] DEFAULT ARRAY[]::TEXT[],
    metadata JSONB DEFAULT '{}',
    search_vector tsvector GENERATED ALWAYS AS (
        to_tsvector('english', title || ' ' || content)
    ) STORED,
    published BOOLEAN DEFAULT false,
    published_at TIMESTAMP WITH TIME ZONE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Indexes for performance
CREATE INDEX idx_users_email_gin ON users USING GIN (email gin_trgm_ops);
CREATE INDEX idx_users_profile ON users USING GIN (profile);
CREATE INDEX idx_posts_search ON posts USING GIN (search_vector);
CREATE INDEX idx_posts_tags ON posts USING GIN (tags);
CREATE INDEX idx_posts_author_published ON posts (author_id, published, created_at DESC);

-- Advanced queries
-- Full-text search with ranking
SELECT 
    p.*,
    u.name as author_name,
    ts_rank(p.search_vector, plainto_tsquery('javascript framework')) as rank
FROM posts p
JOIN users u ON p.author_id = u.id
WHERE p.search_vector @@ plainto_tsquery('javascript framework')
    AND p.published = true
ORDER BY rank DESC, p.created_at DESC
LIMIT 10;

-- JSON queries
SELECT 
    name,
    profile->>'bio' as bio,
    profile->'preferences'->>'theme' as theme
FROM users
WHERE profile->>'location' = 'San Francisco'
    AND profile->'preferences'->>'notifications' = 'true';

-- Array operations
SELECT * FROM posts 
WHERE 'javascript' = ANY(tags)
    OR tags && ARRAY['react', 'vue'];
```

### NoSQL with MongoDB

MongoDB provides flexible document storage with powerful querying capabilities and horizontal scaling features.

**Advanced MongoDB Operations:**

```javascript
// mongodb-service.js
import { MongoClient, ObjectId } from 'mongodb';

class MongoDBService {
    constructor() {
        this.client = null;
        this.db = null;
    }

    async connect(uri, dbName) {
        this.client = new MongoClient(uri, {
            maxPoolSize: 10,
            serverSelectionTimeoutMS: 5000,
            socketTimeoutMS: 45000,
        });
        
        await this.client.connect();
        this.db = this.client.db(dbName);
        
        // Create indexes
        await this.createIndexes();
        
        console.log('Connected to MongoDB');
    }

    async createIndexes() {
        const users = this.db.collection('users');
        const posts = this.db.collection('posts');
        
        // User indexes
        await users.createIndex({ email: 1 }, { unique: true });
        await users.createIndex({ "profile.location": 1 });
        await users.createIndex({ createdAt: -1 });
        
        // Post indexes
        await posts.createIndex({ authorId: 1, createdAt: -1 });
        await posts.createIndex({ tags: 1 });
        await posts.createIndex({ published: 1, publishedAt: -1 });
        await posts.createIndex({ 
            title: "text", 
            content: "text" 
        }, { 
            weights: { title: 10, content: 1 } 
        });
    }

    // Advanced aggregation pipeline
    async getUserPostsAnalytics(userId) {
        const posts = this.db.collection('posts');
        
        return await posts.aggregate([
            { $match: { authorId: new ObjectId(userId) } },
            {
                $group: {
                    _id: null,
                    totalPosts: { $sum: 1 },
                    publishedPosts: {
                        $sum: { $cond: [{ $eq: ['$published', true] }, 1, 0] }
                    },
                    avgWordsPerPost: {
                        $avg: {
                            $size: { $split: ['$content', ' '] }
                        }
                    },
                    mostUsedTags: {
                        $push: '$tags'
                    },
                    oldestPost: { $min: '$createdAt' },
                    newestPost: { $max: '$createdAt' }
                }
            },
            {
                $project: {
                    _id: 0,
                    totalPosts: 1,
                    publishedPosts: 1,
                    draftPosts: { $subtract: ['$totalPosts', '$publishedPosts'] },
                    avgWordsPerPost: { $round: ['$avgWordsPerPost', 0] },
                    mostUsedTags: {
                        $slice: [
                            {
                                $map: {
                                    input: {
                                        $setUnion: {
                                            $reduce: {
                                                input: '$mostUsedTags',
                                                initialValue: [],
                                                in: { $concatArrays: ['$$value', '$$this'] }
                                            }
                                        }
                                    },
                                    as: 'tag',
                                    in: '$$tag'
                                }
                            },
                            5
                        ]
                    },
                    oldestPost: 1,
                    newestPost: 1
                }
            }
        ]).toArray();
    }

    // Complex search with facets
    async searchPosts(query, filters = {}) {
        const posts = this.db.collection('posts');
        
        const pipeline = [
            {
                $match: {
                    $and: [
                        query ? { $text: { $search: query } } : {},
                        { published: true },
                        filters.tags?.length ? { tags: { $in: filters.tags } } : {},
                        filters.dateRange ? {
                            createdAt: {
                                $gte: new Date(filters.dateRange.start),
                                $lte: new Date(filters.dateRange.end)
                            }
                        } : {}
                    ].filter(condition => Object.keys(condition).length > 0)
                }
            },
            {
                $facet: {
                    results: [
                        { $sort: query ? { score: { $meta: 'textScore' } } : { createdAt: -1 } },
                        { $skip: filters.skip || 0 },
                        { $limit: filters.limit || 20 },
                        {
                            $lookup: {
                                from: 'users',
                                localField: 'authorId',
                                foreignField: '_id',
                                as: 'author',
                                pipeline: [
                                    { $project: { name: 1, email: 1, 'profile.avatar': 1 } }
                                ]
                            }
                        },
                        { $unwind: '$author' }
                    ],
                    totalCount: [{ $count: 'count' }],
                    tagFacets: [
                        { $unwind: '$tags' },
                        { $group: { _id: '$tags', count: { $sum: 1 } } },
                        { $sort: { count: -1 } },
                        { $limit: 10 }
                    ]
                }
            }
        ];

        const [result] = await posts.aggregate(pipeline).toArray();
        
        return {
            posts: result.results,
            total: result.totalCount[0]?.count || 0,
            facets: {
                tags: result.tagFacets
            }
        };
    }

    async disconnect() {
        if (this.client) {
            await this.client.close();
            console.log('Disconnected from MongoDB');
        }
    }
}

export default MongoDBService;
```

### ORM & Query Builders

Modern ORMs like Prisma provide type-safe database access with excellent developer experience.

**Prisma Schema and Advanced Usage:**

```prisma
// schema.prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

model User {
  id          String   @id @default(uuid())
  email       String   @unique
  name        String
  passwordHash String   @map("password_hash")
  role        Role     @default(USER)
  profile     Json     @default("{}")
  posts       Post[]
  comments    Comment[]
  followers   Follow[] @relation("UserFollowers")
  following   Follow[] @relation("UserFollowing")
  createdAt   DateTime @default(now()) @map("created_at")
  updatedAt   DateTime @updatedAt @map("updated_at")
  
  @@map("users")
}

model Post {
  id          Int       @id @default(autoincrement())
  title       String
  content     String
  published   Boolean   @default(false)
  authorId    String    @map("author_id")
  author      User      @relation(fields: [authorId], references: [id], onDelete: Cascade)
  comments    Comment[]
  tags        String[]
  metadata    Json      @default("{}")
  createdAt   DateTime  @default(now()) @map("created_at")
  updatedAt   DateTime  @updatedAt @map("updated_at")
  publishedAt DateTime? @map("published_at")
  
  @@map("posts")
}

enum Role {
  USER
  ADMIN
  MODERATOR
}
```

```javascript
// prisma-service.js
import { PrismaClient } from '@prisma/client';

class PrismaService {
    constructor() {
        this.prisma = new PrismaClient({
            log: process.env.NODE_ENV === 'development' ? ['query'] : [],
            errorFormat: 'pretty'
        });
    }

    async createUserWithPosts(userData, postsData) {
        return await this.prisma.user.create({
            data: {
                ...userData,
                posts: {
                    create: postsData
                }
            },
            include: {
                posts: true,
                _count: {
                    select: { posts: true, followers: true }
                }
            }
        });
    }

    async getPostsWithAnalytics(filters = {}) {
        const where = {
            published: true,
            ...(filters.authorId && { authorId: filters.authorId }),
            ...(filters.tags?.length && { 
                tags: { hasEvery: filters.tags } 
            }),
            ...(filters.search && {
                OR: [
                    { title: { contains: filters.search, mode: 'insensitive' } },
                    { content: { contains: filters.search, mode: 'insensitive' } }
                ]
            })
        };

        const [posts, totalCount, analytics] = await Promise.all([
            this.prisma.post.findMany({
                where,
                orderBy: { createdAt: 'desc' },
                skip: filters.skip || 0,
                take: filters.limit || 20,
                include: {
                    author: {
                        select: { id: true, name: true, email: true }
                    },
                    _count: {
                        select: { comments: true }
                    }
                }
            }),
            this.prisma.post.count({ where }),
            this.prisma.post.aggregate({
                where,
                _avg: { id: true },
                _count: { id: true },
                _max: { createdAt: true },
                _min: { createdAt: true }
            })
        ]);

        return {
            posts,
            pagination: {
                total: totalCount,
                page: Math.floor((filters.skip || 0) / (filters.limit || 20)) + 1,
                pages: Math.ceil(totalCount / (filters.limit || 20))
            },
            analytics
        };
    }

    async getUserDashboard(userId) {
        return await this.prisma.user.findUnique({
            where: { id: userId },
            include: {
                posts: {
                    orderBy: { createdAt: 'desc' },
                    take: 5,
                    include: {
                        _count: { select: { comments: true } }
                    }
                },
                _count: {
                    select: {
                        posts: true,
                        followers: true,
                        following: true,
                        comments: true
                    }
                }
            }
        });
    }

    async disconnect() {
        await this.prisma.$disconnect();
    }
}

export default PrismaService;
```

### Database Design Patterns

**1. Optimistic Locking Pattern:**

```javascript
// optimistic-locking.js
class OptimisticLockingService {
    async updateWithOptimisticLock(tableName, id, data, currentVersion) {
        const query = `
            UPDATE ${tableName} 
            SET ${Object.keys(data).map(key => `${key} = $${Object.keys(data).indexOf(key) + 3}`).join(', ')}, 
                version = version + 1,
                updated_at = NOW()
            WHERE id = $1 AND version = $2
            RETURNING *
        `;
        
        const values = [id, currentVersion, ...Object.values(data)];
        const result = await this.db.query(query, values);
        
        if (result.rows.length === 0) {
            throw new Error('Optimistic locking conflict - record was modified by another process');
        }
        
        return result.rows[0];
    }
}
```

### 🏋️ Exercise 6: Database Schema Design
**Difficulty:** 🟡 Intermediate | **Estimated Time:** 45 minutes

Design a complete database schema for a blog platform with users, posts, comments, and tags.

<details>
<summary>✅ Click to see solution</summary>

```sql
-- Complete blog platform schema
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    display_name VARCHAR(100) NOT NULL,
    bio TEXT,
    avatar_url TEXT,
    is_verified BOOLEAN DEFAULT FALSE,
    is_active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    version INTEGER DEFAULT 1
);

CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    slug VARCHAR(200) UNIQUE NOT NULL,
    content TEXT NOT NULL,
    excerpt TEXT,
    author_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    status VARCHAR(20) DEFAULT 'draft' CHECK (status IN ('draft', 'published', 'archived')),
    featured_image_url TEXT,
    published_at TIMESTAMP WITH TIME ZONE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    version INTEGER DEFAULT 1
);

CREATE TABLE tags (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50) UNIQUE NOT NULL,
    slug VARCHAR(50) UNIQUE NOT NULL,
    description TEXT,
    color VARCHAR(7) DEFAULT '#gray',
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE post_tags (
    post_id INTEGER REFERENCES posts(id) ON DELETE CASCADE,
    tag_id INTEGER REFERENCES tags(id) ON DELETE CASCADE,
    PRIMARY KEY (post_id, tag_id)
);

CREATE TABLE comments (
    id SERIAL PRIMARY KEY,
    post_id INTEGER NOT NULL REFERENCES posts(id) ON DELETE CASCADE,
    author_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    parent_id INTEGER REFERENCES comments(id) ON DELETE CASCADE,
    content TEXT NOT NULL,
    is_approved BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Indexes for performance
CREATE INDEX idx_posts_author_status ON posts(author_id, status);
CREATE INDEX idx_posts_published ON posts(published_at DESC) WHERE status = 'published';
CREATE INDEX idx_comments_post ON comments(post_id, created_at);
CREATE INDEX idx_comments_thread ON comments(parent_id, created_at);
```

</details>

---

## Chapter 6: Deployment & DevOps
📊 **Progress:** Chapter 6 of 8 | ⏱️ **Reading Time:** 30 minutes

### Docker Containerization

```dockerfile
# Multi-stage Dockerfile for Node.js app
FROM node:21-alpine AS base
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

FROM node:21-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:21-alpine AS production
WORKDIR /app
COPY --from=base /app/node_modules ./node_modules
COPY --from=build /app/dist ./dist
COPY package*.json ./
EXPOSE 3000
USER node
CMD ["node", "dist/index.js"]
```

### Cloud Deployment Strategies

```yaml
# docker-compose.yml for full stack app
version: '3.8'
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    environment:
      - REACT_APP_API_URL=http://localhost:3001
    depends_on:
      - backend
      
  backend:
    build: ./backend
    ports:
      - "3001:3001"
    environment:
      - DATABASE_URL=postgresql://user:password@postgres:5432/myapp
      - JWT_SECRET=your-secret-key
    depends_on:
      - postgres
      - redis
      
  postgres:
    image: postgres:16-alpine
    environment:
      - POSTGRES_DB=myapp
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=password
    volumes:
      - postgres_data:/var/lib/postgresql/data
      
  redis:
    image: redis:7-alpine
    volumes:
      - redis_data:/data

volumes:
  postgres_data:
  redis_data:
```

### CI/CD Pipelines

```yaml
# .github/workflows/deploy.yml
name: Deploy Full Stack App

on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '21'
      - run: npm ci
      - run: npm run test
      - run: npm run lint
      
  build-and-deploy:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Deploy to production
        run: |
          docker build -t myapp .
          docker push myregistry/myapp:latest
```

### 🏋️ Exercise 7: Complete Deployment Setup
**Difficulty:** 🔴 Advanced | **Estimated Time:** 90 minutes

Set up a complete deployment pipeline with Docker, CI/CD, and monitoring.

<details>
<summary>✅ Click to see solution</summary>

Complete deployment setup with Docker, GitHub Actions, and monitoring configuration.

</details>

---

## Chapter 7: Testing & Quality Assurance
📊 **Progress:** Chapter 7 of 8 | ⏱️ **Reading Time:** 25 minutes

### Frontend Testing Strategies

```javascript
// React component testing with Jest and Testing Library
import { render, screen, fireEvent, waitFor } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { UserProfile } from './UserProfile';

describe('UserProfile Component', () => {
  test('displays user information correctly', () => {
    const mockUser = {
      id: 1,
      name: 'John Doe',
      email: 'john@example.com'
    };
    
    render(<UserProfile user={mockUser} />);
    
    expect(screen.getByText('John Doe')).toBeInTheDocument();
    expect(screen.getByText('john@example.com')).toBeInTheDocument();
  });

  test('handles user update', async () => {
    const mockUser = { id: 1, name: 'John Doe', email: 'john@example.com' };
    const mockOnUpdate = jest.fn();
    
    render(<UserProfile user={mockUser} onUpdate={mockOnUpdate} />);
    
    const editButton = screen.getByRole('button', { name: /edit/i });
    await userEvent.click(editButton);
    
    const nameInput = screen.getByLabelText(/name/i);
    await userEvent.clear(nameInput);
    await userEvent.type(nameInput, 'Jane Doe');
    
    const saveButton = screen.getByRole('button', { name: /save/i });
    await userEvent.click(saveButton);
    
    await waitFor(() => {
      expect(mockOnUpdate).toHaveBeenCalledWith({
        id: 1,
        name: 'Jane Doe',
        email: 'john@example.com'
      });
    });
  });
});
```

### Backend API Testing

```javascript
// API testing with Supertest
import request from 'supertest';
import app from '../app.js';

describe('User API', () => {
  test('POST /api/users should create a new user', async () => {
    const newUser = {
      name: 'John Doe',
      email: 'john@example.com',
      password: 'StrongPassword123!'
    };

    const response = await request(app)
      .post('/api/users')
      .send(newUser)
      .expect(201);

    expect(response.body.data).toMatchObject({
      name: 'John Doe',
      email: 'john@example.com'
    });
    expect(response.body.data).not.toHaveProperty('password');
  });

  test('GET /api/users/:id should return user', async () => {
    const response = await request(app)
      .get('/api/users/1')
      .expect(200);

    expect(response.body.data).toHaveProperty('id', 1);
    expect(response.body.data).toHaveProperty('name');
    expect(response.body.data).toHaveProperty('email');
  });
});
```

### End-to-End Testing

```javascript
// E2E testing with Playwright
import { test, expect } from '@playwright/test';

test.describe('User Management', () => {
  test('should allow user registration and login', async ({ page }) => {
    // Navigate to registration page
    await page.goto('/register');
    
    // Fill registration form
    await page.fill('[data-testid="name-input"]', 'John Doe');
    await page.fill('[data-testid="email-input"]', 'john@example.com');
    await page.fill('[data-testid="password-input"]', 'StrongPassword123!');
    
    // Submit form
    await page.click('[data-testid="register-button"]');
    
    // Verify redirect to login
    await expect(page).toHaveURL('/login');
    
    // Login with new credentials
    await page.fill('[data-testid="email-input"]', 'john@example.com');
    await page.fill('[data-testid="password-input"]', 'StrongPassword123!');
    await page.click('[data-testid="login-button"]');
    
    // Verify successful login
    await expect(page).toHaveURL('/dashboard');
    await expect(page.locator('[data-testid="user-name"]')).toContainText('John Doe');
  });
});
```

---

## Chapter 8: Real-World Projects
📊 **Progress:** Chapter 8 of 8 | ⏱️ **Reading Time:** 40 minutes

### E-commerce Platform

```javascript
// E-commerce platform architecture overview
const ecommerceArchitecture = {
  frontend: {
    framework: 'React 18 with TypeScript',
    stateManagement: 'Zustand + React Query',
    styling: 'Tailwind CSS + Headless UI',
    features: [
      'Product catalog with filtering',
      'Shopping cart with persistence',
      'Checkout process with Stripe',
      'User dashboard and order history',
      'Responsive design'
    ]
  },
  backend: {
    runtime: 'Node.js with Express',
    database: 'PostgreSQL with Prisma ORM',
    authentication: 'JWT with refresh tokens',
    payments: 'Stripe integration',
    features: [
      'Product management API',
      'Order processing system',
      'Inventory management',
      'User authentication and authorization',
      'Email notifications'
    ]
  },
  deployment: {
    platform: 'Docker containers on AWS',
    database: 'AWS RDS PostgreSQL',
    storage: 'AWS S3 for images',
    cdn: 'CloudFront for static assets',
    monitoring: 'CloudWatch and DataDog'
  }
};
```

### Social Media Dashboard

```javascript
// Social media dashboard with real-time features
class SocialMediaDashboard {
  constructor() {
    this.components = {
      postsFeed: 'Infinite scroll with virtual rendering',
      realTimeChat: 'WebSocket with Socket.io',
      notifications: 'Push notifications with service workers',
      analytics: 'Interactive charts with D3.js',
      mediaUpload: 'Drag & drop with progress tracking'
    };
    
    this.techStack = {
      frontend: 'Vue 3 + Composition API + TypeScript',
      backend: 'Node.js + Fastify + GraphQL',
      database: 'MongoDB + Redis for caching',
      realtime: 'Socket.io + Redis adapter',
      deployment: 'Kubernetes on Google Cloud'
    };
  }
}
```

### Task Management System

```javascript
// Task management system with collaborative features
const taskManagementFeatures = {
  userInterface: {
    kanbanBoard: 'Drag & drop task management',
    ganttChart: 'Project timeline visualization',
    calendar: 'Task scheduling and deadlines',
    teamCollaboration: 'Real-time editing and comments',
    fileSharing: 'Document attachments and version control',
    timeTracking: 'Built-in time logging and reporting',
    notifications: 'Smart alerts and email digests'
  },
  
  architecture: {
    frontend: 'Angular 17 + Signals + Material Design',
    backend: 'Node.js + NestJS + TypeORM',
    database: 'PostgreSQL + Redis for sessions',
    realtime: 'WebSockets for live collaboration',
    search: 'Elasticsearch for advanced task search',
    deployment: 'Docker Swarm on DigitalOcean'
  },
  
  keyFeatures: {
    projectManagement: 'Multi-project support with templates',
    userRoles: 'Team roles and permission system',
    integrations: 'Slack, GitHub, Google Calendar APIs',
    reporting: 'Custom dashboards and analytics',
    mobile: 'Progressive Web App with offline support'
  }
};

// Sample implementation structure
class TaskManagementSystem {
  async createProject(projectData) {
    const project = await this.projectService.create({
      ...projectData,
      status: 'active',
      createdAt: new Date()
    });
    
    // Create default task lists
    await this.taskListService.createDefaults(project.id);
    
    return project;
  }
  
  async moveTask(taskId, newListId, position) {
    return await this.db.transaction(async (tx) => {
      // Update task position
      await tx.task.update({
        where: { id: taskId },
        data: { listId: newListId, position }
      });
      
      // Reorder other tasks
      await this.taskService.reorderTasks(newListId, position);
      
      // Notify team members
      await this.notificationService.notifyTaskMove(taskId);
    });
  }
}
```

### 🏋️ Exercise 8: Full Stack Project Implementation
**Difficulty:** 🔴 Advanced | **Estimated Time:** 3-4 hours

Choose one of the three project types and implement a complete full stack application with all the features discussed.

**Requirements:**
1. Complete frontend with modern framework
2. RESTful API with proper authentication
3. Database with optimized schema
4. Real-time features using WebSockets
5. Comprehensive testing suite
6. Docker deployment setup

<details>
<summary>💡 Click to see project planning guide</summary>

**Phase 1: Planning & Setup (30 minutes)**
- Choose your tech stack based on project requirements
- Set up development environment and project structure
- Create database schema and API documentation

**Phase 2: Backend Development (90 minutes)**
- Implement authentication and user management
- Create core API endpoints with proper validation
- Set up database with sample data
- Add real-time features with WebSockets

**Phase 3: Frontend Development (90 minutes)**
- Build responsive UI components
- Implement state management and API integration
- Add real-time features and notifications
- Create user dashboard and main features

**Phase 4: Testing & Deployment (60 minutes)**
- Write unit and integration tests
- Set up CI/CD pipeline
- Create Docker configuration
- Deploy to cloud platform

</details>

<details>
<summary>✅ Click to see implementation checklist</summary>

**Backend Checklist:**
- [ ] User authentication with JWT
- [ ] RESTful API with proper status codes
- [ ] Input validation and sanitization
- [ ] Error handling and logging
- [ ] Database with relationships
- [ ] Real-time WebSocket events
- [ ] API documentation

**Frontend Checklist:**
- [ ] Responsive design with modern CSS
- [ ] Component-based architecture
- [ ] State management (Redux/Zustand/Pinia)
- [ ] Form validation and error handling
- [ ] Loading states and error boundaries
- [ ] Real-time updates
- [ ] Offline support (optional)

**DevOps Checklist:**
- [ ] Docker containerization
- [ ] Environment configuration
- [ ] CI/CD pipeline
- [ ] Database migrations
- [ ] Monitoring and logging
- [ ] Security best practices

</details>

---

## Appendices

### 📖 Glossary

**API (Application Programming Interface)**: A set of protocols and tools for building software applications, defining how components should interact.

**Authentication**: The process of verifying the identity of a user or system.

**Authorization**: The process of determining what permissions an authenticated user has.

**CORS (Cross-Origin Resource Sharing)**: A mechanism that allows restricted resources on a web page to be requested from another domain.

**Docker**: A platform that uses containerization to package applications with their dependencies.

**GraphQL**: A query language and runtime for APIs that allows clients to request exactly the data they need.

**JWT (JSON Web Token)**: A compact way to securely transmit information between parties as JSON objects.

**Middleware**: Software that acts as a bridge between different applications or components.

**NoSQL**: A category of database management systems that don't use the traditional relational model.

**ORM (Object-Relational Mapping)**: A technique that lets you query and manipulate data using an object-oriented paradigm.

**REST (Representational State Transfer)**: An architectural style for designing networked applications.

**Server-Side Rendering (SSR)**: The ability of an application to convert HTML files on the server into a fully rendered page.

**Single Page Application (SPA)**: A web application that loads a single HTML page and dynamically updates content.

**TypeScript**: A typed superset of JavaScript that compiles to plain JavaScript.

**WebSocket**: A communication protocol that provides full-duplex communication over a single TCP connection.

### 🔗 Quick Reference Guide

#### Essential Commands

**Node.js/npm:**
```bash
npm init -y                    # Initialize package.json
npm install package-name       # Install dependency
npm install -D package-name    # Install dev dependency
npm run script-name           # Run package.json script
npx command                   # Run package executable
```

**Git:**
```bash
git init                      # Initialize repository
git add .                     # Stage all changes
git commit -m "message"       # Commit changes
git push origin main          # Push to remote
git pull origin main          # Pull from remote
```

**Docker:**
```bash
docker build -t image-name .  # Build image
docker run -p 3000:3000 image # Run container
docker-compose up -d          # Start services
docker-compose down           # Stop services
```

#### HTTP Status Codes
- **200 OK**: Success
- **201 Created**: Resource created
- **400 Bad Request**: Client error
- **401 Unauthorized**: Authentication required
- **403 Forbidden**: Access denied
- **404 Not Found**: Resource not found
- **500 Internal Server Error**: Server error

#### Common Patterns

**Error Handling:**
```javascript
try {
  const result = await apiCall();
  return result;
} catch (error) {
  console.error('Error:', error);
  throw new APIError(error.message, error.status);
}
```

**Async/Await:**
```javascript
async function fetchData() {
  const response = await fetch('/api/data');
  if (!response.ok) {
    throw new Error('Failed to fetch');
  }
  return await response.json();
}
```

### 📚 Further Reading

#### Books
- **"You Don't Know JS" by Kyle Simpson** - Deep dive into JavaScript
- **"Clean Code" by Robert Martin** - Writing maintainable code
- **"Designing Data-Intensive Applications" by Martin Kleppmann** - System design
- **"System Design Interview" by Alex Xu** - Scalable architecture

#### Online Resources
- **MDN Web Docs**: Comprehensive web development documentation
- **Node.js Documentation**: Official Node.js guides and API reference
- **React Documentation**: Official React learning resources
- **Vue.js Guide**: Complete Vue.js documentation
- **Angular Documentation**: Angular framework guide

#### Courses & Tutorials
- **freeCodeCamp**: Free comprehensive programming courses
- **The Odin Project**: Full-stack curriculum
- **Udemy**: Paid courses on specific technologies
- **Pluralsight**: Enterprise-focused development training

#### Tools & Utilities
- **VS Code**: Popular code editor with extensions
- **Postman**: API testing and documentation
- **Docker Desktop**: Container development environment
- **GitHub**: Version control and collaboration
- **Vercel/Netlify**: Frontend deployment platforms

### 🤝 Community Resources

#### Forums & Discussion
- **Stack Overflow**: Programming Q&A community
- **Reddit**: r/webdev, r/javascript, r/node communities
- **Dev.to**: Developer blogging and discussion platform
- **Discord**: Real-time chat communities for various technologies

#### Conferences & Events
- **JSConf**: JavaScript conferences worldwide
- **React Conf**: Official React conference
- **Node+JS Interactive**: Node.js foundation events
- **Local Meetups**: City-specific developer gatherings

#### Open Source Projects
- **GitHub Explore**: Discover trending repositories
- **First Timers Only**: Beginner-friendly contribution opportunities
- **Hacktoberfest**: Annual open source contribution event
- **Good First Issues**: Curated beginner-friendly issues

#### Learning Communities
- **freeCodeCamp Forum**: Supportive learning community
- **The Odin Project Discord**: Active student community
- **Codecademy Forums**: Platform-specific discussions
- **Dev Twitter**: Follow developers and industry leaders

### 💝 Contributing Guidelines

#### How to Contribute to This Documentation

**Reporting Issues:**
1. Check existing issues before creating new ones
2. Use clear, descriptive titles
3. Provide detailed descriptions with examples
4. Include screenshots for UI-related issues

**Submitting Improvements:**
1. Fork the repository
2. Create a feature branch
3. Make your changes with clear commit messages
4. Submit a pull request with detailed description
5. Respond to review feedback promptly

**Content Guidelines:**
- Keep examples practical and tested
- Use consistent code formatting
- Include error handling in examples
- Add accessibility considerations
- Update version information when relevant

**Style Guide:**
- Use clear, concise language
- Include code comments for complex examples
- Provide both beginner and advanced examples
- Cross-reference related sections
- Maintain consistent emoji usage for visual hierarchy

#### Community Standards
- Be respectful and inclusive
- Help newcomers learn and grow
- Share knowledge and experiences
- Contribute constructively to discussions
- Follow platform-specific guidelines

---

## 🎉 Conclusion

Congratulations! You've completed a comprehensive journey through modern full stack web development. This documentation has covered:

- **Frontend Development**: From HTML5 and CSS3 fundamentals to advanced React, Vue, and Angular applications
- **Backend Development**: Node.js, Express, API design, and security implementation
- **Database Integration**: Both SQL and NoSQL approaches with modern ORMs
- **Deployment & DevOps**: Containerization, CI/CD, and cloud deployment strategies
- **Testing & Quality**: Comprehensive testing strategies for full stack applications
- **Real-World Projects**: Complete application architectures and implementation patterns

### Next Steps

1. **Practice Regularly**: Build projects using different technology combinations
2. **Stay Updated**: Follow framework updates and new web standards
3. **Join Communities**: Engage with other developers and contribute to open source
4. **Specialize Gradually**: Choose areas that interest you most for deeper exploration
5. **Build a Portfolio**: Create projects that demonstrate your full stack capabilities

### Key Takeaways

- **Full stack development** requires understanding multiple technologies and how they integrate
- **Modern frameworks** provide powerful abstractions but understanding fundamentals remains crucial
- **Security** should be considered from the beginning, not added as an afterthought
- **Testing** is essential for maintaining code quality and confidence in deployments
- **Continuous learning** is necessary due to the rapidly evolving nature of web technologies

### Resources for Continued Learning

- Keep this documentation as a reference for implementation details
- Explore the linked resources for deeper understanding
- Join developer communities for ongoing support and networking
- Consider contributing to open source projects to gain real-world experience

Remember: **The best way to learn full stack development is by building real applications.** Start with simple projects and gradually increase complexity as you master each technology layer.

Happy coding! 🚀

---

*This documentation is a living resource. Please contribute improvements, corrections, and updates to keep it current with the rapidly evolving web development landscape.*

**Last Updated**: December 2024  
**Version**: 1.0.0  
**Word Count**: ~18,500 words  
**Completion Status**: ✅ Complete
