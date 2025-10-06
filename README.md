# Common Editor Config

**A unified, language-aware editor and formatter configuration set for modern development.**  
This repository provides a consistent, professional, and cross-platform code style setup for a wide range of programming languages and text formats — ensuring clean, readable, and standardized source code across editors and teams.

> 📦 Repository: [https://github.com/jonas-merkle/Common-Editor-Config](https://github.com/jonas-merkle/Common-Editor-Config)  
> 🧾 License: [LGPLv3](./LICENSE)  
> 🧑‍💻 Author: [Jonas Merkle](https://github.com/jonas-merkle)

---

[![License: LGPL v3](https://img.shields.io/badge/License-LGPLv3-blue.svg)](./LICENSE)
[![Semantic Versioning](https://img.shields.io/badge/SemVer-2.0.0-brightgreen.svg)](https://semver.org/)
[![GitHub release](https://img.shields.io/github/v/release/jonas-merkle/Common-Editor-Config?include_prereleases&sort=semver)](https://github.com/jonas-merkle/Common-Editor-Config/releases)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/jonas-merkle/Common-Editor-Config/release-version-inject.yml?branch=main)](https://github.com/jonas-merkle/Common-Editor-Config/actions)

---

## 📋 Overview

This project bundles **three key configuration files** that define consistent code style and formatting rules across languages and tools:

| File                                 | Purpose                                                         | Primary Scope                                           |
| ------------------------------------ | --------------------------------------------------------------- | ------------------------------------------------------- |
| [`.editorconfig`](./.editorconfig)   | Universal base configuration supported by most editors and IDEs | Indentation, line endings, final newline, trimming      |
| [`.clang-format`](./.clang-format)   | Language-specific style for C / C++ / Objective-C               | Brace style, indentation, column width, spacing         |
| [`.prettierrc.js`](./.prettierrc.js) | Prettier configuration for web and scripting languages          | JavaScript, TypeScript, JSON, YAML, Markdown, HTML, CSS |

Together, these files enforce **style consistency** across mixed-language repositories — from C/C++ backend code to web frontends, C#, LaTeX, and data/config files.

---

## 🎯 Goals

- 🧩 Provide a **shared, editor-agnostic baseline** for formatting and style
- 🧹 Enforce **clean, readable, and maintainable code** automatically
- 🕹️ Work **out of the box** in VS Code, JetBrains IDEs, Visual Studio, Vim, Emacs, Sublime, etc.
- 🔄 Ensure **cross-platform consistency** (Linux line endings by default)
- 💡 Serve as a **foundation for team or organization-wide style guides**

---

## 📦 Included Configurations

### 1. `.editorconfig`

Defines universal, language-aware formatting rules such as indentation style, character encoding, line endings, and whitespace trimming.

**Key highlights:**

- Default: **UTF-8**, **LF** line endings, **4-space indentation**
- **2-space indentation** for web files, markup, YAML, JSON, Markdown, LaTeX, etc.
- **Final newline enforced** for POSIX compatibility
- **Trailing whitespace trimmed** (except Markdown/LaTeX/CSV)
- Includes **language-specific overrides** for:
  - C / C++
  - C#
  - JavaScript / TypeScript
  - HTML / CSS / SCSS / Less
  - JSON / YAML / TOML
  - Markdown, LaTeX
  - Python, Shell, PowerShell
  - CSV, SQL, XML, etc.

📄 → [View full `.editorconfig`](./.editorconfig)

---

### 2. `.clang-format`

Provides a **C/C++ style guide** compatible with the `.editorconfig` base rules.

**Highlights:**

- Based on **LLVM style**
- **4-space indentation**, **no tabs**
- **Column limit: 100**
- Brace style: `Attach`
- Consistent pointer/reference alignment (`Left`)
- Includes logical sorting of includes
- C++20 compatible (`Standard: c++20`)
- Keeps **Linux-style LF** endings (`UseCRLF: false`)

📄 → [View full `.clang-format`](./.clang-format)

---

### 3. `.prettierrc.js`

Defines **Prettier** configuration for web and scripting languages.

**Highlights:**

- **100-character** print width
- **2-space indentation**
- Always use semicolons (`semi: true`)
- Double quotes by default (`singleQuote: false`)
- Trailing commas (`trailingComma: "all"`)
- LF endings enforced (`endOfLine: "lf"`)
- Language-specific overrides for:
  - Markdown (`proseWrap: "preserve"`)
  - JSON / YAML / CSS / HTML / JS / TS files
- Supports version header comments (`@VERSION@` auto-replaced via CI)

📄 → [View full `.prettierrc.js`](./.prettierrc.js)

---

## 🚀 Usage

### 🧩 1. Add the configuration files to your project

Add the configuration files as a git submodule:

```bash
git submodule add https://github.com/jonas-merkle/Common-Editor-Config.git common-editor-config
```

Or simply copy the configuration files into your project root:

```bash
wget https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/main/.editorconfig
wget https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/main/.clang-format
wget https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/main/.prettierrc.js
```

---

### 🛠️ 2. Enable EditorConfig in your IDE

Most modern IDEs and editors support EditorConfig natively.
If not, install the appropriate plugin:

- **VS Code** – [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- **JetBrains IDEs** – built-in
- **Visual Studio** – built-in since 2017
- **Vim** – [editorconfig-vim](https://github.com/editorconfig/editorconfig-vim)
- **Sublime Text** – [EditorConfig plugin](https://packagecontrol.io/packages/EditorConfig)

---

### ⚙️ 3. Integrate with your build or CI pipeline

You can automatically enforce formatting via:

- **clang-format** (`clang-format -i <file>`)
- **prettier** (`prettier --write .`)
- Pre-commit hooks using [`pre-commit`](https://pre-commit.com/) or Husky
- CI style checks with `clang-format --dry-run` and `prettier --check`

---

## 🧪 Example Integration

Example **VS Code** settings snippet:

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "files.eol": "\n",
  "[cpp]": { "editor.defaultFormatter": "ms-vscode.cpptools" },
  "[csharp]": { "editor.defaultFormatter": "ms-dotnettools.csharp" }
}
```

---

## 🌍 Supported Languages

| Category | Languages / Formats               |
| -------- | --------------------------------- |
| Systems  | C, C++, C#, Bash, PowerShell      |
| Web      | HTML, CSS, SCSS, JS, TS, Vue      |
| Config   | JSON, YAML, TOML, INI             |
| Docs     | Markdown, reStructuredText, LaTeX |
| Data     | CSV, TSV, SQL                     |
| Misc     | XML, SVG, project configs         |

---

## 🧰 Recommended Companion Tools

- **clang-format** (C/C++/ObjC): [https://clang.llvm.org/docs/ClangFormat.html](https://clang.llvm.org/docs/ClangFormat.html)
- **Prettier** (JS/TS/Web): [https://prettier.io](https://prettier.io)
- **EditorConfig CLI** (validate or lint configs): [https://editorconfig.org](https://editorconfig.org)
- **.NET Roslyn Analyzers** for C#: [https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/overview](https://learn.microsoft.com/en-us/dotnet/fundamentals/code-analysis/overview)

---

## 🧭 Versioning and GitHub Actions Integration

This repository uses **[Semantic Versioning 2.0.0](https://semver.org/)** and **Git tags** to manage releases.

Each tagged release triggers a **GitHub Actions workflow** (`release-version-inject.yml`) that:

1. Detects the version tag (e.g., `v1.2.3`)
2. Replaces every `@VERSION@` token in the configuration headers
3. Generates a **`dist/`** folder with versioned files
4. Uploads them as both build **artifacts** and **release assets**

### 🔖 Example Header Section

Each configuration includes this header template:

```text
# Common Editor Config
# Repository : https://github.com/jonas-merkle/Common-Editor-Config
# License    : LGPLv3
# Versioning : Semantic Versioning (SemVer) via Git tags
# Version    : @VERSION@
```

When a release is published, `@VERSION@` is automatically replaced by the actual tag (e.g. `v1.0.0`).

---

### 🏷️ How to Get a Versioned Release

Download the pre-built, version-stamped configuration files from any GitHub release:

```bash
# Get latest version automatically
TAG=$(curl -s https://api.github.com/repos/jonas-merkle/Common-Editor-Config/releases/latest | jq -r .tag_name)
curl -LO "https://github.com/jonas-merkle/Common-Editor-Config/releases/download/${TAG}/common-editor-config-${TAG}.zip"
unzip "common-editor-config-${TAG}.zip"

# Or fetch individual files for a specific tag
curl -LO "https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/v1.0.0/.editorconfig"
curl -LO "https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/v1.0.0/.clang-format"
curl -LO "https://raw.githubusercontent.com/jonas-merkle/Common-Editor-Config/v1.0.0/.prettierrc.js"
```

---

## ⚖️ License

This project is licensed under the **GNU Lesser General Public License v3.0 (LGPLv3)**.
You are free to use, modify, and distribute these configurations under the same terms.

See the [LICENSE](./LICENSE) file for details.

---

## 💬 Feedback & Support

If you find this project useful or have suggestions for improvement:

- Open an [Issue](https://github.com/jonas-merkle/Common-Editor-Config/issues)
- Submit a [Pull Request](https://github.com/jonas-merkle/Common-Editor-Config/pulls)
- Or ⭐ **star the repository** to support ongoing development!

---

**© 2025 Jonas Merkle — Licensed under the LGPLv3**
