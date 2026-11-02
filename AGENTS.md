# Repository Guidelines

## Project Structure & Module Organization

ProjectBoost is a Godot 4.7 3D project using GDScript, Forward Plus rendering, and Jolt Physics. Files currently live at the repository root:

- `project.godot`: project settings and main-scene configuration.
- `Player.tscn`: main scene, including the player mesh, camera, lighting, and environment.
- `Player.gd`: player movement and rotation logic attached to the scene root.
- `icon.svg`: project icon.

Keep related scenes and scripts together. Introduce focused directories such as `scenes/`, `scripts/`, and `assets/` as the project grows, updating resource references through Godot. `.godot/` contains generated editor data and is ignored by Git.

## Build, Test, and Development Commands

Use Godot 4.7; the current GDScript code does not require .NET support. Assuming the executable is available as `godot`:

- `godot --editor --path .`: open the project in the editor.
- `godot --path .`: run the configured main scene.
- `godot --headless --path . --editor --quit`: import resources and check editor startup; inspect output for errors.

There are no build scripts or export presets checked in. Configure export presets in Godot before attempting a distributable build.

## Coding Style & Naming Conventions

Use UTF-8 text and LF line endings, consistent with `.editorconfig` and `.gitattributes`. Match the existing tab indentation in GDScript. Use `snake_case` for functions and variables, retain typed signatures such as `_process(delta: float) -> void`, and use descriptive scene and node names. Follow the existing paired naming pattern, such as `Player.gd` and `Player.tscn`. No formatter or linter is configured.

## Testing Guidelines

No automated test framework or coverage threshold exists. For gameplay changes, run the main scene and verify `ui_accept` moves the player upward and `ui_left`/`ui_right` rotate it in opposite directions. Check the Godot debugger for errors and confirm the camera still frames the player. Record manual validation in the pull request.

## Commit & Pull Request Guidelines

Start commit subjects with one emoji followed by a short, imperative description, for example `✨ Add player thrust controls`. Choose the emoji that best describes the main change:

- ✨ Features
- 🐛 Bug fixes
- ♻️ Refactoring
- 🎨 Visuals and assets
- 📝 Documentation
- ✅ Tests
- 🔧 Configuration and tooling

Keep commits focused. Pull requests should describe behavior changes, validation performed, and related issues when applicable; include screenshots or a short recording for visible changes. Commit required resource metadata, including `.uid` and `.import` files, while excluding generated `.godot/` data.
