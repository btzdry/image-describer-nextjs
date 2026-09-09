# 🖼️ Image Describer

A modern AI-powered image analysis application built with **Next.js, React, Tailwind CSS, Lucide React, and Google Gemini**.

Upload an image and generate:

- 📝 Detailed Image Description
- ✨ AI Image Prompt
- 🔤 Extract Text (OCR)
- 📣 Marketing Copy

The application supports drag-and-drop uploads, image previews, templates, loading states, copy-to-clipboard, TXT downloads, responsive design, and light/dark mode.

---

## 🚀 Features

### Image Upload

- Drag and drop images
- Click to browse files
- PNG, JPG/JPEG, and WEBP supported
- Maximum file size: **5 MB**
- Image preview
- Remove uploaded image

### AI Templates

Choose what you want Gemini to generate:

1. **Detailed Description**
2. **AI Image Prompt**
3. **Extract Text (OCR)**
4. **Marketing Copy**

### Output

- Clean formatted AI response
- Copy result to clipboard
- Download result as `.txt`
- Loading skeleton while processing
- Friendly error messages

### UI

- Responsive design
- Mobile friendly
- Light/dark mode
- Modern Tailwind CSS interface
- Lucide icons

---

# 🛠️ Tech Stack

- **Next.js**
- **React**
- **TypeScript**
- **Tailwind CSS**
- **Lucide React**
- **Google Gemini API**
- **@google/genai**
- **Vercel**

---

# 📁 Project Structure

```text
image-describer/
│
├── app/
│   ├── api/
│   │   └── describe/
│   │       └── route.ts
│   │
│   ├── globals.css
│   └── layout.tsx
│   └── page.tsx
│
├── components/
│   ├── image-dropzone.tsx
│   ├── output-panel.tsx
│   ├── template-selector.tsx
│   └── theme-toggle.tsx
│
├── lib/
│   └── templates.ts
│
├── .env.local.example
├── .gitignore
├── package.json
├── postcss.config.js
├── tailwind.config.ts
├── tsconfig.json
└── README.md
```

---

# 💻 Run Locally

## 1. Requirements

Install the following before running the application:

- Node.js 18+ or newer
- npm
- Git
- A Google Gemini API key

Check Node.js:

```bash
node --version
```

Check npm:

```bash
npm --version
```

---

# 2. Clone the Repository

Clone the GitHub repository:

```bash
git clone https://github.com/YOUR_USERNAME/image-describer.git
```

Enter the project directory:

```bash
cd image-describer
```

---

# 3. Install Dependencies

Run:

```bash
npm install
```

---

# 4. Configure Gemini API

Create a file named:

```text
.env.local
```

in the root of the project.

Add:

```env
GEMINI_API_KEY=YOUR_GEMINI_API_KEY
```

Replace `YOUR_GEMINI_API_KEY` with your actual Gemini API key.

You can create/manage your API key through Google AI Studio.

> **Important:** Never commit `.env.local` to GitHub.

---

# 5. Start the Development Server

Run:

```bash
npm run dev
```

You should see something similar to:

```text
✓ Ready
- Local: http://localhost:3000
```

Open:

```text
http://localhost:3000
```

in your browser.

---

# 🏗️ Production Build

Before deploying, you can test the production build locally.

Run:

```bash
npm run build
```

If the build succeeds, start the production server:

```bash
npm start
```

Then open:

```text
http://localhost:3000
```

---

# 🔐 Environment Variables

The application requires:

```env
GEMINI_API_KEY=YOUR_GEMINI_API_KEY
```

### Local development

Create:

```text
.env.local
```

### Vercel

Add the same variable in:

**Vercel → Project → Settings → Environment Variables**

Use:

```text
Name:
GEMINI_API_KEY

Value:
YOUR_GEMINI_API_KEY
```

Enable it for:

- Production
- Preview
- Development

Then redeploy the application.

---

# ☁️ Deploy to Vercel

## 1. Push the project to GitHub

If Git has not been initialized:

```bash
git init
```

Add the files:

```bash
git add .
```

Create the first commit:

```bash
git commit -m "Initial Image Describer app"
```

Rename the branch:

```bash
git branch -M main
```

Add your GitHub repository:

```bash
git remote add origin https://github.com/YOUR_USERNAME/image-describer.git
```

Push:

```bash
git push -u origin main
```

---

## 2. Import the Repository into Vercel

Open Vercel and sign in with GitHub.

Create a new project:

```text
Add New → Project
```

Select:

```text
image-describer
```

Vercel automatically detects the Next.js project.

---

## 3. Add the Gemini API Key

Before deploying, open:

```text
Environment Variables
```

Add:

```text
GEMINI_API_KEY
```

with your real Gemini API key.

Do **not** put the API key directly into your source code.

---

## 4. Deploy

Click:

```text
Deploy
```

After deployment, Vercel will provide a URL similar to:

```text
https://image-describer.vercel.app
```

Your application is now publicly accessible.

---

# 🔄 Updating the Deployed Application

After making changes locally:

```bash
git add .
git commit -m "Update application"
git push
```

Vercel automatically detects the new GitHub commit and creates a new deployment.

---

# 🔒 Security

Never commit sensitive environment variables.

The following files should **not** be uploaded to GitHub:

```text
.env
.env.local
.env.production
.env.development
```

The API key is used only by the server-side API route:

```text
/app/api/describe/route.ts
```

The Gemini API key should never be exposed in client-side React code.

---

# 🧪 Supported Images

| Format | Supported |
|---|---|
| PNG | ✅ |
| JPG | ✅ |
| JPEG | ✅ |
| WEBP | ✅ |
| GIF | ❌ |
| SVG | ❌ |

Maximum file size:

```text
5 MB
```

---

# 🧠 How It Works

```text
User uploads image
        ↓
Image validation
        ↓
Image converted to Base64
        ↓
Next.js /api/describe route
        ↓
Google Gemini multimodal API
        ↓
AI analyzes image
        ↓
Generated result returned
        ↓
Result displayed in UI
```

The Gemini API request is handled server-side so the API key is not exposed to the browser.

---

# 🐛 Troubleshooting

## `GEMINI_API_KEY is missing`

Make sure `.env.local` exists in the project root:

```text
image-describer/
└── .env.local
```

Example:

```env
GEMINI_API_KEY=your_key_here
```

Restart the development server after changing environment variables:

```bash
npm run dev
```

---

## `fetch failed` / `ECONNRESET`

This generally indicates that the connection to the Gemini API was interrupted.

Try:

```bash
npm run dev
```

again.

Also check:

- Internet connection
- VPN/proxy settings
- Firewall/antivirus
- Gemini API availability
- API key configuration

---

## Gemini API authentication error

Verify that:

```env
GEMINI_API_KEY=...
```

contains the correct API key.

Do not include quotes unless necessary.

Correct:

```env
GEMINI_API_KEY=AIza...
```

---

## Port 3000 already in use

Run Next.js on another port:

```bash
npm run dev -- -p 3001
```

Then open:

```text
http://localhost:3001
```

---

# 📜 Available Commands

| Command | Purpose |
|---|---|
| `npm install` | Install dependencies |
| `npm run dev` | Start development server |
| `npm run build` | Create production build |
| `npm start` | Start production server |
| `git add .` | Stage changes |
| `git commit` | Create Git commit |
| `git push` | Push changes to GitHub |

---

# 📄 License

This project is available for personal and commercial use. Modify and extend it as needed.

---

## 👨‍💻 Development

Built with:

**Next.js + React + TypeScript + Tailwind CSS + Google Gemini**

Enjoy building with Image Describer! 🚀