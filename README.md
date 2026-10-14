# MG3
## Devlog
## Minigame 3 Devlog

### 1. For C# member variables without explicit initial values, a float defaults to `0f`, an int defaults to `0`, a bool defaults to `false`, and a string defaults to `null`. A string field may appear blank in Unity’s Inspector, but `null` and an empty string are different values.

### 2. Unity automatically calls `Update()` once per frame when the MonoBehaviour is enabled and its GameObject is active. I do not call it manually in this assignment. My Timer uses `Time.deltaTime` inside `Update()` to subtract the elapsed time between frames from the remaining time.

### 3. KickWeapon uses a Timer component to control how long each kick stays active. When `ActivateKick()` is called, it activates the kick GameObject and calls `BeginTimer(_lifetimeSeconds)` to start a short countdown. The Timer’s `Update()` method decreases the remaining time each frame. KickWeapon’s own `Update()` method calls `IsFinished()` to check whether the countdown has ended, then deactivates the kick GameObject.

TimerText uses a separate Timer component for the game’s 30-second countdown. Its `Start()` method calls `BeginTimer(_maxGameTime)`. Each frame, its `Update()` method displays the remaining time and checks whether the timer has finished. When time runs out, it calls `GameOver()` to display the GameOver screen and disable the player’s controls.

## Open-Source assets
- [Cat fighter spritesheet](https://opengameart.org/content/cat-fighter-sprite-sheet)
- [Food sprites](https://rcpstd.itch.io/pixel-food-pack)
