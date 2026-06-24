# User guide for the newly installed design skills

This guide explains when to use the skills installed on 2026-06-23 and how to ask for them effectively. It is written for users who are new to skills and want a practical decision guide, not a raw catalog.


## The skill mental model

A skill is a reusable expert workflow that the agent can discover and apply when your request matches its description. The host's main recommendation is to treat skills as focused building blocks: use each skill for a clear job, combine them only when the workflow really needs it, and keep verification separate from creation whenever possible.

The host groups skills into four useful types:

| Type | What it does | How that applies here |
| --- | --- | --- |
| Utility skill | Performs one focused task or applies one body of expertise. | `shadcn`, `material-3`, `swiftui-skills`, `building-native-ui`, and the GSAP skills. |
| Verification skill | Checks whether the output meets a bar. | Use `ui-ux-pro-max` or `frontend-design` as review passes after a UI is built. |
| Data enrichment skill | Pulls in external or project context. | None of these are primarily data-enrichment skills. They are mostly design and implementation guidance. |
| Orchestration skill | Chains multiple focused skills into a workflow. | Use manual orchestration by asking for a sequence, such as "use `frontend-design`, then `shadcn`, then `gsap-scrolltrigger`." |

The host also emphasizes trigger quality. A good skill trigger says who it serves and when it should run. In normal use, this means your prompt should name the medium, framework, style target, and desired output.

Good:

```text
Build a React dashboard using shadcn/ui. Use the dashboard skill for the visual system and use gsap-scrolltrigger only if the scroll behavior needs animation.
```

Weak:

```text
Make it better.
```

## Quick decision table

| If you are doing this | Start with | Add these when needed |
| --- | --- | --- |
| Building or redesigning a web page or web app | `frontend-design` | `shadcn`, `premium-frontend-ui`, `minimalist-ui`, `industrial-brutalist-ui`, GSAP skills |
| Building a shadcn/ui app or component | `shadcn` | `frontend-design`, `dashboard`, `ui-ux-pro-max`, GSAP skills |
| Creating a data-heavy dashboard | `dashboard` | `shadcn`, `ui-ux-pro-max`, `gsap-performance` |
| Doing broad UI/UX critique or improvement | `ui-ux-pro-max` | `frontend-design`, platform-specific skills |
| Adding animation to any web UI | `gsap-core` | `gsap-react`, `gsap-scrolltrigger`, `gsap-timeline`, `gsap-performance` |
| Building React or Next.js animations | `gsap-react` | `gsap-core`, `gsap-scrolltrigger`, `gsap-performance` |
| Building scroll-driven animation | `gsap-scrolltrigger` | `gsap-timeline`, `gsap-performance` |
| Creating a polished marketing or immersive web experience | `premium-frontend-ui` | `frontend-design`, GSAP skills |
| Making a quiet, refined, document-like interface | `minimalist-ui` | `frontend-design`, `shadcn` |
| Making a raw tactical, industrial, or editorial interface | `industrial-brutalist-ui` | `frontend-design`, GSAP skills |
| Designing mobile app screens or flows | `mobile-app-ui-design` | `building-native-ui`, `swiftui-skills`, `material-3` |
| Building an Expo app | `building-native-ui` | `mobile-app-ui-design`, `material-3`, GSAP only for web targets |
| Building SwiftUI | `swiftui-skills` | `mobile-app-ui-design` for product UX direction |
| Building Material Design or Android Compose UI | `material-3` | `mobile-app-ui-design`, `ui-ux-pro-max` |

## How to ask for a skill

You can name the skill directly, or describe the work in terms that match the skill.

Direct:

```text
Use `frontend-design` to create three visual directions for this analytics page before coding.
```

Natural language:

```text
Create a distinctive production-quality web dashboard. Avoid generic SaaS styling and give me a strong visual direction before implementation.
```

For best results, include:

