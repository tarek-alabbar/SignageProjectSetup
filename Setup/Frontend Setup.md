# 🎨 FRONTEND ENGINEER - Setup Tasks

## Week 1, Day 1-2 Tasks

### ✅ Task 1: Accept GitHub Organization Invite

**Join the GitHub organization**

**Steps:**

1. Check your email for GitHub invitation from PM
2. Click the invitation link
3. Click "Join [organization-name]"
4. Verify you can see the organization at `https://github.com/yourorg`

**If you don't have a GitHub account:**

1. Go to https://github.com/signup
2. Create account
3. Ask PM to resend invitation

---

### ✅ Task 2: Install Development Tools

**Set up your local development environment**

**Required Software:**

1. **Node.js (LTS version):**
   - Download: https://nodejs.org/
   - Choose LTS (Long Term Support) version
   - Install for your OS
   - Verify installation:
     ```bash
     node --version  # Should show v20.x.x or v18.x.x
     npm --version   # Should show 10.x.x or 9.x.x
     ```

2. **Git:**
   - Download: https://git-scm.com/downloads
   - Install for your OS
   - Configure:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```

3. **Visual Studio Code:**
   - Download: https://code.visualstudio.com/
   - Install extensions:
     - **ESLint** (dbaeumer.vscode-eslint)
     - **Prettier** (esbenp.prettier-vscode)
     - **Tailwind CSS IntelliSense** (bradlc.vscode-tailwindcss)
     - **ES7+ React/Redux/React-Native snippets** (dsznajder.es7-react-js-snippets)
     - **Auto Rename Tag** (formulahendry.auto-rename-tag)
     - **GitLens** (eamodio.gitlens)

4. **Browser:**
   - Chrome or Firefox (for React DevTools extension)
   - Install **React Developer Tools** extension

**Optional but recommended:**

- **Postman** or **Insomnia** (for API testing): https://www.postman.com/downloads/

---

### ✅ Task 3: Clone Frontend Repository

**Get the frontend code locally**

**Steps:**

```bash
# Navigate to your projects folder
cd ~/projects  # or wherever you keep projects

# Clone frontend repository
git clone https://github.com/yourorg/yourproject-frontend.git
cd yourproject-frontend

# Verify you're on main branch
git branch
```

---

### ✅ Task 4: Create React + TypeScript + Vite Project

**Set up the frontend project**

**Steps:**

1. **Create Vite project:**

```bash
# Make sure you're in the frontend repo folder
cd yourproject-frontend

# Create Vite project (will create in current directory)
npm create vite@latest . -- --template react-ts

# Answer prompts:
# Current directory is not empty. Remove existing files and continue? Yes
```

2. **Install dependencies:**

```bash
npm install
```

3. **Install additional packages:**

```bash
# State management and data fetching
npm install @tanstack/react-query zustand

# Routing
npm install react-router-dom

# API client
npm install axios

# Forms and validation
npm install react-hook-form zod @hookform/resolvers

# UI Framework (TailwindCSS)
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

# Icons (optional but useful)
npm install lucide-react
```

4. **Configure Tailwind CSS:**

Edit `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Edit `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Custom styles */
body {
  margin: 0;
  font-family:
    -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen", "Ubuntu",
    "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family:
    source-code-pro, Menlo, Monaco, Consolas, "Courier New", monospace;
}
```

5. **Create folder structure:**

```bash
mkdir -p src/components/auth
mkdir -p src/components/layout
mkdir -p src/components/devices
mkdir -p src/components/media
mkdir -p src/components/schedules
mkdir -p src/pages
mkdir -p src/services
mkdir -p src/stores
mkdir -p src/types
mkdir -p src/hooks
mkdir -p src/utils
```

Your structure should look like:

```
src/
├── components/
│   ├── auth/
│   ├── layout/
│   ├── devices/
│   ├── media/
│   └── schedules/
├── pages/
├── services/
├── stores/
├── types/
├── hooks/
├── utils/
├── App.tsx
├── main.tsx
└── index.css
```

6. **Create environment variables file:**

File: `.env.example`

```bash
VITE_API_URL=http://localhost:5000/api
```

File: `.env`

```bash
VITE_API_URL=http://localhost:5000/api
```

7. **Update .gitignore:**

Make sure these are in `.gitignore`:

```
# Environment variables
.env
.env.local
.env.production

# Dependencies
node_modules

# Build
dist
build

# IDE
.vscode
.idea

# OS
.DS_Store
Thumbs.db
```

