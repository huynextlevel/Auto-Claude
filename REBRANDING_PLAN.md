# Rebranding Plan

## Name Suggestions

| # | Name | Ý nghĩa | Vibe |
|---|------|---------|------|
| 1 | **Archon** | "Ruler/Leader" trong tiếng Hy Lạp — gợi ý orchestrator điều khiển nhiều agents | Powerful, mythical |
| 2 | **Forgekit** | "Forge" = lò rèn — nơi phần mềm được rèn ra bởi AI | Builder, craftsman |
| 3 | **Nexacode** | "Nexus" + "Code" — trung tâm kết nối agents và code | Modern, tech |
| 4 | **Kairo** | Từ "Kairos" (thời điểm quyết định) — AI chọn đúng thời điểm hành động | Minimal, elegant |
| 5 | **Pylon** | Trụ cột, nền tảng — hỗ trợ vững chắc cho dev workflow | Solid, infrastructure |
| 6 | **Aethon** | Từ "Aether" — sức mạnh vô hình của AI | Futuristic, premium |
| 7 | **Cogent** | "Convincing/Powerful" + gợi đến "Cognition" | Smart, professional |
| 8 | **Voltra** | "Volt" + "Ultra" — năng lượng, tốc độ | Bold, energetic |

> Chọn tên xong thì replace `{NEW_NAME}` trong toàn bộ plan bên dưới.

---

## Phase 1: Package & Build Configuration

### 1.1 `apps/frontend/package.json`
| Line | Hiện tại | Thay đổi |
|------|----------|----------|
| 2 | `"name": "auto-claude-ui"` | `"{new-name}-ui"` |
| 5 | `"description": "Desktop UI for Auto Claude..."` | Update description |
| 6 | `"homepage": "https://github.com/AndyMik90/Auto-Claude"` | Update repo URL |
| 9 | Repository URL `Auto-Claude` | Update repo URL |
| 13 | `"name": "Auto Claude Team"` | `"{New Name} Team"` |
| 41 | `open dist/mac-arm64/Auto-Claude.app` | `{New-Name}.app` |
| 42 | `start "" "dist\\win-unpacked\\Auto-Claude.exe"` | `{New-Name}.exe` |
| 146 | `"appId": "com.autoclaude.ui"` | `"com.{newname}.ui"` |
| 147 | `"productName": "Auto-Claude"` | `"{New-Name}"` |
| 154 | `"repo": "Auto-Claude"` | Update repo name |

### 1.2 `apps/frontend/src/renderer/index.html`
| Line | Hiện tại | Thay đổi |
|------|----------|----------|
| 10 | `<title>Auto Claude</title>` | `<title>{New Name}</title>` |

---

## Phase 2: i18n Translation Files

### 2.1 English — `apps/frontend/src/shared/i18n/locales/en/`

**welcome.json:**
| Key | Hiện tại | Thay đổi |
|-----|----------|----------|
| `title` | "Welcome to Auto Claude" | "Welcome to {New Name}" |
| `subtitle` | "Build software autonomously with AI-powered agents" | Update tagline |

**onboarding.json:**
| Key | Hiện tại | Thay đổi |
|-----|----------|----------|
| `description` | "Configure your Auto Claude environment..." | Update |
| `welcome.title` | "Welcome to Auto Claude" | "Welcome to {New Name}" |
| `welcome.subtitle` | "Build software autonomously..." | Update tagline |
| `completion.subtitle` | "Auto Claude is ready to help you..." | "{New Name} is ready..." |
| `claudeCode.description` | "...powers Auto Claude's AI features..." | "...powers {New Name}'s AI features..." |

**navigation.json:**
| Key | Hiện tại | Thay đổi |
|-----|----------|----------|
| `initializeToCreateTasks` | "Initialize Auto Claude to create tasks" | "Initialize {New Name}..." |

### 2.2 French — `apps/frontend/src/shared/i18n/locales/fr/`

**welcome.json:**
| Key | Hiện tại | Thay đổi |
|-----|----------|----------|
| `title` | "Bienvenue sur Auto Claude" | "Bienvenue sur {New Name}" |
| `subtitle` | "Construisez des logiciels..." | Update |

**onboarding.json:**
| Key | Hiện tại | Thay đổi |
|-----|----------|----------|
| `description` | "Configurez votre environnement Auto Claude..." | Update |
| `welcome.title` | "Bienvenue sur Auto Claude" | Update |
| `completion.subtitle` | "Auto Claude est prêt..." | "{New Name} est prêt..." |

---

## Phase 3: React Components (Hardcoded Strings)

