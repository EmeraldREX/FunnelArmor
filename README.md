# FunnelArmor 0.2.0 – Orbiting Drone Edition

Paper 26.3 / Java 25 / Gradle. **BetterModel is not required.**

## How it works
The main-hand leather horse armor is a controller. Its equipped/held 3D rendering is nearly hidden, but the inventory icon remains visible. Four independent `ItemDisplay` entities (each with its own custom item model) orbit around the player, bob and face tangentially. Their models are split into `models/funnel_drone_1.bbmodel` through `funnel_drone_4.bbmodel`; they can be edited in Blockbench. A right click fires particles from the display positions at the camera's ray-traced target (2 HP by default).

## Build
Open this folder directly in IntelliJ, select JDK 25 as Gradle JVM, run `build`. JAR: `build/libs/FunnelArmor-0.2.0-SNAPSHOT.jar`. Replace old FunnelArmor JAR, restart Paper. Do not install both versions.

## Commands
- `/funnel give` – give controller (OP)
- `/funnel pack` – request bundled pack download to player
- `/funnel status` – pack status
- `/funnel reload` – reload config (OP)

## Resource pack
Updated resource pack is bundled, extracted to `plugins/FunnelArmor/FunnelArmor-pack.zip` on server startup and served over HTTP. `/funnel pack` sends it to the client; if the host is not the same PC, replace the default `127.0.0.1` with a reachable IP/hostname or external HTTPS URL. Client approval might be required. The old 0.1.0 pack will not contain the individual drone models; make sure the client accepts the updated pack.

## Notes
These are four independent displays that follow the player, not a vanilla horse armor body slot. The controller must be in the main hand to see/control them. Displays are removed upon switching away, death, quit, world change, and shutdown. Entity display chunks cannot cross worlds. Orbit motion is server-driven; it can look choppy on higher latency. Test on a staging server before deploying.

Source implementation has not yet been compiled or runtime-tested against Paper 26.3 here.


## v0.3.0 art refresh
Models and texture refreshed into an original sci-fi remote-weapon style inspired by classic anime funnels/bits/fin-funnels. This is an homage, not a direct copy of any one franchise design.