8. **Test that everything works:**

```bash
npm run dev
```

Should see: "Local: http://localhost:5173/"

Open browser to that URL, should see Vite + React page.

Press Ctrl+C to stop.

9. **Commit initial setup:**

```bash
git add .
git commit -m "Initial React + TypeScript + Vite setup with TailwindCSS"
git push origin main
```

---

### ✅ Task 5: Set Up API Client Service

**Create Axios instance for API calls**

**Steps:**

1. **Create API service:**

File: `src/services/api.ts`

```typescript
import axios from "axios";

const API_URL = import.meta.env.VITE_API_URL || "http://localhost:5000/api";

export const api = axios.create({
  baseURL: API_URL,
  headers: {
    "Content-Type": "application/json",
  },
});

// Request interceptor to add auth token
api.interceptors.request.use(
  (config) => {
    const token = localStorage.getItem("token");
    if (token) {
      config.headers.Authorization = `Bearer ${token}`;
    }
    return config;
  },
  (error) => {
    return Promise.reject(error);
  },
);

// Response interceptor for error handling
api.interceptors.response.use(
  (response) => response,
  (error) => {
    if (error.response?.status === 401) {
      // Token expired or invalid
      localStorage.removeItem("token");
      window.location.href = "/login";
    }
    return Promise.reject(error);
  },
);

export default api;
```

2. **Create TypeScript types:**

File: `src/types/api.types.ts`

```typescript
export interface User {
  id: string;
  email: string;
  createdAt: string;
}

export interface LoginRequest {
  email: string;
  password: string;
}

export interface RegisterRequest {
  email: string;
  password: string;
}

export interface AuthResponse {
  token: string;
  email: string;
  expiresAt: string;
}

export interface Device {
  id: string;
  userId: string;
  name: string;
  deviceUuid?: string;
  isPaired: boolean;
  lastHeartbeat?: string;
  createdAt: string;
}

export interface Media {
  id: string;
  userId: string;
  fileName: string;
  fileType: "Image" | "Video";
  blobUrl: string;
  thumbnailUrl?: string;
  sizeInBytes: number;
  durationSeconds?: number;
  uploadedAt: string;
}

export interface Schedule {
  id: string;
  userId: string;
  deviceId: string;
  name: string;
  isActive: boolean;
  timezone: string;
  createdAt: string;
  updatedAt: string;
  items: ScheduleItem[];
}

export interface ScheduleItem {
  id: string;
  scheduleId: string;
  mediaId: string;
  displayOrder: number;
  startTime: string; // "09:00:00"
  endTime: string; // "17:00:00"
  displayDuration: number; // seconds
  media?: Media;
}
```

3. **Create auth service:**

File: `src/services/authService.ts`

```typescript
import api from "./api";
import {
  LoginRequest,
  RegisterRequest,
  AuthResponse,
} from "../types/api.types";

export const authService = {
  async login(credentials: LoginRequest): Promise<AuthResponse> {
    const response = await api.post<AuthResponse>("/auth/login", credentials);
    return response.data;
  },

  async register(credentials: RegisterRequest): Promise<AuthResponse> {
    const response = await api.post<AuthResponse>(
      "/auth/register",
      credentials,
    );
    return response.data;
  },

  async logout(): Promise<void> {
    localStorage.removeItem("token");
  },
};
```

---

### ✅ Task 6: Set Up Auth Store (Zustand)

**Create global state management for authentication**

**Steps:**

File: `src/stores/authStore.ts`

```typescript
import { create } from "zustand";

interface AuthState {
  token: string | null;
  email: string | null;
  isAuthenticated: boolean;
  setAuth: (token: string, email: string) => void;
  logout: () => void;
}

export const useAuthStore = create<AuthState>((set) => ({
  token: localStorage.getItem("token"),
  email: localStorage.getItem("email"),
  isAuthenticated: !!localStorage.getItem("token"),

  setAuth: (token: string, email: string) => {
    localStorage.setItem("token", token);
    localStorage.setItem("email", email);
    set({ token, email, isAuthenticated: true });
  },

  logout: () => {
    localStorage.removeItem("token");
    localStorage.removeItem("email");
    set({ token: null, email: null, isAuthenticated: false });
  },
}));
```

---

### ✅ Task 7: Create Authentication Pages

**Build login and register pages**