> Lưu ý: Những strings này nên được chuyển sang i18n thay vì chỉ đổi tên.
> Nhưng nếu chỉ rebrand nhanh thì replace trực tiếp.

| File | Strings cần đổi |
|------|-----------------|
| `src/renderer/components/AppUpdateNotification.tsx` | "A new version of Auto Claude is ready to download" |
| | "Please move Auto Claude to your Applications folder before updating." |
| `src/renderer/components/Worktrees.tsx` | "Manage isolated workspaces for your Auto Claude tasks" |
| | "Worktrees are created automatically when Auto Claude builds features." |
| `src/renderer/components/AuthFailureModal.tsx` | "...to continue using Auto Claude." |
| `src/renderer/components/AgentTools.tsx` | `name: 'Auto-Claude Tools'` → `'{New-Name} Tools'` |
| `src/renderer/components/GitHubSetupModal.tsx` | 3 chỗ chứa "Auto Claude" |
| `src/renderer/components/onboarding/ClaudeCodeStep.tsx` | "...powers Auto Claude's AI features" |

---

## Phase 4: Sidebar Links

| File | Hiện tại | Thay đổi |
|------|----------|----------|
| `src/renderer/components/Sidebar.tsx` | `https://github.com/AndyMik90/Auto-Claude/issues` | Update repo URL |
| | `https://github.com/sponsors/AndyMik90` | Update or remove |

---

## Phase 5: Internal References (User-Agent, Repo Constants)

| File | Hiện tại | Thay đổi |
|------|----------|----------|
| `src/main/ipc-handlers/github/utils.ts` | `'User-Agent': 'Auto-Claude-UI'` | `'{New-Name}-UI'` |
| `src/main/app-updater.ts` | `'User-Agent': 'Auto-Claude/...'` | `'{New-Name}/...'` |
| `src/main/app-updater.ts:33` | `const GITHUB_REPO = 'Auto-Claude'` | Update |
| `scripts/download-prebuilds.cjs:14` | `'AndyMik90/Auto-Claude'` | Update repo |
| `scripts/download-prebuilds.cjs:63` | `'User-Agent': 'Auto-Claude-Installer'` | Update |

---

## Phase 6: App Icons (Visual Branding)

Cần design lại toàn bộ icons trong `apps/frontend/resources/`:

| File | Format | Kích thước |
|------|--------|-----------|
| `resources/icon.icns` | macOS | Multi-size |
| `resources/icon.ico` | Windows | Multi-size |
| `resources/icon.png` | PNG | Full resolution |
| `resources/icon-256.png` | PNG | 256x256 |
| `resources/icons/16x16.png` | PNG | 16x16 |
| `resources/icons/32x32.png` | PNG | 32x32 |
| `resources/icons/48x48.png` | PNG | 48x48 |
| `resources/icons/64x64.png` | PNG | 64x64 |
| `resources/icons/128x128.png` | PNG | 128x128 |
| `resources/icons/256x256.png` | PNG | 256x256 |
| `resources/icons/512x512.png` | PNG | 512x512 |

---

## Phase 7: Color Theme (Optional)

Nếu muốn thay đổi default color palette để phù hợp brand mới:

| File | Mục đích |
|------|----------|
| `src/shared/constants/themes.ts` | Đổi tên/description themes, preview colors |
| `src/renderer/styles/globals.css` (lines 110-224) | Đổi default light/dark CSS variables |
| `src/renderer/styles/globals.css` (lines 230-1028) | Đổi từng theme variant |
| `src/renderer/lib/terminal-theme.ts` | Đổi terminal theme cho phù hợp |
| `src/shared/constants/config.ts` | Đổi default theme nếu cần |

---

## Phase 8: Docs & Scripts (Low Priority)

| File | Thay đổi |
|------|----------|
| `apps/frontend/.env.example` | Comment text |
| `apps/frontend/README.md` | Title, description |
| `apps/frontend/CONTRIBUTING.md` | Title, repo URLs |
| `scripts/postinstall.cjs` | Comment text |

---

## Checklist thực hiện

- [ ] Chọn tên mới
- [ ] Phase 1: Package & build config
- [ ] Phase 2: i18n (EN + FR)
- [ ] Phase 3: Hardcoded strings trong components
- [ ] Phase 4: Sidebar links
- [ ] Phase 5: Internal references
- [ ] Phase 6: Design + replace app icons
- [ ] Phase 7: Color theme (nếu cần)
- [ ] Phase 8: Docs & scripts
- [ ] Build test: `cd apps/frontend && npm run build`
- [ ] Typecheck: `cd apps/frontend && npm run typecheck`
- [ ] Visual QA: chạy app kiểm tra tất cả screens có branding
