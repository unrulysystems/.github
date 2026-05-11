# Unruly Systems Vision

Unruly Systems builds bold, useful software that challenges default assumptions and turns experimental ideas into working systems.

Tagline: Bold systems, made real.

## Thesis

Native apps and games should be able to use modern rendering, real physics, and real device E2E without abandoning React, React Native, Expo, Three.js, or React Three Fiber ergonomics.

The current proof path is a cross-platform 3D app stack built around:

- WebGPU and Dawn for native rendering.
- Three.js and React Three Fiber as productive authoring layers.
- Native-friendly physics with a headless session boundary.
- Real device E2E as the release gate.

## Current Direction

- Use `react-native-wgpu` and Dawn/WebGPU as the likely long-term native renderer path.
- Keep existing Expo GL and split-renderer paths as measured fallback and migration baselines until parity is proven.
- Keep game state and physics renderer-neutral so rendering, physics, and E2E can evolve independently.
- Prefer a native Rapier JSI/TurboModule path on iOS and Android instead of depending on browser-first WASM assumptions.
- Keep browser Rapier and React/R3F bindings available for web where they fit naturally.
- Extract shared packages only after the Sortessori proving ground shows stable boundaries.

## Principles

- Device proof beats simulated confidence.
- Shared packages should own integration primitives, not app-specific game rules.
- Renderers should consume snapshots and publish explicit input intents.
- Physics should be usable without a mounted render tree.
- Public APIs should stay small until native constraints are proven.
- Private game code should remain private until the product and package boundaries are clear.

## Non-Goals

- Replacing Three.js, React Three Fiber, Expo, or React Native.
- Moving private Sortessori implementation details into public repositories prematurely.
- Treating Polygen or native WASM as the strategic native physics path without a successful proof.
- Removing the Expo GL fallback before WebGPU parity is verified on real devices.
- Calling unit-only or mocked coverage sufficient for native runtime behavior.
