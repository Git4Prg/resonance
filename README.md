# Resonance 🎙️

Resonance is a high-performance, AI-driven Text-to-Speech (TTS) platform that allows users to generate expressive audio from text and clone their own voices with studio-quality precision.

Built with a cutting-edge tech stack, Resonance showcases the integration of cloud storage, real-time audio processing, and type-safe API communication.

## 🚀 Technical Highlights

This project demonstrates proficiency in modern full-stack architecture:

- **Framework**: [Next.js 15](https://nextjs.org/) (App Router) for a seamless, serverless-first experience.
- **API Architecture**: [tRPC](https://trpc.io/) for end-to-end type safety between the client and server.
- **Database & ORM**: [Prisma](https://www.prisma.io/) with **PostgreSQL**, managing complex relationships between users, organizations, voices, and generations.
- **Infrastructure**: [AWS S3](https://aws.amazon.com/s3/) for scalable cloud storage of audio assets, utilizing **Signed URLs** for secure access.
- **Authentication**: [Clerk](https://clerk.com/) for robust, multi-tenant (Organization-based) user management.
- **Audio Intelligence**: 
    - [wavesurfer.js](https://wavesurfer-js.org/) for interactive, real-time audio waveform visualization.
    - [recordrtc](https://recordrtc.org/) for high-fidelity browser-based audio recording.
    - [music-metadata](https://github.com/borewit/music-metadata) for server-side audio validation and duration extraction.
- **State Management**: [TanStack Query](https://tanstack.com/query/latest) (via tRPC) and [TanStack Form](https://tanstack.com/form/latest) for complex form logic and optimistic UI updates.
- **Observability**: [Sentry](https://sentry.io/) for comprehensive error tracking and performance monitoring.
- **AI Engine**: [Chatterbox](https://modal.com/) (running on **Modal**) for state-of-the-art TTS inference.

---

## ✨ Key Features

### 🔊 Advanced Text-to-Speech
- **Real-time Generation**: Transform text into natural-sounding speech with adjustable parameters (Temperature, Top-P, Top-K, Repetition Penalty).
- **Interactive Previews**: High-quality playback with visual waveforms, scrubbing, and speed controls.
- **Persistent History**: Every generation is saved to the cloud, allowing users to revisit and download their audio at any time.

### 🎭 Custom Voice Cloning
- **Voice Training**: Users can create custom voice models by uploading audio files or recording directly in the browser.
- **Validation Engine**: Automated checks for audio duration and format integrity before processing.
- **Voice Library**: A searchable marketplace of both system-provided and user-created custom voices.

### 📱 Premium UX/UI
- **Responsive Design**: Built with **Tailwind CSS** and **shadcn/ui**, featuring a mobile-first approach with elegant drawers and desktop-optimized panels.
- **Dynamic Feedback**: Skeleton loaders for all async states, toast notifications for real-time status updates, and smooth transitions.
- **SEO & Performance**: Optimized for fast page loads and search engine visibility.

---

## 🛠️ Local Development

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd resonance
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up Environment Variables**:
   Create a `.env` file in the root based on your credentials:
   - AWS Keys (S3)
   - Clerk API Keys
   - BetterStack/Neon DB URL
   - Chatterbox API Key

4. **Initialize the Database**:
   ```bash
   npx prisma generate
   npx prisma db push
   ```

5. **Run the development server**:
   ```bash
   npm run dev
   ```

---

## 🏗️ Architecture Note
Resonance was recently migrated from Cloudflare R2 to **AWS S3** to take advantage of native S3 features and better scalability. The storage logic is abstracted into a clean, modular library in `src/lib/s3.ts`.
