# CitySkylineModTemplate (Cities: Skylines 1)

A beginner-friendly **project template** for creating **Cities: Skylines (1)** mods in **C#**.

## How to identify the template

When you search inside your IDE, look for:

- **Template name:** `City Skyline 1 Mod Template`
- **Keyword / short name:** `cs1mod`
- **Category/Tags:** Cities: Skylines / Mod

---

## Install in JetBrains Rider (no command line)

1. Open **Rider** → **New Solution** (or **New Project**).
2. Click **More Templates** (left side).
3. Click **Install Template**.
4. Select the **template folder** (the folder that contains `.template.config/template.json`), or select a packaged template file if provided.
5. When the template path appears, click **Reload**. :contentReference[oaicite:0]{index=0}

After reload, your template will appear in the template list.

---

## Use in JetBrains Rider

1. Open **New Solution / New Project**.
2. Search **`City Skyline 1 Mod Template`** (or type **`cs1mod`**).
3. Select it → set **Name** and **Location**.
4. If Rider shows extra options (template parameters), fill them in (or keep defaults).
5. Click **Create**. :contentReference[oaicite:1]{index=1}

---

## Install in Visual Studio 2022 (no command line)

> Visual Studio supports templates either as **VSIX** (recommended) or as a **user template ZIP** in a known folder.

### Option A: Install the VSIX (recommended)
1. Download the template’s `.vsix` file (for example from the project Releases).
2. **Double-click** the `.vsix` file and follow the installer steps.
3. Restart Visual Studio. :contentReference[oaicite:2]{index=2}

### Option B: Install as a user template ZIP
1. Download the template `.zip` file (it must be a Visual Studio template ZIP that contains a `.vstemplate` file).
2. Copy the ZIP into this folder:
   - `%USERPROFILE%\Documents\Visual Studio 2022\Templates\ProjectTemplates`
3. Restart Visual Studio. :contentReference[oaicite:3]{index=3}

---

## Use in Visual Studio 2022

1. Open **File → New → Project**.
2. In the search box, type:
   - `City Skyline 1 Mod Template` (recommended), or
   - `cs1mod`
3. Select the template → set **Project name** and **Location** → **Create**.

> If you used the ZIP method, Visual Studio finds user templates from the ProjectTemplates folder and then lists them in the New Project dialog. :contentReference[oaicite:4]{index=4}

---

## After creation: set your Cities: Skylines game paths (if needed)

The generated project includes settings for:
- **CS1ManagedPath** (Cities: Skylines “Managed” DLL folder)
- **ModsRootPath** (your local Mods folder)

If you’re not on macOS (or your Steam library is in a different location), update these paths in the generated project files (usually in the `.csproj` or a props/settings file created by the template).

---

## Build and run

- **Rider:** Build the solution (Build button / Build menu), then launch the game and enable the mod in **Content Manager → Mods**.
- **Visual Studio:** Build the solution (Build Solution), then launch the game and enable the mod in **Content Manager → Mods**.