| Prompt ingredient | Example |
| --- | --- |
| Product type | "B2B analytics dashboard", "mobile finance app", "developer docs site" |
| Framework | "React + shadcn/ui", "Expo Router", "SwiftUI", "Jetpack Compose" |
| User goal | "compare campaigns quickly", "track order status", "present a product launch" |
| Style direction | "quiet editorial", "industrial", "premium immersive", "Material 3" |
| Constraints | "accessible", "mobile-first", "no heavy animation", "prefers reduced motion" |
| Verification request | "review for accessibility, responsiveness, and visual hierarchy after implementation" |

## Skill-by-skill guide

### `frontend-design`

Use this for the first design pass on web pages, components, apps, and redesigns. It is best when you want a distinctive visual direction rather than a generic implementation.

Best for:

| Use case | Why it fits |
| --- | --- |
| New web page or app UI | It forces aesthetic direction, typography, palette, layout, and a memorable signature idea. |
| Redesigning generic output | It explicitly pushes away from templated AI aesthetics. |
| Picking between design directions | It can brainstorm multiple visual approaches before code is written. |

Example prompts:

```text
Use `frontend-design` to design a serious but memorable SaaS dashboard. Give me a compact design plan first: palette, typography, layout, and signature interaction.
```

```text
This page feels generic. Use `frontend-design` to critique it, then implement a stronger direction without changing the product scope.
```

Pair it with:

| Pair with | When |
| --- | --- |
| `shadcn` | You are implementing in a shadcn/ui project. |
| `dashboard` | The interface is data-heavy and operational. |
| `premium-frontend-ui` | The page needs high-end motion, hero composition, and immersive craft. |
| GSAP skills | The direction depends on deliberate animation. |

### `shadcn`

Use this whenever a project uses shadcn/ui, a `components.json` file, component registries, or shadcn presets. It is for correct component usage, project setup, component selection, styling, and composition.

Best for:

| Use case | Why it fits |
| --- | --- |
| Adding shadcn components | It knows the CLI patterns and component rules. |
| Fixing broken shadcn composition | It covers Radix/base component structure, triggers, tabs, forms, icons, and styling. |
| Starting from a preset | It handles `shadcn init`, presets, and registry workflows. |

Example prompts:

```text
Use `shadcn` to build this settings panel with tabs, forms, validation states, and accessible labels.
```

```text
This shadcn dialog trigger is not working. Use `shadcn` to inspect the component structure and fix it.
```

Pair it with:

| Pair with | When |
| --- | --- |
| `frontend-design` | You need a visual direction before component implementation. |
| `dashboard` | You are building an operational dashboard. |
| `ui-ux-pro-max` | You want a final UI/UX review. |

### `dashboard`

Use this for data-heavy dashboards with strong hierarchy, modular grids, and a dark cloud-platform feel. It is a visual system skill, not a data analysis skill.

Best for:

| Use case | Why it fits |
| --- | --- |
| Metrics dashboards | It emphasizes scanability and hierarchy. |
| Admin panels | It fits dense operational tools. |
| Cloud or developer platforms | It has a dark, modular, technical aesthetic. |

Example prompts:

```text
Use `dashboard` to design a dark operational dashboard for support managers. Prioritize hierarchy, dense tables, and clear alert states.
```

```text
Use `dashboard` plus `shadcn` to implement a metrics overview with filters, cards, a table, and empty/loading/error states.
```

Avoid using it for:

| Avoid when | Use instead |
| --- | --- |
| Editorial landing pages | `frontend-design` or `premium-frontend-ui` |
| Mobile-native app screens | `mobile-app-ui-design` |
| Warm minimal document-style tools | `minimalist-ui` |

### `ui-ux-pro-max`

Use this as a broad UI/UX planning, review, and improvement skill across web and mobile. It covers accessibility, layout, typography, color, interaction states, navigation, forms, charts, and multiple stacks.

Best for:

| Use case | Why it fits |
| --- | --- |
| Final UI review | It works well as a verification-style pass. |
| Accessibility and responsive checks | It has explicit rule categories for these. |
| Choosing patterns across many stacks | It spans React, Next.js, Vue, Svelte, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui, and HTML/CSS. |

Example prompts:

```text
Use `ui-ux-pro-max` as a verifier. Review this UI for accessibility, responsive behavior, touch targets, forms, charts, and interaction states. Return pass/fail issues with concrete fixes.
```

```text
Use `ui-ux-pro-max` to improve this mobile onboarding flow. Keep the product goal unchanged and focus on hierarchy, friction, and error states.
```

Important: the install CLI flagged this skill with a high Gen security risk assessment. Review its recommendations before applying broad changes automatically.

### GSAP skills

Use the GSAP family when animation is part of the product experience. The host's broader advice applies strongly here: keep each skill focused. Do not ask one animation skill to solve every animation problem.

| Skill | Use when |
| --- | --- |
| `gsap-core` | Basic GSAP tweens, easing, stagger, transforms, responsive animation, or choosing GSAP as the animation library. |
| `gsap-react` | React or Next.js animation, `useGSAP`, refs, cleanup, and client-only behavior. |
| `gsap-frameworks` | Vue, Nuxt, Svelte, SvelteKit, lifecycle hooks, scoped selectors, and cleanup. |
| `gsap-scrolltrigger` | Scroll animations, parallax, pinning, scrub, scroll-linked timelines, and ScrollTrigger config. |
| `gsap-timeline` | Sequencing, choreography, timeline labels, nested timelines, and animation order. |
| `gsap-plugins` | Flip, Draggable, ScrollToPlugin, ScrollSmoother, SplitText, ScrambleText, SVG plugins, and plugin registration. |
| `gsap-performance` | Animation jank, FPS, layout thrashing, too many triggers, cleanup, and smooth 60fps work. |
| `gsap-utils` | `clamp`, `mapRange`, `normalize`, `interpolate`, `random`, `snap`, `toArray`, `wrap`, and helper functions. |

Example prompts:

```text
Use `gsap-react` and `gsap-core` to add a subtle page-load animation to this React component. Respect prefers-reduced-motion and clean up animations on unmount.
```

```text
Use `gsap-scrolltrigger` to create a pinned product story section. Then use `gsap-performance` to review it for jank and cleanup issues.
```

```text
Use `gsap-timeline` to sequence these hero animations. Keep ScrollTrigger only on the top-level timeline if scroll controls it.
```

Common pairing:

| Goal | Recommended sequence |
| --- | --- |
| React animation | `gsap-react` -> `gsap-core` -> `gsap-performance` |
| Scroll story | `gsap-scrolltrigger` -> `gsap-timeline` -> `gsap-performance` |
| Complex UI state transition | `gsap-plugins` with Flip -> `gsap-core` |
| Data-driven animation math | `gsap-utils` -> `gsap-core` |

### `minimalist-ui`

Use this for refined, document-like, editorial interfaces with warm monochrome color, strong typography, flat bento grids, and restraint. It is not a generic "simple UI" skill; it has a specific premium utilitarian aesthetic.

Best for:

| Use case | Why it fits |
| --- | --- |
| Knowledge tools | It emphasizes readable structure and whitespace. |
| Internal workspaces | It keeps the interface calm and utilitarian. |
| Editorial or document-heavy UIs | It prioritizes typography and flat structure. |

Example prompts:

```text
Use `minimalist-ui` to redesign this notes app as a warm, editorial workspace. Avoid gradients, heavy shadows, and generic SaaS cards.
```

```text
Use `minimalist-ui` with `shadcn` to build a quiet settings page with excellent typography and spacing.
```

### `industrial-brutalist-ui`

Use this when the interface should feel mechanical, tactical, raw, or like a declassified technical artifact. It is strongest for data-heavy dashboards, portfolios, and editorial pages that need an intentional edge.

Best for:

| Use case | Why it fits |
| --- | --- |
| Technical dashboards | It supports rigid grids and telemetry-like information density. |
| Portfolio or launch pages with attitude | It creates a memorable visual signature. |
| Editorial explainers | It can make information feel like a blueprint or dossier. |

Example prompts:

```text
Use `industrial-brutalist-ui` to design a data-heavy security dashboard. Make it feel like tactical telemetry, but keep accessibility and scanability intact.
```

```text
Use `industrial-brutalist-ui` for the visual direction, then use `gsap-performance` if you add any motion.
```

### `premium-frontend-ui`

Use this for immersive, high-craft web experiences: launches, portfolios, brand pages, editorial microsites, and pages where motion and atmosphere are part of the value.

Best for:

| Use case | Why it fits |
| --- | --- |
| Brand or launch sites | It emphasizes creative foundation, hero architecture, motion, and texture. |
| High-end portfolio work | It pushes toward immersive digital environments. |
| Scroll-driven narratives | It explicitly calls for scroll motion and contextual navigation. |

Example prompts:

```text
Use `premium-frontend-ui` to design a product launch page with a strong hero, contextual navigation, and high-performance motion. Use `gsap-scrolltrigger` only for scroll-driven moments.
```

Avoid using it for:

| Avoid when | Use instead |
| --- | --- |
| Dense operational dashboards | `dashboard` |
| Strict enterprise component work | `shadcn` plus `frontend-design` |
| Mobile-native screens | `mobile-app-ui-design` |

### `mobile-app-ui-design`

Use this for mobile app screens, flows, components, onboarding, navigation, and mobile-first prototypes. It is useful even when the implementation target is React Native, Flutter, SwiftUI, or a visual mockup.

Best for:

| Use case | Why it fits |
| --- | --- |
| App screen design | It starts from context and UX structure before visual polish. |
| Mobile onboarding | It covers flow, friction, emotion, and stage-specific patterns. |
| Mobile navigation | It knows mobile-first navigation and interaction constraints. |

Example prompts:

```text
Use `mobile-app-ui-design` to design a three-screen onboarding flow for a budgeting app. Include empty states, error states, and the primary navigation pattern.
```

```text
Use `mobile-app-ui-design` to critique this mobile screen for hierarchy, tap targets, and emotional peak-end moments.
```

Pair it with:

| Pair with | When |
| --- | --- |
| `building-native-ui` | The app is Expo or React Native with Expo Router. |
| `swiftui-skills` | The app is native SwiftUI. |
| `material-3` | The app is Android or Material Design based. |

### `swiftui-skills`

Use this for Apple-native SwiftUI guidance. It is especially useful when you want idiomatic SwiftUI and fewer platform hallucinations.

Best for:

| Use case | Why it fits |
| --- | --- |
| SwiftUI implementation | It is based on Apple-authored SwiftUI/platform guidance. |
| Refactoring non-idiomatic SwiftUI | It can push code toward platform conventions. |
| Native iOS/macOS UI questions | It helps align with Apple's actual APIs and patterns. |

Example prompts:

```text
Use `swiftui-skills` to implement this settings screen in idiomatic SwiftUI. Keep the UI native and avoid web-style layout assumptions.
```

```text
Use `mobile-app-ui-design` for the flow, then `swiftui-skills` for the SwiftUI implementation.
```

### `material-3`

Use this for Google's Material Design 3 system, especially Jetpack Compose Material3. It also has limited web guidance for `@material/web`.

Best for:

| Use case | Why it fits |
| --- | --- |
| Android Compose UI | It maps directly to MaterialTheme color, typography, and shape roles. |
| Material Design systems | It covers MD3 tokens, components, layouts, theming, and accessibility. |
| Cross-platform Material decisions | It explains where Material 3 applies and where support is limited. |

Example prompts:

```text
Use `material-3` to build this Jetpack Compose screen with correct MaterialTheme roles, component choices, and accessibility states.
```

```text
Use `material-3` to review this Android UI for token usage, component selection, and Material 3 consistency.
```

### `building-native-ui`

Use this for Expo Router apps and beautiful native-feeling Expo UI. It covers routing, styling, components, navigation, animations, patterns, and native tabs.

Best for:

| Use case | Why it fits |
| --- | --- |
| Expo Router apps | It knows Expo app structure and routing conventions. |
| React Native UI with Expo | It covers styling, behavior, navigation, and library preferences. |
| Native tabs and app shell work | It includes Expo-specific navigation guidance. |

