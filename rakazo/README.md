# Game Studio skills for Rakazo

This skills-only plugin is now at the **repository root** so Rakazo can preview it directly from the main repository URL.

## Install

In Rakazo, open Integrations > + > From GitHub and paste the root repository URL:

https://github.com/bmoh95/Claude-Code-Game-Studios

Select Add skills. Skill names are prefixed `studio-` to avoid common name collisions, e.g. `/studio-start` and `/studio-brainstorm`.

## Important limitations

These are instruction-only adaptations, not Claude Code compatibility. Hooks, rules, scripts, automatic agent delegation, Claude tool permissions and model choices are not installed or automatically executed. Many workflows refer to files, templates, agents and scripts in the full game project: clone the repository separately into a working directory and tell the bot its location. Installed text references belong to each skill; other .claude paths are not installed with the plugin. The bot must use its available tools and explicitly report checks it could not perform. Do not assume all workflows have been individually tested.

Upstream: https://github.com/Donchitos/Claude-Code-Game-Studios (MIT).
