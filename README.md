# C# Scripting in Unity — Course Project

Authored HTML course built from `../course_template`, matching the structure of the
existing C# courses (`csharp`, `csharp_int`, `csharp_adv`).

- **Title:** C# Scripting in Unity
- **Difficulty:** intermediate (a few advanced lessons)
- **Prerequisite:** C# fundamentals (the `csharp` "Introduction to C#" course)
- **Positioning:** focuses on the **C# scripting** side of Unity. It *complements* Ray's
  engine/editor-focused Unity courses (Fundamentals / Intermediate / Advanced) rather than
  repeating them — here the star is the script, not the editor.
- **Intended deploy:** Netlify (suggested name `rays-csharp-unity`), then add a link on
  `rayhome/index.html` and `rayhome/search.html` under "Computer Programming Topics"
  (next to the other C# courses).

## Status

- [x] Folder scaffolded, template assets copied (`styles/`, `js/`, `tools/`, `images/`, `assets/`, favicons)
- [x] `git init` done
- [x] `course-config.json` written (5 modules × 3 = 15 lessons)
- [x] `index.html` written (homepage with all 5 module cards, prerequisites, resources)
- [x] **Lessons 01–15 — ALL WRITTEN & VALIDATED** (2026-08-07). 31/31 Mermaid diagrams pass the
  jsdom+mermaid checker; nav chain index→01→…→15→index verified; no `[placeholders]` or `language-python`.
  Code accuracy grounded against the live Unity 6 API via MCP (e.g. `linearVelocity`, `Awaitable`,
  `ObjectPool<T>`, `Instantiate<T>`, `TryGetComponent`). Capstone = "Coin Rush", integrating all 5 modules.
- [ ] Deploy to Netlify (suggested name `rays-csharp-unity`)
- [ ] Add links on `rayhome/index.html` + `rayhome/search.html` under "Computer Programming Topics"

## Syllabus (15 lessons)

**Module 1 — Unity's C# Model**
1. 1.1 MonoBehaviour and the Component Model — `lesson_01.html`
2. 1.2 The Event Function Lifecycle (Awake/Start/Update/FixedUpdate/OnDestroy) — `lesson_02.html`
3. 1.3 Accessing GameObjects and Components (GetComponent, references, [SerializeField]) — `lesson_03.html`

**Module 2 — Gameplay Scripting**
4. 2.1 Input and Movement (Input System, Transform, Time.deltaTime) — `lesson_04.html`
5. 2.2 Physics and Collisions (Rigidbody, OnCollision/OnTrigger) — `lesson_05.html`
6. 2.3 Instantiating and Destroying Objects (prefabs, lifecycle) — `lesson_06.html`

**Module 3 — Structuring Game Code**
7. 3.1 ScriptableObjects for Data — `lesson_07.html`
8. 3.2 Events and Decoupling (C# events, UnityEvents, event channels) — `lesson_08.html`
9. 3.3 Coroutines and Async in Unity (IEnumerator/yield vs async/await) — `lesson_09.html`

**Module 4 — Systems and Managers**
10. 4.1 Game State and Managers (singletons, scene management) — `lesson_10.html`
11. 4.2 UI Scripting (uGUI / UI Toolkit) — `lesson_11.html`
12. 4.3 Saving and Loading (JSON serialization, PlayerPrefs) — `lesson_12.html`

**Module 5 — Quality and Performance**
13. 5.1 Unity Performance and Memory (avoid GC in Update, caching, object pooling) — `lesson_13.html`
14. 5.2 Debugging and the Unity Test Framework — `lesson_14.html`
15. 5.3 Capstone Project (a complete gameplay system) — `lesson_15.html`

Cross-references to reuse: OOP (intro), events/LINQ + JSON + unit testing (intermediate),
GC/pooling/performance (advanced) — recontextualized for Unity.

## Build conventions (same as the other C# courses)

- One lesson per HTML file, copied structure from `course_template/lesson_template.html`:
  nav, breadcrumb, sticky TOC, learning objectives, sections with cards/tables/Mermaid,
  worked code examples with copy buttons, a hands-on exercise (hint + solution `<details>`),
  a 3-question quiz, summary, prev/next lesson nav.
- Code blocks use `language-csharp` (Unity C#). Escape `<`, `>`, `&` as `&lt;`, `&gt;`, `&amp;`
  inside `<pre><code>`.
- **Mermaid rule:** never put raw `<`/`>` inside Mermaid node/edge labels (they render as HTML
  tags and break the diagram — parser still passes). Use Unicode `⟨ ⟩` for generics, or reword.
  Keep `<br/>` only for line breaks.
- Validate every lesson's diagrams with the checker (rebuild it if the scratchpad was cleared):
  - Deps: `npm install mermaid@10 jsdom` in a scratch dir
  - Script `check3.mjs`: loads each `lesson_*.html`/`index.html` via jsdom, runs
    `mermaid.parse()` on every `.mermaid` block, AND flags any `<`/`>` inside a quoted label.
  - Run: `node check3.mjs /home/practicalace/projects/csharp_unity`
- Working style: build one lesson at a time; pause for review (user says "proceed").
- After each lesson: check nav chain (index → 01 → … → 15 → index) and no leftover
  `[placeholders]` / `language-python`.

## To resume

All 15 lessons are complete. Next action is **deployment**: publish to Netlify (suggested name
`rays-csharp-unity`), then add links on `rayhome/index.html` + `rayhome/search.html` under
"Computer Programming Topics" (next to the other three C# courses). See the memory note
`csharp-course-project` for the broader context and `unity-mcp-connection` for the Unity MCP setup state.
