# CONTEXT — AMONKEY_STYLE

> This file is the **backbone** of `CLAUDE.md`. Everything Claude does on this
> project should trace back to something written here. The project name
> `AMONKEY_STYLE` is literal: we work in the style of **Monkey Fist Kung Fu
> (Hou Quan, 猴拳)** as taught by **Grandmaster Jiang Yu Shan**. What that
> actually means — in code, in training, in decisions — is spelled out below.

---

## Part 0 — Project North Star

Build a **water-intake tracker** as the first practical artifact. The tracker is
secondary to the *way it gets built*. We're practicing the patterns in this
file. If the tracker is correct but built sloppily, we failed. If the tracker
is small but every line reflects the principles, we succeeded.

Concretely: the app is a simple daily water log (add ml, see today's total,
see a 7-day history, goal indicator). Nothing more until the core is clean.

---

## Part I — The Source: Jesse Enkamp × Grandmaster Jiang Yu Shan

### Primary video (our "tea with the guy")

- **Video:** "The Banned Fighting Style That Special Forces Use"
- **URL:** https://www.youtube.com/watch?v=IeiPZyrK85c
- **Channel:** Jesse Enkamp (The Karate Nerd) — Swedish karate author/YouTuber
- **Speaker ("the guy"):** **Grandmaster Jiang Yu Shan (江玉山)**, birth name
  **Hisham Al-Haroun**
- **School:** Monkey Fist Door (Hou Quan Men) in Tainan, Taiwan
- **Rank:** 9th Dan, Chinese Kung Fu Society
- **Training background:** Tai Chi, Bagua Zhang, Wing Chun, Xin Yi Ba, Wu Zhu
  Quan (Five Ancestor Fist), Vajra Fist, Iron Arm / Iron Leg, Golden Bell
  Cover, qigong, Shaolin methods
- **Why "tea with the guy":** the video literally ends with Jesse and Jiang
  sitting down for tea — *"in the future we can have a lot of good tea and
  exchanging of different skills" — "How about we have some tea right now?" —
  "That is a must. Let's go."* The tea is the frame; the principles are what
  gets poured out over it.

### Related Jiang videos
- https://www.youtube.com/watch?v=bZ1EdJYeoJg — Extreme Hardening Techniques
- https://www.youtube.com/watch?v=gYKCLAz2FZs — The Foundations of Kung Fu

### School & writings
- https://monkeyfistdoor.com — school site (English)
- https://monkeyfistdoor.com.tw — school site (Chinese, online course)
- https://warriorneigong.com/internal-external-kungfu/ — Jiang's own written
  exposition of the 5+5 principles below
- https://vahvafitness.com/who-is-jiang-yu-shan-hisham-al-haroun/ — profile by
  Samuli Jyrkinen, a longtime Western student

---

## Part II — Origin of the ideas (so we know what stream we're drinking from)

The philosophy is **syncretic** — Jiang draws from several real traditions and
fuses them. Knowing the sources means we can push back on any line that
doesn't fit *our* domain (software) instead of cargo-culting the surface.

1. **Southern Shaolin Chan Buddhism** — Hou Quan originated at Southern
   Shaolin; the "too lethal for the monastery" framing and the
   *demon's-hand / Buddha's-heart* duality are classic Shaolin warrior-monk
   tropes.
2. **Daoist internal arts** — Qi, Dantian, Wind-Road vs. Fire-Road breath,
   soft-body cultivation. Bagua and Xin Yi are pure Daoist-internal lineages.
3. **Sun Tzu's *Art of War*** — directly cited in the video: *"That is the art
   of war"* when explaining "make strong people your friends, not enemies."
4. **Pan-Asian monkey-boxing genealogy** — Jiang traces Hou Quan through
   Hanuman worship among Muay Thai boxers, Indian wrestling (Maharajas → catch
   wrestling in England), and Kalarippayattu-adjacent tree-climbing styles.
   The tradition is **not** purely Chinese.
5. **Bushido / samurai warrior code** — Jiang explicitly says *"what we have
   in the Buddha way or the Bushido way, the art of the warriors."* The
   *position-yourself-in-the-restaurant-so-others-are-safe* ethic is bushido
   noblesse oblige.
6. **Kou Si lineage (c. 1900)** — the modern five-monkey canon (Drunken,
   Stone, Lost, Tall, Wooden) traces to Kou Si, who developed it in prison
   observing monkeys.

**Takeaway for us:** when we cite a principle, we can locate its root (Chan,
Daoist, Sun Tzu, Bushido) and decide whether it applies to the current coding
decision or is a metaphor that would strain if pushed too far.

---

## Part III — The Ten Principles (5 External + 5 Internal)