Example prompts:

```text
Use `building-native-ui` to build this Expo Router app shell with tabs, modal routes, responsive styling, and native-feeling interactions.
```

```text
Use `mobile-app-ui-design` to design the flow, then `building-native-ui` to implement it in Expo Router.
```

## Recommended workflows

### Build a web dashboard

Use this when you want a real dashboard, not a landing page.

1. Ask for the visual and UX plan.

```text
Use `dashboard` and `frontend-design` to plan a data-heavy dashboard. Give me the hierarchy, layout, palette, typography, and key states before coding.
```

2. Implement with the component system.

```text
Use `shadcn` to implement the dashboard components. Include filters, cards, a table, loading states, empty states, and error states.
```

3. Verify the result.

```text
Use `ui-ux-pro-max` as a verifier. Check accessibility, responsive behavior, chart readability, and interaction states. Return concrete fixes.
```

### Build a polished marketing page

Use this when the experience needs to feel distinctive and high craft.

1. Establish the creative direction.

```text
Use `premium-frontend-ui` and `frontend-design` to create a strong visual direction for this launch page. Keep the hero first-viewport signal clear and avoid generic AI aesthetics.
```

2. Add motion only where it has a job.

```text
Use `gsap-core` for deliberate page-load and hover animation. If there is a scroll story, use `gsap-scrolltrigger`. Respect prefers-reduced-motion.
```

3. Run performance review.

```text
Use `gsap-performance` to review the animations for layout thrashing, excessive triggers, cleanup, and mobile smoothness.
```

### Build a mobile app feature

Use this when the target is a real mobile app or mobile prototype.

1. Design the flow.

```text
Use `mobile-app-ui-design` to design the flow, navigation, screen hierarchy, empty states, and error states.
```

2. Choose the platform implementation skill.

| Platform | Use |
| --- | --- |
| Expo / React Native | `building-native-ui` |
| SwiftUI | `swiftui-skills` |
| Android Compose / Material | `material-3` |

3. Verify the UI.

```text
Use `ui-ux-pro-max` to review the final screens for accessibility, tap targets, contrast, responsiveness, and form behavior.
```

## Host recommendations applied to these skills

The transcript recommendations are most useful as operating rules:

| Recommendation | How to apply it |
| --- | --- |
| Keep skills focused. | Use `gsap-scrolltrigger` for scroll animation, not the whole GSAP family at once. Use `dashboard` for dashboards, not every web UI. |
| Prefer verifiers. | After creation, ask `ui-ux-pro-max`, `frontend-design`, or `gsap-performance` to review the output with pass/fail issues. |
| Use scripts and deterministic tools where possible. | When the skill suggests running a real app, screenshot, build, or test, let the agent verify instead of relying only on prose. |
| Use templates and assets for repeatability. | For decks, dashboards, brand pages, or mobile screens, provide screenshots, brand files, or prior examples as file paths. |
| Add gotchas from real failures. | If a skill repeatedly produces a bad pattern in your work, ask the agent to write a proposed gotcha before editing the skill itself. |
| Tune triggers. | Say the skill name or use the exact domain language: "shadcn", "Expo Router", "SwiftUI", "Material 3", "ScrollTrigger", "dashboard", "mobile app screen". |
| Orchestrate by chaining focused skills. | Ask for explicit phases: design plan, implementation, animation, verification. |

## Common mistakes

| Mistake | Better approach |
| --- | --- |
| Asking every design skill to run on every UI. | Pick one primary design direction, then add implementation and verification skills. |
| Using `premium-frontend-ui` for dense internal tools. | Use `dashboard`, `minimalist-ui`, or `shadcn` depending on the product. |
| Using GSAP without cleanup. | Use `gsap-react` or `gsap-frameworks` for framework lifecycle and `gsap-performance` for review. |
| Asking for animation before the layout works. | Build the static hierarchy first, then animate the moments that matter. |
| Treating `ui-ux-pro-max` as only a creation skill. | Use it as a verifier after implementation. |
| Giving the agent images without paths. | Provide local file paths to assets when you want them inserted or used as references. |
| Accepting a first pass without a review loop. | Ask for screenshots, responsive checks, accessibility checks, and a final issue list. |