**Steps:**

1. **Create Login Page:**

File: `src/pages/LoginPage.tsx`

```typescript
import { useState } from 'react';
import { useNavigate, Link } from 'react-router-dom';
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';
import { authService } from '../services/authService';
import { useAuthStore } from '../stores/authStore';

const loginSchema = z.object({
  email: z.string().email('Invalid email address'),
  password: z.string().min(1, 'Password is required'),
});

type LoginFormData = z.infer<typeof loginSchema>;

export default function LoginPage() {
  const navigate = useNavigate();
  const setAuth = useAuthStore((state) => state.setAuth);
  const [error, setError] = useState('');
  const [loading, setLoading] = useState(false);

  const {
    register,
    handleSubmit,
    formState: { errors },
  } = useForm<LoginFormData>({
    resolver: zodResolver(loginSchema),
  });

  const onSubmit = async (data: LoginFormData) => {
    setLoading(true);
    setError('');

    try {
      const response = await authService.login(data);
      setAuth(response.token, response.email);
      navigate('/dashboard');
    } catch (err: any) {
      setError(err.response?.data?.message || 'Login failed');
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-100">
      <div className="max-w-md w-full bg-white rounded-lg shadow-md p-8">
        <h2 className="text-2xl font-bold text-center mb-6">Sign In</h2>

        {error && (
          <div className="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded mb-4">
            {error}
          </div>
        )}

        <form onSubmit={handleSubmit(onSubmit)}>
          <div className="mb-4">
            <label className="block text-gray-700 text-sm font-bold mb-2">
              Email
            </label>
            <input
              type="email"
              {...register('email')}
              className="w-full px-3 py-2 border border-gray-300 rounded focus:outline-none focus:border-blue-500"
              placeholder="Enter your email"
            />
            {errors.email && (
              <p className="text-red-500 text-xs mt-1">{errors.email.message}</p>
            )}
          </div>

          <div className="mb-6">
            <label className="block text-gray-700 text-sm font-bold mb-2">
              Password
            </label>
            <input
              type="password"
              {...register('password')}
              className="w-full px-3 py-2 border border-gray-300 rounded focus:outline-none focus:border-blue-500"
              placeholder="Enter your password"
            />
            {errors.password && (
              <p className="text-red-500 text-xs mt-1">{errors.password.message}</p>
            )}
          </div>

          <button
            type="submit"
            disabled={loading}
            className="w-full bg-blue-500 text-white font-bold py-2 px-4 rounded hover:bg-blue-600 disabled:bg-blue-300"
          >
            {loading ? 'Signing in...' : 'Sign In'}
          </button>
        </form>

        <p className="text-center text-gray-600 text-sm mt-4">
          Don't have an account?{' '}
          <Link to="/register" className="text-blue-500 hover:text-blue-600">
            Sign up
          </Link>
        </p>
      </div>
    </div>
  );
}
```

2. **Create Register Page:**

File: `src/pages/RegisterPage.tsx`