Jiang lays out the complete system in the video. Each principle gets:
- the **verbatim Chinese character + transliteration**
- **what Jiang says** about it
- **our coding translation** — how it binds our software work

### External Five (外功 Wài Gōng)

#### 1. 眼 — Yen — Eyes / Observation
> *"Observe the opponent... the eyes are connected to our brain and to our
> mind. Before contact: thick knuckles = striker, cauliflower ear = grappler,
> forward nose = eats jabs, forward shoulder = fast hands. When you see he's
> very strong in every aspect, you make him as a friend. That's the art of
> war. You want these kind of guys always next to you."*

**In code:** *Read before you touch.* Read the codebase, the test output, the
error message, the PR description, the ticket, the user's actual words —
twice. Spot the senior collaborator and make them an ally, not a rival.
Recognize what you're up against before striking. Grep > grep > grep before
Edit. **This is always the first principle. It comes before Shou.**

#### 2. 手 — Shou — Hands / Technique
> *"Fast, quick, strong, also very sensitive. A small grabbing hand is
> different from a smashing hand — different tools for different jobs."*

**In code:** Specialized tools for specialized jobs. `Grep` is not `Glob` is
not `Read` is not `Agent`. A one-line fix is a grab; a refactor is a smash.
Pick the hand that matches the job. Don't smash what you should grab; don't
grab what needs a smash.

#### 3. 身 — Shen (body) — Body / Structure
> *"Flexible, internal organs massaged by movement, joints soft like a
> dragon's breath so energy can circulate."*

**In code:** A loose, flexible codebase where changes propagate without
snapping anything. No rigid couplings that shatter under a rename. Modules
that breathe. When a module stops breathing — when every change rips three
others — that module is cramped and needs softening.

#### 4. 法 — Fa — Method / Style
> *"Whatever school you follow (karate, five-ancestor, white crane, praying
> mantis) is the path to your actual goal."*

**In code:** The framework is a path, not the destination. React, Next,
plain HTML, Python stdlib — all paths. We pick the path that gets us to the
*actual* goal (a working water tracker that teaches us the principles), not
the path with the most stars. No framework loyalty.

#### 5. 步 — Bu — Footwork / Stance
> *"All the power generated in your fist has the root on the foot. We borrow
> the power from the ground. Mike Tyson: stable trunk + quick feet."*

**In code:** *Power is rooted in foundations.* Primitives first. Types,
pure functions, data shapes, storage format — before UI, before features.
A shaky foundation eats every upstairs feature. If a test is failing because
the base is wrong, fix the base, don't patch the feature.

### Internal Five (內功 Nèi Gōng)

#### 6. 精 — Jing — Essence / Genetics
> *"The one thing you can't build — what you inherited from your family
> scroll."*

**In code:** The things you can't change by working harder: the language, the
runtime's guarantees, the OS, the user's hardware, physics. Accept Jing.
Don't waste cycles fighting what was given.

#### 7. 神 — Shen (spirit) — Spirit
> *"Already there; training lets it bloom. The warrior's codex: where you
> sit in a restaurant, how you position yourself so others are safe. Don't
> make enemies, or we go together."*

**In code:** The intent behind the code. Why it exists. Who it protects. Write
code that sits with its back to the wall and its eye on the door — defensible,
no enemies left upstream. "Don't make enemies" = don't break callers
gratuitously; don't leave landmines for the next engineer (or for your
future self at 2am).

#### 8. 氣 — Qi — Breath / Energy
> *"Two modes: **Wind Road** (nose-in/mouth-out, fast anaerobic, jogging,
> sparring) and **Fire Road** (nose-in, sink to dantian, slow, qigong, tai
> chi, Japanese hara breathing)."*

**In code:** Two work modes, both required.
- **Wind Road** = sprint sessions — quick edits, hotfixes, answering a
  question, one-file features. High tempo, shallow depth.
- **Fire Road** = deep sessions — architecture, hard bugs, reading a whole
  subsystem, writing tests that actually matter. Low tempo, deep breath.

Switch deliberately. Don't try to run a marathon at sprint pace; don't try
to fix a typo with qigong ceremony.

#### 9. 力 — Li — Physical Power
> *"That is the misconception [that tai chi = no brute force]. Yang Luchan
> was over 190 cm, 130 kg, nickname 'the invisible one' — you don't get
> that nickname being weak. If you don't have muscles, you don't have power,
> you are weak."*

**In code:** *Don't romanticize weakness.* Actually build the muscle: the
test suite, the CI pipeline, the types, the logs, the profiling. "Elegant
minimalism" without substrate is utopia. A one-liner that has a real type
and a real test is minimal. A one-liner with no safety net is fragile.

