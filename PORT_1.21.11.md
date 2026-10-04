# ZenithDLC — Minecraft 1.21.11 port

This source tree is prepared for Minecraft 1.21.11 / Yarn 1.21.11+build.6.

## Versions
- Minecraft: 1.21.11
- Yarn: 1.21.11+build.6
- Fabric Loader: >= 0.18.1
- Fabric API: 0.141.6+1.21.11
- Java: 21
- Fabric Loom: 1.14

## Build
Run from this directory:

```bash
./gradlew clean build
```

The output JAR will be under `build/libs/`.

## Important
The original project contains many Mixin targets written for 1.21.4. The Mixin config is intentionally tolerant (`required=false`, `defaultRequire=0`) so a changed injection point does not prevent the entire client from starting. Any injection that no longer exists in 1.21.11 will be skipped and its related feature may not work until its target is manually updated.

The generated `zenithdlc-refmap.json` is intentionally removed from source control; Loom regenerates it for the selected mappings.

For a strict port, run a full Gradle compile and fix each reported Java/Mixin target against Yarn 1.21.11.