```typescript
import { useState } from 'react';
import { useNavigate, Link } from 'react-router-dom';
import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod';
import { authService } from '../services/authService';
import { useAuthStore } from '../stores/authStore';

const registerSchema = z.object({
  email: z.string().email('Invalid email address'),
  password: z.string().min(8, 'Password must be at least 8 characters'),
  confirmPassword: z.string(),
}).refine((data) => data.password === data.confirmPassword, {
  message: "Passwords don't match",
  path: ['confirmPassword'],
});

type RegisterFormData = z.infer<typeof registerSchema>;

export default function RegisterPage() {
  const navigate = useNavigate();
  const setAuth = useAuthStore((state) => state.setAuth);
  const [error, setError] = useState('');
  const [loading, setLoading] = useState(false);

  const {
    register,
    handleSubmit,
    formState: { errors },
  } = useForm<RegisterFormData>({
    resolver: zodResolver(registerSchema),
  });

  const onSubmit = async (data: RegisterFormData) => {
    setLoading(true);
    setError('');

    try {
      const response = await authService.register({
        email: data.email,
        password: data.password,
      });
      setAuth(response.token, response.email);
      navigate('/dashboard');
    } catch (err: any) {
      setError(err.response?.data?.message || 'Registration failed');
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-100">
      <div className="max-w-md w-full bg-white rounded-lg shadow-md p-8">
        <h2 className="text-2xl font-bold text-center mb-6">Create Account</h2>

        {error && (
          <div className="bg-red-100 border border-red-400 text-red-700 px-4 py-3 rounded mb-4">
            {error}
          </div>
        )}

        <form onSubmit={handleSubmit(onSubmit)}>
          <div className="mb-4">
            <label className="block text-gray-700 text-sm font-bold mb-2">
              Email
            </label>
            <input
              type="email"
              {...register('email')}
              className="w-full px-3 py-2 border border-gray-300 rounded focus:outline-none focus:border-blue-500"
              placeholder="Enter your email"
            />
            {errors.email && (
              <p className="text-red-500 text-xs mt-1">{errors.email.message}</p>
            )}
          </div>

          <div className="mb-4">
            <label className="block text-gray-700 text-sm font-bold mb-2">
              Password
            </label>
            <input
              type="password"
              {...register('password')}
              className="w-full px-3 py-2 border border-gray-300 rounded focus:outline-none focus:border-blue-500"
              placeholder="At least 8 characters"
            />
            {errors.password && (
              <p className="text-red-500 text-xs mt-1">{errors.password.message}</p>
            )}
          </div>

          <div className="mb-6">
            <label className="block text-gray-700 text-sm font-bold mb-2">
              Confirm Password
            </label>
            <input
              type="password"
              {...register('confirmPassword')}
              className="w-full px-3 py-2 border border-gray-300 rounded focus:outline-none focus:border-blue-500"
              placeholder="Re-enter your password"
            />
            {errors.confirmPassword && (
              <p className="text-red-500 text-xs mt-1">
                {errors.confirmPassword.message}
              </p>
            )}
          </div>

          <button
            type="submit"
            disabled={loading}
            className="w-full bg-blue-500 text-white font-bold py-2 px-4 rounded hover:bg-blue-600 disabled:bg-blue-300"
          >
            {loading ? 'Creating account...' : 'Sign Up'}
          </button>
        </form>

        <p className="text-center text-gray-600 text-sm mt-4">
          Already have an account?{' '}
          <Link to="/login" className="text-blue-500 hover:text-blue-600">
            Sign in
          </Link>
        </p>
      </div>
    </div>
  );
}
```

3. **Create Dashboard placeholder:**

File: `src/pages/DashboardPage.tsx`

```typescript
export default function DashboardPage() {
  return (
    <div className="p-8">
      <h1 className="text-3xl font-bold">Dashboard</h1>
      <p className="text-gray-600 mt-2">Welcome to your dashboard!</p>
    </div>
  );
}
```

4. **Set up routing:**

File: `src/App.tsx`

```typescript
import { BrowserRouter, Routes, Route, Navigate } from 'react-router-dom';
import { useAuthStore } from './stores/authStore';
import LoginPage from './pages/LoginPage';
import RegisterPage from './pages/RegisterPage';
import DashboardPage from './pages/DashboardPage';

function PrivateRoute({ children }: { children: React.ReactNode }) {
  const isAuthenticated = useAuthStore((state) => state.isAuthenticated);
  return isAuthenticated ? <>{children}</> : <Navigate to="/login" />;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<LoginPage />} />
        <Route path="/register" element={<RegisterPage />} />
        <Route
          path="/dashboard"
          element={
            <PrivateRoute>
              <DashboardPage />
            </PrivateRoute>
          }
        />
        <Route path="/" element={<Navigate to="/dashboard" />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

5. **Update main.tsx to include QueryClient:**

File: `src/main.tsx`

```typescript
import React from 'react';
import ReactDOM from 'react-dom/client';
import { QueryClient, QueryClientProvider } from '@tanstack/react-query';
import App from './App.tsx';
import './index.css';

const queryClient = new QueryClient({
  defaultOptions: {
    queries: {
      refetchOnWindowFocus: false,
      retry: 1,
    },
  },
});

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <QueryClientProvider client={queryClient}>
      <App />
    </QueryClientProvider>
  </React.StrictMode>
);
```

6. **Test the application:**

```bash
npm run dev
```

- Navigate to http://localhost:5173
- Should see login page
- Try clicking "Sign up" link
- Should navigate to register page

7. **Commit:**

```bash
git add .
git commit -m "Add authentication pages and routing"
git push origin main
```

---

## Week 1, Day 3-5 Tasks

### ✅ Task 8: Clone Player Repository

**Set up the PWA player project**

**Steps:**

```bash
cd ~/projects