## Practical prompt recipes

### Strong web UI from scratch

```text
Use `frontend-design` to create a design plan for [product]. Then implement it in [framework]. If shadcn/ui is present, use `shadcn` for components. End with a `ui-ux-pro-max` review of accessibility, responsive behavior, and visual hierarchy.
```

### Shadcn dashboard

```text
Use `dashboard` for the visual system and `shadcn` for implementation. Build a [dashboard type] with [key metrics], filters, table, loading state, empty state, and error state. Then run `ui-ux-pro-max` as a verifier.
```

### Premium animated page

```text
Use `premium-frontend-ui` for the page direction. Use `gsap-core` for focused animation and `gsap-scrolltrigger` only for scroll-driven sections. Use `gsap-performance` to review the final animation.
```

### React animation

```text
Use `gsap-react` and `gsap-core` to add [animation goal] to this component. Keep animation client-only, scoped to refs, and cleaned up on unmount. Respect prefers-reduced-motion.
```

### Expo app screen

```text
Use `mobile-app-ui-design` to design the screen and `building-native-ui` to implement it in Expo Router. Include navigation behavior, loading state, error state, and platform-appropriate touch targets.
```

### SwiftUI screen

```text
Use `mobile-app-ui-design` for the UX flow and `swiftui-skills` for the implementation. Keep the result idiomatic SwiftUI and native to Apple platforms.
```

### Material 3 Android screen

```text
Use `material-3` to build this Jetpack Compose screen with correct MaterialTheme tokens, components, layout, and accessibility states.
```

## Installed inventory

| Skill | Installed path |
| --- | --- |
| `frontend-design` | `C:\Users\simon\.agents\skills\frontend-design` |
| `shadcn` | `C:\Users\simon\.agents\skills\shadcn` |
| `dashboard` | `C:\Users\simon\.agents\skills\dashboard` |
| `ui-ux-pro-max` | `C:\Users\simon\.agents\skills\ui-ux-pro-max` |
| `gsap-core` | `C:\Users\simon\.agents\skills\gsap-core` |
| `gsap-frameworks` | `C:\Users\simon\.agents\skills\gsap-frameworks` |
| `gsap-performance` | `C:\Users\simon\.agents\skills\gsap-performance` |
| `gsap-plugins` | `C:\Users\simon\.agents\skills\gsap-plugins` |
| `gsap-react` | `C:\Users\simon\.agents\skills\gsap-react` |
| `gsap-scrolltrigger` | `C:\Users\simon\.agents\skills\gsap-scrolltrigger` |
| `gsap-timeline` | `C:\Users\simon\.agents\skills\gsap-timeline` |
| `gsap-utils` | `C:\Users\simon\.agents\skills\gsap-utils` |
| `minimalist-ui` | `C:\Users\simon\.agents\skills\minimalist-ui` |
| `industrial-brutalist-ui` | `C:\Users\simon\.agents\skills\industrial-brutalist-ui` |
| `premium-frontend-ui` | `C:\Users\simon\.agents\skills\premium-frontend-ui` |
| `mobile-app-ui-design` | `C:\Users\simon\.agents\skills\mobile-app-ui-design` |
| `swiftui-skills` | `C:\Users\simon\.agents\skills\swiftui-skills` |
| `material-3` | `C:\Users\simon\.agents\skills\material-3` |
| `building-native-ui` | `C:\Users\simon\.agents\skills\building-native-ui` |

## Failed or unavailable item

| Item | Status |
| --- | --- |
| `frontend-ui-ux` | Not installed. The skills.sh page advertised this skill, but the current `code-yeongyu/oh-my-opencode` repository did not expose a matching skill name when installed. |
| MCPs from these links | None found. These links resolved to skill packages, not MCP server packages. |