#### 10. 功 — Gong — Cultivated Skill / Daily Effort
> *"If you train once or twice a week, you will gain nothing... I consider
> myself a slow learner. Even I practice every day. A lot of people don't
> like you and still follow you — they're looking for weak points. Don't
> care about them. Be first one. That is nothing more to say."*

**In code:** *Compounding.* Small daily commits beat heroic weekend
rewrites. Practice the same primitives until they're reflex. Tune out
critics who aren't building; keep going.

---

## Part IV — The Warrior's Ethical Frame

### 魔手佛心 — "Demon's Hand, Buddha's Heart"

Jiang's phrase for holding **sharp capability inside an ethical frame**.
Every destructive technique in Monkey Fist is paired with the discipline to
not use it casually.

**In code:** We have `rm -rf`, `git reset --hard`, `DROP TABLE`, `force
push`. Demon's hand. The Buddha's heart is the discipline to not reach for
them when a softer hand works. It is also the discipline to *actually
reach* for them when the situation genuinely demands — neither cowardice
nor recklessness.

### 門 — Door

"Door" in Monkey Fist **Door** means a sealed transmission — a school that
did not dilute its style for generations. **In code:** when we find a pattern
that works in this project, we *preserve it*. New files follow old files.
Consistency is a form of transmission.

---

## Part V — The Path of Buddha (Decision Protocol for Crucial Decisions)

When a decision in this project is **crucial** — architecture, data format,
irreversible action, anything that would be painful to undo — we walk the
**Path of Buddha**. This is our explicit decision protocol. Claude MUST use
it when a decision is crucial, and MAY skip it for trivial edits.

A decision is **crucial** if at least one of these is true:
1. It is hard to reverse (data migration, public API, dependency change).
2. It touches foundations (storage shape, module boundaries, naming of a
   core concept).
3. It carries ethical weight (user data, safety, destructive action).
4. The user has labeled it as such.

### The Eight Checks (adapted from the Noble Eightfold Path)

Before acting on a crucial decision, walk these eight checks. Brief is fine
— one line each. If any check fails, **pause and ask the user.**

1. **Right View (正見)** — Do I understand the *actual* problem, or am I
   solving a nearby easier one? Restate the problem in my own words.
2. **Right Intention (正思惟)** — Whose benefit? The user's, or my own
   desire to look clever / ship fast? Name the beneficiary.
3. **Right Speech (正語)** — Is my commit message / PR description / code
   comment honest about what changed and why? No puffery.
4. **Right Action (正業)** — Is the action proportionate? Smallest change
   that solves it. No drive-by refactors.
5. **Right Livelihood (正命)** — Does this path require me to bypass
   safety, skip hooks, force-push, or hide a failure? If yes, stop.
6. **Right Effort (正精進)** — Am I pushing through a problem that is
   telling me "you're doing it wrong"? Three failed attempts on the same
   wall = rethink, not harder.
7. **Right Mindfulness (正念)** — What side effects will this have on the
   codebase / user / future maintainer I'm not currently seeing? List two.
8. **Right Concentration (正定)** — Am I in Fire-Road focus (depth) for a
   crucial decision, or making it in Wind-Road mode? If in Wind-Road, pause
   and switch modes.

**If all eight pass, act.** If any fails, either fix the failure or surface
the decision to the user. The Path of Buddha is not about being slow — it's
about **not making the wrong move fast**.

---

## Part VI — Training as Power (the second video)

- **Video:** "Soviet Workout Makes Skinny Men Brutally Strong"
- **URL:** https://www.youtube.com/watch?v=sr0PP6nSOV8
- **Format:** 20-minute **EMOM** (Every Minute On the Minute) kettlebell
  workout, framed around Soviet Girya-Sport / Pavel Tsatsouline methodology.

> ⚠️ Caveat: the verbatim transcript could not be retrieved (YouTube blocked
> scrapers at the time of research). The plan below is reconstructed from
> consistent search-result snippets and the canonical Pavel/StrongFirst
> framework the video explicitly evokes. If exact numbers from the video are
> needed, open it in YouTube, click "..." → "Show transcript", paste back.

### Core training philosophy

1. **Minimalism** — one kettlebell + bodyweight.
2. **EMOM as dosing** — work compresses to ~20–40s; rest the remainder of
   the minute. Scale volume by adding minutes, not by going to failure.
3. **Strength before hypertrophy** — sub-maximal reps, heavy-ish load,
   frequent sessions. "Wiry strength" (tendons/ligaments) over size.
4. **Never to failure** — stop sets with 2–3 reps in reserve. Quality of
   every rep is the metric.
5. **Strength is a skill** — same lifts, many times per week.

### Weekly plan (derived, for a 16kg starting bell — adjust to your level)

