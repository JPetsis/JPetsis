```text
╔══════════════════════════════════╗
║                                  ║
║    John Petsis                   ║
║    Systems · Languages           ║
║                                  ║
╚══════════════════════════════════╝
```

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="https://img.shields.io/badge/-Systems%20%26%20Languages%20Engineer-1a1a2e?style=for-the-badge&labelColor=0f3460"
  />
  <img
    alt="tagline"
    src="https://img.shields.io/badge/-Systems%20%26%20Languages%20Engineer-1a1a2e?style=for-the-badge&labelColor=0f3460"
  />
</picture>

I build **programming language infrastructure** and **full-stack systems** — from multi-tier pattern matching engines to production web applications.

- **libsnobol4** — A high-performance SNOBOL4 string-processing engine in C with computed-goto dispatch, 10-tier search acceleration (BMH, DFA automaton, trie), start-byte bitmap filtering, and SIMD-ready architecture. Pattern matching, template substitution, zero-allocation literal matching.
- **cadence** — A multi-tenant driving school management platform in Go, using chi, PostgreSQL, HTMX, and TailwindCSS.
- Ask me about **compilers, language runtimes, search engines, or building web apps with Go & Laravel.**

---



## Tech

<table>
  <tr>
    <th colspan="2" align="left">Languages</th>
  </tr>
  <tr>
    <td>
      <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white"/>
      <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"/>
      <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white"/>
      <img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white"/>
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white"/>
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white"/>
      <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white"/>
    </td>
  </tr>
</table>

<table>
  <tr>
    <th colspan="2" align="left">Frameworks & Tools</th>
  </tr>
  <tr>
    <td>
      <img src="https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white"/>
      <img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black"/>
      <img src="https://img.shields.io/badge/Inertia.js-9553E9?style=for-the-badge&logo=inertia&logoColor=white"/>
      <img src="https://img.shields.io/badge/HTMX-3366CC?style=for-the-badge&logo=htmx&logoColor=white"/>
      <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white"/>
      <img src="https://img.shields.io/badge/shadcn/ui-000000?style=for-the-badge&logo=shadcnui&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/>
      <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white"/>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
      <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white"/>
      <img src="https://img.shields.io/badge/PHPUnit-366488?style=for-the-badge&logo=phpunit&logoColor=white"/>
      <img src="https://img.shields.io/badge/sqlc-16213E?style=for-the-badge&logo=go&logoColor=white"/>
    </td>
  </tr>
</table>

---

## Featured Project

### <picture><source media="(prefers-color-scheme: dark)" srcset="https://img.shields.io/badge/libsnobol4-16213E?style=for-the-badge&labelColor=0f3460&logo=c&logoColor=white"/><img src="https://img.shields.io/badge/libsnobol4-0f3460?style=for-the-badge&logo=c&logoColor=white"/></picture>

A **high-performance SNOBOL4** string-processing engine in C — a PCRE alternative with **computed-goto dispatch, 10-tier search acceleration, DFA automaton, and trie-based alternation matching**.

```
┌──────────────────────────────────────────────────────────────────┐
│  SNOBOL4 VM — computed-goto dispatch (15-30% over switch)        │
│  10-tier search: BMH · bitmap · trie · DFA automaton · search-VM │
│  Start-byte bitmap · min-length pre-check · literal fast-path    │
└──────────────────────────────────────────────────────────────────┘
```

| Feature                   | Detail                                                                                                            |
|---------------------------|-------------------------------------------------------------------------------------------------------------------|
| **Dispatch**              | Computed-goto opcode dispatch (15-30% faster). MSVC switch fallback.                                              |
| **Search Acceleration**   | 10-tier pipeline: BREAK/SPAN → literal-only → literal-prefix (BMH) → bitmap → alt-literals trie → search-VM → DFA automaton → SIMD NFA → general VM |
| **Platforms**             | macOS ARM64/Intel, Linux AArch64/x86-64/ARMv7/RISC-V, Windows x86-64                                              |
| **Bindings**              | PHP (stable) — Python reference in progress                                                                       |
| **Pattern Engine**        | Backtracking VM with computed-goto dispatch, catastrophic backtracking protection, compact choice stack, UTF-8 with full BMP case folding |
| **Template Substitution** | Compiled C VM instructions — captures, formatting, table lookups                                                  |
| **CI**                    | Native runners: macOS ARM64/x86-64, Linux AArch64/x86-64/ARMv7/RISC-V, Windows x86-64                            |
| **Distro**                | Homebrew (macOS), PIE (PHP), GitHub Releases                                                                      |

```c
// One-shot convenience API
snobol_match_result_t *r = snobol_match(
    "'abc' ARB 'def'", 15, "xyz abc def xyz", 15, 0
)
```

[ ![CI](https://img.shields.io/github/actions/workflow/status/JPetsis/libsnobol4/ci-core.yml?label=CI&logo=github) ](https://github.com/JPetsis/libsnobol4)
[ ![PHP](https://img.shields.io/github/actions/workflow/status/JPetsis/libsnobol4/ci-php.yml?label=PHP%20binding&logo=php) ](https://github.com/JPetsis/libsnobol4)
[ ![Sanitizers](https://img.shields.io/github/actions/workflow/status/JPetsis/libsnobol4/sanitizers.yml?label=sanitizers&logo=github) ](https://github.com/JPetsis/libsnobol4)

---

## Projects

### cadence
<p>
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/HTMX-3366CC?style=for-the-badge&logo=htmx&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white"/>
  <img src="https://img.shields.io/badge/chi_router-0077B5?style=for-the-badge&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/sqlc-16213E?style=for-the-badge&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
</p>

A multi-tenant driving school management platform — scheduling engine, instructor/student/vehicle management, role-based auth, session management, and contact forms.


---

## GitHub

[![GitHub followers](https://img.shields.io/github/followers/JPetsis?style=for-the-badge&logo=github&label=Followers&color=1a1a2e)](https://github.com/JPetsis)
[![GitHub User's stars](https://img.shields.io/github/stars/JPetsis?style=for-the-badge&logo=github&label=Stars&color=1a1a2e)](https://github.com/JPetsis)
