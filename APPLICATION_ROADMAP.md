# SurePost v2.5 — OpenClaw Implementation Roadmap

This document outlines the technical implementation plan for building the SurePost on-demand local orchestration system using OpenClaw.

## Phase 1: OpenClaw Environment Setup (Week 1)
**Goal:** Install and configure the OpenClaw orchestrator on the host Mac.

- [ ] **1.1 Install OpenClaw:** Set up OpenClaw runtime, ensuring Go, NodeJS, and Python dependencies are met on the host machine.
- [ ] **1.2 Directory Structure:** Scaffold the local folders:
  - `openclaw/agents/` (Agent definitions)
  - `openclaw/tools/` (Custom skills/tools)
  - `Google Drive/SurePost_Content/` (Output directory)
- [ ] **1.3 API Keys Configuration:** Configure `.env` for OpenClaw with Kimi, Claude, getimg.ai, and ElevenLabs API keys.

## Phase 2: Agent Definition & Configuration (Week 1-2)
**Goal:** Define the multi-agent hierarchy in OpenClaw.

- [ ] **2.1 Coordinator Agent:** Define the primary router agent that takes the exact command (e.g., "Generate today's content for AIxMoney") and manages the workflow.
- [ ] **2.2 Research Agent:** Configure with tools to search the web, analyze trends, and compile a daily brief.
- [ ] **2.3 Content Agent:** Configure the Kimi-powered agent with specific system prompts to write hooks, scripts, threads, and captions.
- [ ] **2.4 Media Agent:** Configure the agent responsible for issuing image generation requests and text-to-speech commands.

## Phase 3: Custom Tool/Skill Building (Week 2)
**Goal:** Build the native tools that OpenClaw agents will call to execute tasks.

- [ ] **3.1 `getimg_generator` tool:** A script that accepts a prompt, calls getimg.ai FLUX, and saves the image to a temporary folder.
- [ ] **3.2 `tts_generator` tool:** A script that accepts text and outputs an MP3/WAV file.
- [ ] **3.3 `video_assembler` tool:** A wrapper script around `ffmpeg` that takes 1 audio file and N images, applies Ken Burns zoom, and exports an MP4.
- [ ] **3.4 `drive_exporter` tool:** Organizes the final outputs into a structured daily folder in the Google Drive mapped directory.

## Phase 4: Workflow Testing & Refinement (Week 3)
**Goal:** Run end-to-end tests from a single OpenClaw prompt.

- [ ] **4.1 Test Run:** Execute the full pipeline locally.
- [ ] **4.2 Media Timing Adjustments:** Tweak ffmpeg animations to match audio length precisely.
- [ ] **4.3 Content Quality Gate:** Ensure the Content Agent generates captions and prompts correctly before passing to the Media Agent.
- [ ] **4.4 Final Review:** Verify the Google Drive output folder structure is frictionless for the user's manual phone upload process.