git clone https://github.com/yourorg/yourproject-player.git
cd yourproject-player

# Create Vite project
npm create vite@latest . -- --template react-ts

# Install dependencies
npm install

# Install PWA plugin
npm install -D vite-plugin-pwa

# Install workbox
npm install workbox-window
```

---

### ✅ Task 10: Configure PWA

**Set up Progressive Web App capabilities**

**Steps:**

1. **Update vite.config.ts:**

File: `vite.config.ts`

```typescript
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";
import { VitePWA } from "vite-plugin-pwa";

export default defineConfig({
  plugins: [
    react(),
    VitePWA({
      registerType: "autoUpdate",
      includeAssets: ["favicon.ico", "robots.txt", "apple-touch-icon.png"],
      manifest: {
        name: "Digital Signage Player",
        short_name: "DS Player",
        description: "Display content on your screen",
        theme_color: "#ffffff",
        background_color: "#ffffff",
        display: "fullscreen",
        orientation: "landscape",
        icons: [
          {
            src: "/icon-192.png",
            sizes: "192x192",
            type: "image/png",
          },
          {
            src: "/icon-512.png",
            sizes: "512x512",
            type: "image/png",
          },
        ],
      },
      workbox: {
        runtimeCaching: [
          {
            urlPattern: /^https:\/\/.*\.blob\.core\.windows\.net\/.*/i,
            handler: "CacheFirst",
            options: {
              cacheName: "media-cache",
              expiration: {
                maxEntries: 50,
                maxAgeSeconds: 7 * 24 * 60 * 60, // 7 days
              },
            },
          },
        ],
      },
    }),
  ],
});
```

2. **Create basic player structure:**

File: `src/App.tsx`

```typescript
import { useState, useEffect } from 'react';

function App() {
  const [isPaired, setIsPaired] = useState(false);

  useEffect(() => {
    // Check if device is already paired
    const paired = localStorage.getItem('isPaired');
    if (paired) {
      setIsPaired(true);
    }
  }, []);

  if (!isPaired) {
    return <PairingScreen onPaired={() => setIsPaired(true)} />;
  }

  return <PlayerScreen />;
}

function PairingScreen({ onPaired }: { onPaired: () => void }) {
  const [code, setCode] = useState('');

  const handleSubmit = async (e: React.FormEvent) => {
    e.preventDefault();

    // TODO: Call API to activate device
    console.log('Pairing with code:', code);

    // For now, just mark as paired
    localStorage.setItem('isPaired', 'true');
    onPaired();
  };

  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-900 text-white">
      <div className="text-center">
        <h1 className="text-4xl font-bold mb-8">Digital Signage Player</h1>
        <p className="text-xl mb-8">Enter the pairing code from your dashboard</p>

        <form onSubmit={handleSubmit} className="space-y-4">
          <input
            type="text"
            value={code}
            onChange={(e) => setCode(e.target.value)}
            placeholder="Enter 6-digit code"
            className="px-6 py-3 text-2xl text-center bg-gray-800 rounded text-white w-64"
            maxLength={6}
          />
          <br />
          <button
            type="submit"
            className="px-8 py-3 bg-blue-500 hover:bg-blue-600 rounded text-xl"
          >
            Pair Device
          </button>
        </form>
      </div>
    </div>
  );
}

function PlayerScreen() {
  return (
    <div className="min-h-screen flex items-center justify-center bg-black text-white">
      <div className="text-center">
        <h1 className="text-6xl font-bold">Ready to Display</h1>
        <p className="text-2xl mt-4">Waiting for content...</p>
      </div>
    </div>
  );
}

export default App;
```

3. **Test the player:**

```bash
npm run dev
```

Open http://localhost:5173 - should see pairing screen

4. **Commit:**

```bash
git add .
git commit -m "Initial PWA player setup with pairing screen"
git push origin main
```

---

## Summary

**Frontend Setup Complete! ✅**

You've set up:

- ✅ React + TypeScript + Vite project
- ✅ TailwindCSS styling
- ✅ Authentication pages (login/register)
- ✅ API client with Axios
- ✅ State management with Zustand
- ✅ Routing with React Router
- ✅ Deployed to Azure Static Web Apps
- ✅ PWA Player basic structure

**Next tasks (Sprint 1 continuation):**

- Build Devices page
- Build Media Library page
- Build Schedules page
- Complete player functionality

**Estimated time for all tasks above:** 2 days

---
