# Game Studio skills for Rakazo

This skills-only plugin adapts the 74 workflows in Claude Code Game Studios. The original project and MIT license remain at the repository root.

## Install

In Rakazo, open Integrations > + > From GitHub and preview this folder:

https://github.com/bmoh95/claude-code-game-studios/tree/main/rakazo

Select Add skills. Skill names are prefixed studio- to avoid common name collisions, e.g. /studio-start and /studio-brainstorm. Preview the list and skipped parts before adding.

## Important limitations

These are instruction-only adaptations, not Claude Code compatibility. Hooks, rules, scripts, automatic agent delegation, Claude tool permissions and model choices are not installed or automatically executed. Many workflows refer to files, templates, agents and scripts in the full game project: clone the repository separately into a working directory and tell the bot its location. Installed text references belong to each skill; other .claude paths are not installed with the plugin. The bot must use its available tools and explicitly report checks it could not perform. Do not assume all workflows have been individually tested.

Upstream: https://github.com/Donchitos/Claude-Code-Game-Studios (MIT).
