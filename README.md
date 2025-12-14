````markdown
# CitySkylineModTemplate (Cities: Skylines 1)

A **.NET / C# mod template** for **Cities: Skylines (1)**, designed to be installed via `dotnet new` so you can scaffold a new CS1 mod project quickly and consistently.

This repo is the “template source” (and also contains a solution you can open in Rider/VS to develop the template itself).

---

## What this is for

- Create a new **Cities: Skylines 1** mod project in seconds
- Reuse a clean, repeatable structure (entry point + loading hooks + game DLL refs)
- A solid base for gameplay systems (e.g., Chirper/news-style systems) without redoing setup every time

---

## Requirements

- **Cities: Skylines 1** installed (Steam)
- **.NET SDK** (for `dotnet new` + build)
- IDE: **JetBrains Rider** / Visual Studio / VS Code

> CS1 modding relies on the game’s managed assemblies (e.g., `ICities.dll`, `UnityEngine.dll`), so your project must reference your local game install.

---

## Repo layout

At the repo root:

- `CitySkylineModTemplate/` – the template project/source
- `CitySkylineModTemplate.sln` – solution for editing the template
- `.gitignore`

---

## Install the template (local)

Clone the repo, then install the template from the folder that contains the template config (usually the repo root, or the inner project folder if `.template.config/` lives there):

```bash
git clone <your-repo-url>
cd CitySkylineModTemplate
dotnet new install . --force
````

Verify it’s installed:

```bash
dotnet new --list
```

Find the template’s **Short Name** in that list (you’ll use it next).

> Update/reinstall later:

```bash
dotnet new uninstall .
dotnet new install . --force
```

---

## Create a new mod project from the template

From anywhere:

```bash
mkdir MyCS1Mod
cd MyCS1Mod
dotnet new <SHORT_NAME_FROM_LIST> --name MyCS1Mod
```

If you’re not sure what parameters the template supports:

```bash
dotnet new <SHORT_NAME_FROM_LIST> --help
```

---

## Point references to Cities: Skylines Managed DLLs

Your generated mod project must reference the game’s managed assemblies, typically located at:

### Windows (Steam default)

`...\Steam\steamapps\common\Cities_Skylines\Cities_Data\Managed\`

### macOS (Steam)

`~/Library/Application Support/Steam/steamapps/common/Cities_Skylines/Cities_Data/Managed/`

### Linux (Steam)

`~/.steam/steam/steamapps/common/Cities_Skylines/Cities_Data/Managed/`

How to set it depends on how your template is written:

* if you have a central props/setting file → set the Managed path there
* otherwise → update `HintPath` values in the `.csproj` references

You’ll know it’s correct when the project resolves `ICities` and `UnityEngine` types.

---

## Build

```bash
dotnet build
```

Your mod DLL will be generated under something like:

`bin/Debug/.../YourMod.dll`

---

## Install the mod for local testing

Copy your built DLL into your local Mods folder:

### Windows

`%LOCALAPPDATA%\Colossal Order\Cities_Skylines\Addons\Mods\YourModName\`

### macOS

`~/Library/Application Support/Colossal Order/Cities_Skylines/Addons/Mods/YourModName/`

### Linux

`~/.local/share/Colossal Order/Cities_Skylines/Addons/Mods/YourModName/`

Then in-game:

**Content Manager → Mods → Enable your mod**

---

## Troubleshooting

### macOS: `getcwd() failed: Operation not permitted` / `UnauthorizedAccessException` during `dotnet new install`

This is usually macOS privacy/permission related (some folders are “special” even if they look normal).

Fixes that often work:

* run `dotnet new install .` from a **normal writable folder** under your home directory (avoid protected/synced locations)
* give **Terminal** / your IDE **Full Disk Access**:
  System Settings → Privacy & Security → Full Disk Access

You already noticed “parent folder works” — that’s a strong sign the original folder had restricted permissions.

---

## Contributing

PRs are welcome, especially for:

* cleaner cross-platform reference handling
* better default logging / diagnostics
* more mod examples (kept optional and removable)

---

## License

Add a license you’re happy with (MIT is common for templates).
If you haven’t chosen yet, you can add `LICENSE` later.

---

## Credits

* Cities: Skylines modding API (`ICities.dll`)
* Unity engine runtime types (`UnityEngine.dll`)

```

If you want, paste the output of `dotnet new --list` (just the line that shows this template) and I’ll replace `<SHORT_NAME_FROM_LIST>` with the exact short name and tighten the install path section to match your repo’s actual `.template.config` location.
```
