# Unreal Engine AI Implementation

**Student:** Yuşa Göverdik <br>
**Instructor:** M.Sc. Eng. Piotr Synoś <br>
**Institution:** University of Information Technology and Management in Rzeszów (UITM) <br>
**Program:** Game Design Development (Erasmus+) - AI in Games Lecture  <br>

---

## Project Overview

This project is an academic assignment demonstrating the implementation of artificial intelligence within Unreal Engine. The objective of this assignment is to establish a functional navigation system and develop two distinct types of AI behaviors: a simple task-oriented actor and an advanced dynamic tracking entity using Unreal Engine's Behavior Tree architecture.

## Implemented Features

### 1. Navigation Mesh (NavMesh)
*   **Static and Dynamic Navigation:** Implemented a `NavMeshBoundsVolume` covering the playable area to generate walkable surfaces.
*   **Runtime Generation:** Configured the NavMesh to update dynamically at runtime, allowing AI to recalculate paths in response to moving obstacles or environmental changes.

### 2. Simple AI (Task-Based)
*   **Blueprint:** `BP_SimpleEnemy`
*   **Controller:** `AIC_Simple`
*   **Logic:** Utilizes the base `AI MoveTo` node executed via `Event BeginPlay`. This entity retrieves the player's location once upon initialization and moves to that specific coordinate, demonstrating basic single-execution pathfinding.

### 3. Advanced AI (Behavior Tree and Blackboard)
*   **Blueprint:** `BP_AdvancedEnemy`
*   **Controller:** `AIC_Advanced`
*   **Logic:** Employs a robust decision-making architecture for continuous tracking.
*   **Blackboard (`BB_Enemy`):** Stores essential runtime data, specifically utilizing an Actor object key (`TargetActor`) to hold the reference to the player character.
*   **Behavior Tree (`BT_Enemy`):** Executes a repeating `Sequence` node that commands the AI to perform a `Move To` task targeting the `TargetActor`. This creates a persistent chasing mechanic that actively updates as the player moves through the environment.

## Execution and Setup

To review the implementation within the Unreal Engine Editor:
1. Open the primary level map containing the NavMesh Bounds Volume.
2. Ensure both `BP_SimpleEnemy` and `BP_AdvancedEnemy` are placed within the level.
3. Press **Play**. 
4. The Simple AI will move to the player's starting location and stop.
5. The Advanced AI will actively track and pursue the player character dynamically across the NavMesh.

## Technical Requirements
*   **Engine:** Unreal Engine 5 (Configured for standard AI and NavMesh features).
*   **Dependencies:** No external plugins required. All logic is built using standard Blueprint visual scripting, AI Controllers, Behavior Trees, and Blackboard assets.
