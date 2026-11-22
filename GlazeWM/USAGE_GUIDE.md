# GlazeWM Usage Guide

> A comprehensive guide to using GlazeWM productively with Vim-style keybindings

This configuration is designed with Vim-style keybindings (HJKL for movement) for efficient window management. Master these shortcuts to transform your Windows 11 workflow.

---

## 🚀 Quick Start: Core Workflow

### Basic Window Navigation (Vim-style)

| Action | Keybind | Alternative |
|--------|---------|-------------|
| **Focus left window** | `Alt + H` | `Alt + ←` |
| **Focus down window** | `Alt + J` | `Alt + ↓` |
| **Focus up window** | `Alt + K` | `Alt + ↑` |
| **Focus right window** | `Alt + L` | `Alt + →` |
| **Move window left** | `Alt + Shift + H` | `Alt + Shift + ←` |
| **Move window down** | `Alt + Shift + J` | `Alt + Shift + ↓` |
| **Move window up** | `Alt + Shift + K` | `Alt + Shift + ↑` |
| **Move window right** | `Alt + Shift + L` | `Alt + Shift + →` |

### Launch Terminal & Quick Actions

| Action | Keybind |
|--------|---------|
| **Open Windows Terminal** | `Alt + Enter` |
| **Toggle floating/tiling** | `Alt + Shift + Space` |
| **Fullscreen** | `Alt + F` |
| **Close window** | `Alt + Shift + Q` |
| **Reload config** | `Alt + Shift + R` |

---

## 🎯 Productivity Tips

### Workspace Strategy

You have 9 workspaces (`Alt + 1-9` to switch). Here's a recommended organization:

| Workspaces | Purpose | Examples |
|------------|---------|----------|
| **1-3** | Core work | Browser, Editor, Terminal |
| **4-6** | Communication | Slack, Email, Discord |
| **7-9** | Media/Misc | Spotify, Reference material |

**Move windows between workspaces**: `Alt + Shift + 1-9`

### Window Management Flow

1. **Open apps** → They tile automatically in the current workspace
2. **Resize quickly**:
   - Enter resize mode: `Alt + R`
   - Use `HJKL` or arrow keys to resize
   - Exit: `Enter` or `Esc`
3. **Need floating window?** → `Alt + Shift + Space` (centered by default)

### Monitor Management

With multiple monitors:

| Action | Keybind |
|--------|---------|
| Move workspace to left monitor | `Alt + Shift + A` |
| Move workspace to right monitor | `Alt + Shift + F` |
| Move workspace to upper monitor | `Alt + Shift + D` |
| Move workspace to lower monitor | `Alt + Shift + S` |

> 💡 Cursor jumps automatically when focus changes monitors (enabled by default)

---

## ⚙️ Customization Areas

### 1. Add Your Favorite Apps to Startup

```yaml
general:
  startup_commands:
    - 'shell-exec "C:/Users/YourUsername/AppData/Local/Programs/obsidian/obsidian.exe"'
    - 'shell-exec "C:/Program Files/Google/Chrome/Application/chrome.exe"'
```

### 2. Create Application-Specific Rules

Add to `window_rules` in your config:

```yaml
- commands: ['set-floating --centered']
  match:
    # Keep calculator floating
    - window_process: { equals: 'calculator' }
    
    # Keep password managers floating
    - window_process: { equals: 'KeePass' }
    - window_process: { equals: '1Password' }
```

### 3. Workflow-Specific Optimization

**For Developers:**
- Map `Alt + T` to terminal for frequent access
- Consider workspace-per-project strategy
- Use vertical splits for code + terminal side-by-side

**For Content Creators:**
- Increase gaps for better visual separation
- Add more floating window rules for media apps
- Use dedicated workspace for preview windows

### 4. Performance Tweaks

- `hide_method: 'cloak'` is optimal for performance
- Keep `show_all_in_taskbar: false` for a cleaner taskbar

---

## 🛠 Troubleshooting

### Common Issues

| Problem | Solution |
|---------|----------|
| App isn't tiling | Check if it's in the ignore list (`window_rules`), try `Alt + T` to force tiling |
| Keybind conflict with app | Pause GlazeWM: `Alt + Shift + P`, resume with same shortcut |
| Visual glitches | Redraw: `Alt + Shift + W`, or reload: `Alt + Shift + R` |
| Window stuck in wrong state | Toggle floating `Alt + Shift + Space` twice |

---

## 📈 Next-Level Productivity

### Master These Combos

1. **Quick workspace switch**: 
   - `Alt + 2` → Switch to workspace 2
   - `Alt + Shift + 2` → Move current window to workspace 2

2. **Temporary floating**: 
   - `Alt + Shift + Space` → Float window for quick task
   - `Alt + T` → Tile it back when done

3. **Multi-monitor flow**: 
   - Work on monitor 1
   - `Alt + Shift + F` → Send window to monitor 2

### Recommended Daily Workflow

| Time | Action | Keybind |
|------|--------|---------|
| **Morning** | Start with 3 core apps in workspace 1 | `Alt + Enter`, open apps |
| **Working** | Cycle active workspaces | `Alt + S/A` |
| **Focus** | Use transparency on non-focused windows | Already enabled |
| **Wrap-up** | Close windows, minimize others | `Alt + Shift + Q`, `Alt + M` |

---

## 🎓 Learning Path

### Week 1: Basics
- Master `Alt + HJKL` navigation
- Practice `Alt + 1-3` workspace switching
- Get comfortable with `Alt + Enter` for terminal

### Week 2: Intermediate
- Learn window movement with `Alt + Shift + HJKL`
- Practice resize mode `Alt + R`
- Use floating toggle `Alt + Shift + Space`

### Week 3: Advanced
- Multi-monitor management
- Custom window rules
- Startup commands automation

---

## ⌨️ Complete Keybind Reference

### Navigation
| Keybind | Action |
|---------|--------|
| `Alt + H/J/K/L` | Focus window (left/down/up/right) |
| `Alt + ←/↓/↑/→` | Focus window (arrow alternatives) |

### Window Management
| Keybind | Action |
|---------|--------|
| `Alt + Shift + H/J/K/L` | Move window |
| `Alt + Shift + Space` | Toggle floating |
| `Alt + T` | Toggle tiling |
| `Alt + F` | Toggle fullscreen |
| `Alt + M` | Minimize |
| `Alt + Shift + Q` | Close window |

### Workspaces
| Keybind | Action |
|---------|--------|
| `Alt + 1-9` | Switch to workspace |
| `Alt + Shift + 1-9` | Move window to workspace |
| `Alt + S` | Focus next workspace |
| `Alt + A` | Focus previous workspace |

### Resize Mode
| Keybind | Action |
|---------|--------|
| `Alt + R` | Enter resize mode |
| `H/J/K/L` or arrows | Resize in direction |
| `Enter` or `Esc` | Exit resize mode |

### System
| Keybind | Action |
|---------|--------|
| `Alt + Enter` | Open terminal |
| `Alt + Shift + R` | Reload config |
| `Alt + Shift + W` | Redraw windows |
| `Alt + Shift + P` | Pause/Resume GlazeWM |
| `Alt + Shift + E` | Exit GlazeWM |

---

## 📚 Additional Resources

- [GlazeWM Official Documentation](https://github.com/glzr-io/glazewm)
- [GlazeWM Discord Community](https://discord.gg/glazewm)

---

*Start with 15 minutes of practice using just `Alt + HJKL` navigation and `Alt + 1-3` workspace switching. Once muscle memory develops, incorporate the advanced features.*