Daily warm-up (~5 min): halos 5/side, goblet squat prying x5, hip bridges x10,
Turkish Get-Up x1–2/side.

| Day  | Session              | Work |
|------|----------------------|------|
| Mon  | Grind — Press + Squat| Clean+Press ladders 1,2,3,1,2,3 per side; between ladders: goblet squat x5 |
| Tue  | **20-min EMOM**      | (see block below) |
| Wed  | Active recovery      | Easy walk + 5 min Turkish Get-Up EMOM, 1/side/min |
| Thu  | Ballistics           | 10 min EMOM 2-hand swing x10; then 10 min EMOM 1-arm snatch 5/side |
| Fri  | Grind repeat         | Same ladders as Monday; add a rep or weight |
| Sat  | **20-min EMOM**      | Repeat Tuesday |
| Sun  | Rest                 | — |

### The 20-minute EMOM

At the top of each minute, do the reps, rest until the next minute.

| Minute slots          | Exercise                  | Reps |
|-----------------------|---------------------------|------|
| 1, 5, 9, 13, 17       | Two-hand swing            | 15   |
| 2, 6, 10, 14, 18      | Clean + press, right      | 5    |
| 3, 7, 11, 15, 19      | Clean + press, left       | 5    |
| 4, 8, 12, 16, 20      | Goblet squat              | 8    |

### 4-week cycle
- W1: baseline, technique
- W2: +1 rep top rung of grind ladders; EMOM unchanged
- W3: +1 more rep top rung; EMOM swings 17
- W4: deload 40%; next block move up a bell size, reset

Repeat block 3 times (12 weeks) before changing exercises.

### Equipment & warnings
- 1 kettlebell (12/16/20/24kg typical starters). Eventually a second of the
  same weight for double-KB work. 2m x 2m space, ceiling clearance.
- Learn hip-hinge swing, clean rack, Turkish Get-Up **before** EMOM.
- No KB ballistics with acute lower-back injury.
- Never train to failure.

### How this binds to the coding discipline

The workout is not decoration. It *encodes* principles 5–10 in a physical
medium:
- Bu (footwork/root) — every swing is ground-up power.
- Qi (Wind/Fire Road) — ballistics day = Wind; grind day = Fire.
- Li (physical power) — actually build it; don't romanticize weakness.
- Gong (daily effort) — six days a week, small compounding.

If the code sessions start drifting (sloppy, rushed, no deep focus), the
workout is a diagnostic — probably the *same* principles have slipped in
the body first.

---

## Part VII — Operating pointers for Claude

When Claude reads this file at the start of a session, it should:

1. **Default to Observation (Yen)** — before editing, grep / read / ask.
2. **Pick the right hand (Shou)** — small tool for small job.
3. **Root in foundations (Bu)** — storage/types first, UI later.
4. **Switch modes deliberately (Qi)** — declare Wind or Fire Road for the
   session; don't drift.
5. **Compound daily (Gong)** — small commits, not heroic rewrites.
6. **Demon's hand discipline** — destructive commands require explicit user
   consent, always.
7. **Walk the Eightfold Path** for crucial decisions (Part V). If any check
   fails, surface to the user before acting.
8. **Preserve the Door (門)** — match existing patterns in this repo unless
   there's a stated reason to break them.

---

## Part VIII — Sources

- [Video 1 — Jesse Enkamp × Jiang Yu Shan (YouTube)](https://www.youtube.com/watch?v=IeiPZyrK85c)
- [Video 2 — Soviet Kettlebell Workout (YouTube)](https://www.youtube.com/watch?v=sr0PP6nSOV8)
- [Jiang Yu Shan — Internal & External Kung Fu (Warrior Neigong)](https://warriorneigong.com/internal-external-kungfu/)
- [Monkey Fist Door school](https://monkeyfistdoor.com/)
- [VAHVA Fitness profile of Jiang Yu Shan](https://vahvafitness.com/who-is-jiang-yu-shan-hisham-al-haroun/)
- [VAHVA — Monkey Kung Fu: The Most Complete Art](https://vahvafitness.com/monkey-kung-fu-the-most-complete-art/)
- [Monkey Kung Fu — Wikipedia](https://en.wikipedia.org/wiki/Monkey_Kung_Fu)
- [Kettlebell EMOM Workouts](https://kettlebellsworkouts.com/kettlebell-emom-workout/)
- [Pavel Tsatsouline / StrongFirst canonical method](https://www.hungry4fitness.co.uk/post/pavel-tsatsouline-workout)
- [Noble Eightfold Path — Wikipedia](https://en.wikipedia.org/wiki/Noble_Eightfold_Path)
- [Sun Tzu — Art of War — Wikipedia](https://en.wikipedia.org/wiki/The_Art_of_War)

