# Game Foundation

## 1. High concept

A grounded, cinematic open-world crime drama about loyalty, ambition, family pressure, neighborhood identity, and the consequences of difficult choices. The city and cast are original creations. The experience should feel mature and character-led rather than relying on spectacle alone.

**Working title:** Untitled Open-World Crime Drama  
**Engine:** Unreal Engine 5  
**Initial target:** Windows PC (provisional)  
**Prototype style:** Third-person, single-player, Blueprint-first

## 2. Creative pillars

- **Character-led drama:** Missions grow from relationships, conflicting goals, and personal consequences.
- **A lived-in city:** Distinct neighborhoods, recognizable landmarks, ambient activity, and a day/night rhythm.
- **Player agency:** Important scenes allow meaningful dialogue or exploration choices, with clear narrative consequences.
- **Grounded presentation:** Naturalistic animation, material response, lighting, sound design, and restrained UI.
- **Readable gameplay:** Responsive movement, clear interaction prompts, and consistent feedback.

## 3. Original setting

The city is not named yet. The setting remains open for approval; it may be a fictional coastal West African-inspired metropolis, but no real city or neighborhood is assumed. The first prototype should use one compact, fictional block with:

- A residential street
- A small commercial frontage
- A public gathering space
- A recognizable landmark for navigation
- Interior access to one simple location, if scope permits

The vertical slice should establish mood and scale without attempting a full city.

## 4. First playable vertical slice

**Goal:** Prove that the player can explore a small environment, move naturally, interact with a character, and experience a short story beat.

### Included
1. Third-person player controller and camera
2. Walk, jog, and basic jump
3. Camera collision and sensible movement tuning
4. Interaction interface with a contextual prompt
5. One NPC with a short dialogue exchange
6. One objective with a simple completion state
7. Basic pause menu and restart flow
8. A small test map with lighting and ambient audio placeholders

### Explicitly out of scope for this slice
- A full open world
- Online multiplayer
- Complex traffic simulation
- Large crowds or advanced NPC schedules
- Detailed combat systems
- Full economy, faction simulation, or property systems
- Final cinematic assets or voice acting

## 5. Unreal Engine architecture

Start with a clean UE5 project using a third-person template.

### Suggested folders
```
Content/
  _Project/
    Characters/
    Input/
    Interaction/
    Missions/
    UI/
    World/
    Audio/
    Data/
  Maps/
    Prototype/
Config/
Source/                 # Add when C++ modules are introduced
Docs/
```

### Initial gameplay classes and assets
- `BP_PlayerCharacter`: player movement and interaction entry point
- `BP_PlayerController`: input context and UI focus
- `BPI_Interactable`: common interaction contract
- `BP_NPC_Base`: simple NPC interaction behavior
- `BP_MissionManager`: prototype objective state
- `WBP_InteractionPrompt`: contextual prompt
- `WBP_Dialogue`: short dialogue display
- `L_PrototypeBlock`: first test environment

Use Enhanced Input. Keep interaction and mission logic modular so the prototype can grow without coupling every feature to the player Blueprint.

## 6. Visual and performance direction

High fidelity is a target, not a guarantee. Validate the intended visual quality against the actual development PC and target frame rate.

- Use physically based materials and consistent scale.
- Establish lighting and exposure before adding decorative detail.
- Use Nanite and Virtual Shadow Maps selectively where supported by target hardware.
- Use Lumen only after checking performance on the target machine.
- Profile frame time early; do not wait until the city is large.
- Add level streaming and World Partition when the world layout justifies them, not before.

## 7. Milestones

| Milestone | Deliverable | Exit condition |
|---|---|---|
| 1. Foundation | Design brief and technical direction | Scope and assumptions documented |
| 2. Prototype block | UE project, player, camera, interaction | A short playable loop works |
| 3. Story slice | NPC dialogue and one objective | A complete short story beat works |
| 4. World systems | Save state, time-of-day foundation, ambient life | Systems are testable and scoped |
| 5. Production planning | District plan, mission outline, asset pipeline | Content can be produced consistently |
| 6. Optimization and QA | Performance budgets and test plan | Target hardware meets agreed goals |

## 8. Decisions still needed

- Exact Unreal Engine 5 minor version
- Development PC specifications and target frame rate
- Whether the fictional setting should be West African-inspired or another original setting
- Final game title
- Intended release platform(s)

## 9. Immediate next task

Create the UE5 third-person project and implement the vertical-slice foundation: player movement, camera, interaction interface, one NPC, and one short dialogue beat. Keep all art assets replaceable until the visual direction is validated.
