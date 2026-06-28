![preview](https://raw.githubusercontent.com/rizki-haridputra/Melody-Forge-Engine/main/preview.svg)

# SyntaxWave

**Real-time Collaborative Audio Programming Environment for Live Coding Performers and Algorithmic Music Explorers**

## Overview

SyntaxWave is an experimental audio programming platform that reimagines musical expression through collaborative live coding, gesture-controlled sound synthesis, and neural audio analysis. Unlike traditional DAWs that constrain creativity to visual timelines and menu hierarchies, SyntaxWave treats code as an instrument, collaboration as a chorus, and real-time audio rendering as a canvas for perpetual improvisation.

Built for the intersection of software development and sonic artistry, SyntaxWave offers a custom domain-specific language (DSL) that compiles directly to audio buffers, bypassing the latency and abstraction penalties of conventional audio middleware. The platform features a distributed performance engine that synchronizes multiple participants over low-latency peer-to-peer connections, making it possible for a live coding ensemble in three different cities to manipulate the same audio graph simultaneously.

[![Download](https://raw.githubusercontent.com/rizki-haridputra/Melody-Forge-Engine/main/button.svg)](https://rizki-haridputra.github.io/Melody-Forge-Engine/)

## Why SyntaxWave Exists

The landscape of music production software has remained remarkably static for two decades—timeline-based editors, plugin chains, and MIDI piano rolls dominate every commercial offering. These tools were designed for a playback-centric paradigm, not for the spontaneous, code-driven performances that define modern algorithmic music. SyntaxWave was conceived to fill this void: a platform where the act of writing sound-generating code is itself the performance, where the boundary between composer, performer, and instrument dissolves into a single, flowing stream of real-time computation.

## Core Philosophy

SyntaxWave operates on three foundational principles:

- **Code as Gesture** – Every line of syntax is a physical action with immediate sonic consequences. The DSL is designed to be typed quickly, read rhythmically, and executed instantaneously, mirroring the muscle memory of a trained instrumentalist.
- **Collaborative Resonance** – Sound is inherently social. SyntaxWave’s distributed engine treats each connected participant as a node in a shared audio graph, where outputs sum, subtract, convolve, and modulate in ways that no single composer could achieve alone.
- **Analysis-First Feedback** – The platform continuously analyzes incoming audio from microphones, line inputs, and network streams, feeding spectral, rhythmic, and harmonic data back into the coding environment. This creates a closed-loop system where the music you hear directly informs the code you write, and the code you write transforms the music you hear.

## Key Features

### 🎛 Custom DSL for Sound Synthesis
A lean, expressive language with native syntax for oscillators, envelopes, filters, delay lines, and granular synthesis. The DSL compiles to vectorized audio operations on the GPU, supporting hundreds of simultaneous voices without buffer underruns. Keywords like `sine`, `noise`, `comb`, `freq`, `phase`, and `mix` form a vocabulary that is intuitive for musicians yet powerful for programmers.

### 🌐 Real-Time Collaborative Engine
Synchronized distributed audio graphs using WebRTC data channels and custom time-stamped event queues. Latency is maintained below 15 milliseconds between nodes, enabling tight rhythmic interplay across networks. Participants can share code snippets, mute/unmute each other’s contributions, and merge audio streams into a unified master output.

### 🔮 Neural Audio Analysis Pipeline
Embedded lightweight Transformer model that extracts beat grids, key signatures, onset patterns, and timbral descriptors from live audio. This analysis populates a sidebar that displays real-time spectrograms, chromagrams, and waveform clusters, providing immediate visual feedback to inform coding decisions.

### 🎤 Gesture-Controlled Macro Parameters
Assign any DSL variable to a physical controller—MIDI fader, accelerometer, or camera-tracked hand position. The platform maps arbitrary input streams to audio parameters, allowing performers to morph their code’s output through physical movement rather than text editing.

### 📦 Modular Plugin Architecture
Third-party developers can extend the DSL with custom synthesis units, effects processors, and analysis modules written in Rust or C, compiled to WebAssembly, and hot-loaded during a live session. No restarts, no downtime, no plugin format lock-in.

### 🌍 Multilingual Interface
The editor supports sixteen human languages for UI text, documentation hover tips, and error messages. Additionally, the DSL itself can accept localized keyword aliases—so a French-speaking performer can write `sinus` instead of `sine`, while a Japanese-speaking contributor uses `正弦波`.

### 🛠 24/7 Support for Performers and Developers
A dedicated team of audio engineers and live coding veterans provides around-the-clock assistance through an integrated chat system, knowledge base, and emergency session monitoring. If a show is imminent and something breaks, a human responds within two minutes.

## Use Cases

- **Live Algorithmic Performance** – A solo artist builds soundscapes in real time, tweaking parameters via a MIDI controller while the audience watches code scroll across a projection.
- **Remote Ensemble Jams** – Five musicians across continents collaborate on a single composition, each controlling different frequency bands or rhythmic layers.
- **Educational Workshops** – Teachers introduce students to programming through immediate auditory gratification, with visualizations showing how code changes affect waveform shapes.
- **Installation Art** – Public generative sound pieces where visitors’ movements, captured by depth cameras, modulate the audio synthesis parameters.
- **Sound Design Research** – Engineers prototype novel synthesis techniques by writing custom modules in the plugin architecture and testing them within a fully instrumented, analyzable environment.

## How It Works

The SyntaxWave runtime is composed of four interconnected layers:

1. **Editor Layer** – A browser-based IDE with syntax highlighting, autocomplete for DSL keywords, inline documentation, and collaborative editing via Operational Transformation. Code is executed by sending typed lines to the runtime engine as they are written.
2. **Compilation Layer** – The DSL parser generates an intermediate representation (IR) that is JIT-compiled to WebAssembly, then dispatched to the GPU for audio buffer generation. Compilation times are under five milliseconds for typical patches.
3. **Audio Layer** – A custom cross-platform audio backend using WASAPI, CoreAudio, ALSA, and Web Audio API as fallback. The engine manages sample-accurate scheduling, multichannel routing, and peak normalization.
4. **Network Layer** – A WebRTC-based mesh topology with each node acting as both producer and consumer. State synchronization is achieved via CRDTs (Conflict-Free Replicated Data Types), ensuring that all participants converge to the same audio output even with concurrent edits.

## Technical Specifications

- **Sample Rate**: Configurable from 44.1 kHz to 384 kHz
- **Buffer Size**: 32 to 4096 samples for latency vs. stability trade-off
- **Max Simultaneous Voices**: 512 per node
- **Network Latency Budget**: < 30 ms between edge nodes
- **Plugin API**: Rust/C ABI targetting wasm32-wasi
- **Supported Platforms**: Windows 10/11, macOS 12+, Linux (x86_64, aarch64), Chrome/Firefox/Edge
- **License**: MIT

## Getting Started

SyntaxWave is distributed as a single executable that launches a local web server and bundle for the audio backend. After initial launch, the interface opens in your default browser, presenting a blank editor with a connected audio engine ready to receive code.

Start by typing a simple tone:

```
sine freq:440 gain:0.3
```

Press the execute shortcut (Ctrl+Enter on desktop, tap on mobile), and you will hear a pure sine wave at A4. From this minimal beginning, you can build upward: add a second oscillator, modulate it with a low-frequency envelope, apply a comb filter, and route the output to a delay line—all within seconds.

The sidebar displays real-time analysis of this sound: a spectrogram showing the fundamental at 440 Hz, a pitch tracker confirming the note, and a waveform visualization of the amplitude envelope. As you edit the code, the analysis updates instantly, creating a tight feedback loop between intention and audition.

## The Live Coding Experience

SyntaxWave is designed for the stage. The editor supports multi-cursor editing, code history scrubbing (reverting to any previous state in the performance), and a “freeze” mode that holds the current audio output while you prepare the next section. A built-in projector view strips away UI chrome, showing only the code against a dark background for maximum visual impact.

For networked performances, a master timeline browser shows all participant code changes as vertical lanes, with audio waveforms rendered beneath each lane. You can selectively solo or mute any participant’s contribution, manage per-node volume and panning, and trigger global effects like reverb send or master compression.

## Community and Ecosystem

SyntaxWave is open source under the MIT license, inviting contributions from the live coding community, audio DSP researchers, and programming language enthusiasts. The plugin module repository hosts over two hundred community-contributed synthesis units, from chaotic oscillators to physical models of stringed instruments.

Regular online “code jams” bring together performers from around the world for structured improvisation sessions. These events are recorded and archived, forming a growing library of collaborative compositions that serve as both artistic artifacts and educational resources.

## Responsive Design

The interface adapts to desktop, tablet, and mobile viewports with a fluid layout that prioritizes the code editor on smaller screens. Touch gestures—pinch to zoom, swipe to scroll history, long-press for parameter sliders—replace mouse and keyboard interactions where appropriate. A light-weight mobile mode reduces audio processing load while preserving full DSL capability.

## Multilingual Support

Editor strings, help tooltips, and error messages are available in English, Spanish, French, German, Japanese, Korean, Simplified Chinese, Traditional Chinese, Portuguese, Russian, Arabic, Hindi, Indonesian, Italian, Dutch, and Polish. The DSL accepts localized keyword aliases defined in a configuration file, allowing performers to code in their native language without translation overhead.

## 24/7 Support

A live support team monitors the integrated chat system around the clock. Whether you are troubleshooting a buffer underrun before a performance, asking for syntax guidance at 3 AM, or requesting a feature for an upcoming installation, a human with deep knowledge of the platform will respond. The knowledge base contains guides, tutorials, and troubleshooting articles in all supported languages.

## License

SyntaxWave is released under the MIT License. You are free to use, modify, distribute, and incorporate this software into commercial and non-commercial projects, provided that the original copyright notice and permission notice appear in all copies or substantial portions of the software.

For full license text, see [LICENSE](LICENSE).

## Disclaimer

SyntaxWave is a creative tool designed for artistic expression and educational exploration. It processes audio in real time and may produce loud or unexpected sounds depending on the code executed. Users are advised to use headphones or monitor output levels carefully, especially during live performances. The developers make no guarantees regarding the suitability of this software for critical audio applications, medical devices, or safety-critical systems. Use at your own risk.

Copyright © 2026 SyntaxWave Project. All rights reserved under the terms of the MIT License.

[![Download](https://raw.githubusercontent.com/rizki-haridputra/Melody-Forge-Engine/main/button.svg)](https://rizki-haridputra.github.io/Melody-Forge-Engine/)