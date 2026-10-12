# PRD: Dark Theme for Memory Game

## 1. Overview

### Product summary
The Memory Game currently uses a light color scheme and is designed for standard daylight browsing. The goal of this feature is to introduce a dark theme that improves readability, reduces eye strain in low-light conditions, and gives the game a more modern, polished look.

### Objective
Add a dark mode toggle and dark theme styling to the game without changing the underlying gameplay behavior or breaking accessibility.

### Problem statement
The existing UI is visually optimized for bright backgrounds. In low-light environments, the light palette can be uncomfortable to use and may reduce readability for extended play sessions. A dark theme improves user comfort and modernizes the game experience.

## 2. Goals
- Provide a visually comfortable dark theme for the game
- Allow users to switch between light and dark mode easily
- Maintain strong contrast and readable text across all game states
- Preserve the current gameplay logic and UX behavior
- Ensure the feature works across desktop and mobile layouts

## 3. Non-goals
- Adding multiple theme variants beyond light and dark
- Rebuilding the game architecture or game rules
- Introducing a backend or account-based theme persistence
- Redesigning the full UI beyond color and surface styling

## 4. User personas
### Casual player
Wants a game that feels polished and comfortable during long sessions, especially at night.

### Accessibility-focused player
Needs readable contrast, visible controls, and clear focus states in all color modes.

## 5. User stories
- As a player, I want to toggle between light and dark mode so I can play comfortably in any lighting condition.
- As a player, I want the dark theme to cover the board, controls, modal, and score panel so the entire experience feels consistent.
- As a player, I want the theme to persist across refreshes so I do not need to re-enable it each time.
- As a player, I want visible keyboard focus states so I can navigate the game accessibly.
- As a player, I want the game to remain readable and clear even when using the dark theme.

## 6. Functional requirements

### 6.1 Theme toggle
- The game must include a visible theme toggle control in the main interface.
- The toggle should allow switching between Light and Dark themes.
- The selected theme should be stored in browser local storage.

### 6.2 Theme styling
The following UI elements must support dark mode styling:
- page background
- card faces and card backs
- text color
- buttons and control states
- summary/stat panels
- modal dialog
- best scores section
- hover and active button states
- focus ring for keyboard navigation

### 6.3 Persistence
- The selected theme must persist after page refresh.
- If no user preference exists, the app may default to the system preference where possible.

### 6.4 Accessibility
- Text contrast must remain readable in dark mode.
- Focus states must remain clearly visible for keyboard users.
- Buttons and controls must stay accessible and touch-friendly.

### 6.5 Compatibility
- The dark theme must work for both 4x4 and 6x6 game layouts.
- It should remain responsive across desktop and mobile breakpoints.
- It must not affect card matching or game logic.

## 7. UX requirements
- Theme switching should be immediate and obvious.
- Theme control should be placed near the game controls for discoverability.
- Dark mode should feel premium and cohesive rather than simply inverted colors.
- The card game should remain visually balanced with consistent contrast on all states.

## 8. Acceptance criteria

### AC1: Theme toggle present
When a user opens the game, there is a visible control to switch to dark mode.

### AC2: Dark mode updates UI
When the user switches to dark mode, the page background, card surfaces, controls, modal, and score panel update to dark styling.

### AC3: Theme persists
After refreshing the page, the selected theme remains active.

### AC4: Contrast is readable
All text and controls remain legible in dark mode with no low-contrast issues.

### AC5: Gameplay remains unchanged
The user can still play the memory game normally after switching themes without broken or delayed interactions.

### AC6: Keyboard accessibility works
Keyboard users can toggle the theme and retain visible focus styling.

### AC7: Mobile responsiveness
The dark theme remains usable and well-styled on smaller screen widths.

## 9. Design direction
### Visual approach
Use CSS custom properties for colors and theme tokens instead of hardcoded values so the theme can switch cleanly.

### Suggested tokens
- background base
- surface base
- elevated surface
- primary accent
- primary accent hover
- text primary
- text secondary
- success highlight
- card back color
- modal overlay

### Example theme model
```css
:root {
  --bg: #f5f5f5;
  --surface: #ffffff;
  --surface-strong: #eaeaea;
  --text: #333333;
  --primary: #2196f3;
  --primary-hover: #1565c0;
  --card-back: #1976d2;
  --card-front: #ffffff;
  --success: #4caf50;
}

[data-theme="dark"] {
  --bg: #121826;
  --surface: #1d2433;
  --surface-strong: #2a3447;
  --text: #edf2ff;
  --primary: #5ea5ff;
  --primary-hover: #8ab9ff;
  --card-back: #2f4b7c;
  --card-front: #1f2937;
  --success: #66bb6a;
}
```

## 10. Technical notes
- Implement theme variables in the `<style>` section of `memory-game.html`.
- Add a small toggle button in the existing controls area.
- Use `data-theme="dark"` or a class on the `<body>` to trigger styling.
- Use `localStorage` to store the user preference under a simple key such as `memoryGameTheme`.
- Keep the logic simple and avoid adding framework complexity.

## 11. Estimated implementation scope
This is a small, low-risk UI enhancement with the following likely effort:
- 1 small feature addition in the HTML structure
- CSS variable updates for dark palette
- JavaScript for toggle behavior and persistence
- light regression testing for keyboard controls and game flow

## 12. Risks and mitigations
### Risk: low contrast in cards
Mitigation: test text and controls under dark palette and adjust color tokens aggressively.

### Risk: user confusion about toggle location
Mitigation: place toggle next to grid size controls and label it clearly.

### Risk: persistent state issues
Mitigation: store and retrieve theme preference carefully in localStorage and apply on startup before rendering the UI.

## 13. Definition of done
- Light and dark themes are both implemented and working.
- The theme toggle is visible and usable.
- Theme preference persists on refresh.
- All game UI components remain readable and consistent.
- Keyboard navigation and focus states remain functional.
- The app is tested manually for gameplay in both modes.

## 14. Next steps
1. Add the theme toggle in the control panel.
2. Define dark/light CSS variables.
3. Implement theme persistence in JavaScript.
4. Test manual gameplay in both modes.
5. Validate accessibility and responsiveness before release.
