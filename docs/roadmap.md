# Unruly Systems Roadmap

## Phase 1: Prove the Native 3D Stack

Goal: show that a real React Native app can render and test a meaningful 3D game slice through WebGPU on a physical device.

Status:

- WebGPU/Dawn rendering has been proven through `react-native-wgpu`.
- Three.js `WebGPURenderer` and React Three Fiber have a working native path.
- Sortessori has a WebGPU gameplay slice verified through native E2E.
- Expo GL and split-renderer fallback paths remain available.

## Phase 2: Make Sortessori Playable on WebGPU

Goal: move from an E2E-proven gameplay slice to a human-playable WebGPU route.

Work:

- Route real native pointer input through the same renderer-neutral session API used by E2E.
- Preserve drag, snap, retry, completion, and reset behavior.
- Keep native E2E as the gate for every gameplay behavior.
- Keep fallback rendering available until WebGPU is the clear default.

## Phase 3: Own Native Physics

Goal: remove native dependence on fragile browser-first WASM physics assumptions.

Work:

- Time-box a final Polygen/Rapier prove-or-kill spike.
- Build the smallest useful native Rapier JSI/TurboModule backend if Polygen remains blocked.
- Hide backend details behind `@unrulysystems/physics`.
- Start with a narrow surface: world creation, rigid bodies, cuboid colliders, stepping, kinematic motion, raycast, transform snapshots, and destroy.

## Phase 4: Extract Shared Packages

Goal: turn proven Sortessori infrastructure into reusable packages without leaking game-specific logic.

Candidate packages:

- `@unrulysystems/nativegpu`: WebGPU/Dawn and R3F setup helpers for React Native.
- `@unrulysystems/physics`: renderer-neutral physics/session contracts.
- `@unrulysystems/rapier-native`: native Rapier backend for iOS and Android.
- `@unrulysystems/r3f`: native React Three Fiber bridge helpers.
- `@unrulysystems/e2e`: native E2E helpers for React Native apps and games.

## Phase 5: Productize the Studio Pattern

Goal: make Unruly Systems credible as both an indie studio and a consulting brand.

Work:

- Publish clear examples after the private app boundary is clean.
- Keep public repos honest about scaffold, experiment, and production status.
- Build a small public website only after the core narrative and first proof points are solid.
