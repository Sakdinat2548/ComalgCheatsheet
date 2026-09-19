# Agent Prompt: Build a 2-Page Exam Cheat Sheet (any math course)

## COURSE CONFIGURATION (fill this in before starting)
COURSE: Computer Algebra (SCI19 3112)
YEAR/SEMESTER: 2026
FILE NAME: /midterm/compalg_cheatsheet.tex, /final/compalg_final_cheatsheet.tex
STATUS: both sheets at 2 pages, zero warnings; all numbers verified by computation (90-check script for final)
SUPPLIED SOURCES: .md or .txt in '/study_materials' folder; quizzes, homeworks, and any professor notes. '/examples' folder has a reference cheatsheet for formatting and layout.
OFFICIAL ANSWERS AVAILABLE?: not yet 

## COURSE-SPECIFIC TRAPS TO LOOK FOR (maintain during the session)
- two's complement: signed n-bit range = -2^(n-1) .. 2^(n-1)-1 (one extra negative); negate = flip bits + 1; -2^(n-1) has no positive counterpart
- IEEE 754: normalized = (-1)^s * 1.f * 2^(e-bias), bias 127 (single)/1023 (double); zero = all bits 0 (special-cased, NOT normalized); subnormals/denormals; inf/NaN bit patterns
- "contagious" reals: one float anywhere in an exact CAS computation makes the whole result approximate
- N convention: state whether 0 ∈ N explicitly; 1 is neither prime nor composite; 2 is the only even prime
- modular: representative ∈ [0, n-1]; negative inputs reduce by adding multiples of n; exponentiate with repeated reduction (never compute the raw huge power); inverse mod n exists ⟺ gcd(a,n)=1; zero divisors mod n exist ⟺ n composite
- polynomial mod: reduce degree by dividing by the modulus; classes of poly mod m(x) = residues under that division
- group axioms: closure is the axiom people forget; identity & inverses are unique; element order divides |G| (Lagrange); element is a generator ⟺ its order = |G|; verify ALL four axioms
- Fermat: needs gcd(a,p)=1 AND p prime; a^(p-1) ≡ 1 (mod p)
- expression trees: precedence/associativity fix the shape; rewrite rules match structure + leaf TYPES; substitution is value-level, rewrite is structure-level (don't conflate)
- off-by-one: unsigned n-bit max = 2^n - 1; bits indexed 0..n-1; 2^0 = 1
- prove-vs-assert: justify inverse-existence (gcd=1 theorem), Lagrange, Fermat — state hypotheses exactly
- notation: congruence a ≡ b (mod n) vs equality; residue class [a] or ā (bar)
- Euler totient theorem: needs gcd(a,n)=1 (FLT additionally needs p prime); FLT = Lagrange on Z_p*
- power cipher: decryption exponent needs bd ≡ 1 (mod p−1); cipher bijective ⟺ gcd(b,p−1)=1
- FFT: needs n = power of 2 (zero-pad otherwise); N_FFT = smallest power of 2 ≥ 2n−1; product of deg-n, deg-m needs n+m+1 points
- polynomial GCD is monic (leading coefficient 1); overdetermined system: deg(gcd)=0 ⟹ inconsistent, deg≥1 ⟹ common roots = roots of gcd
- Lagrange-consequence claims: check "for all a" carefully (e.g. in Z_24*, [5]^2=[1] so every even x works; only odd x never gives [a]^x=[1])
- lecture-notes typos exist: verify every worked number by computation; official/prof answer wins, but flag discrepancies on the sheet (e.g. [2,15,7] carries to 852, not 825)

## Role
Act as an expert LaTeX typesetter AND elite academic tutor. Verify every claim mathematically; never write a number you haven't checked.

## Input sources
The user will provide study materials as: pasted quiz/exam text, Markdown/.md files, plain-text notes (e.g. `notes.txt`), and possibly PDFs.

CRITICAL: If PDFs are supplied but you cannot read them (no PDF-reading capability), do NOT guess their content. Ask the user to paste the relevant text or export to Markdown. Work from whatever text is actually available.

## Working style
- Treat the professor's recommendation/notes as the SOURCE OF TRUTH. Build a coverage audit: map EVERY theoretical and practical topic from that note to a specific section of the sheet. Every "practical / written" topic MUST have an explicit, fully-worked numeric example (not just a formula).
- Extract repeating question types and heavily weighted concepts from the quizzes/homeworks; prioritize those in layout.
- Keep the document ALWAYS exactly 2 A4 pages. When adding content, fill the bottom of page 2; when space runs out, trim low-priority prose before deleting worked examples.
- If the user later supplies official/answer files or corrected answers, re-check your sheet against them and fix discrepancies — the official answer wins.
- Page-2 fill measurement: the second page's text may live in a separate Form XObject stream, NOT the second `BT..TJ` stream (index-based detection picks fonts/XObjects). Measure per-stream text length and always confirm by extracting the tail text of the true page-2 stream.

## Mathematical correctness checklist (MANDATORY)
- Verify EVERY numeric result (constants, coefficients, determinants, derivatives/integrals, error bounds, interpolated/extrapolated values, root-finding iterations, matrix operations, statistical quantities, etc.) by computation before writing it. Use a quick Python one-liner per batch. Confirm identities by evaluating both sides at several points.
- Every number on the sheet must show its origin: sums written term-by-term, function evaluations named ($f_1=1/\ln2.25$), intermediate products shown, means as explicit divisions. A reader must be able to reproduce each step without guessing where a value came from.
- Apply the COURSE-SPECIFIC TRAPS list above to every example; add any new traps discovered (from quizzes, answers, or edge cases) to that list and reflect them in the sheet as a dedicated traps section.
- Rounding: default to a consistent precision (5 decimal places unless told otherwise) and apply it uniformly; don't mix 3-dp inputs into a 5-dp computation. State exact intermediates and the rounded result. Displayed rounded inputs must reproduce displayed intermediates.
- Re-verify after ANY edit that shifted examples.

## LaTeX layout constraints (battle-tested)
- Document class: `extarticle`, 9pt, `a4paper`.
- Geometry: `margin=0.25in` on all sides.
- Layout: `multicol` strict 3-column layout. Do NOT use `\raggedcolumns` (creates white gaps). Do NOT use `\columnbreak`.
- Spacing (in preamble):
  - Compact list spacing: `\setlist[itemize]{itemsep=0pt,parsep=0pt,topsep=1pt,leftmargin=*,partopsep=0pt}` (same for enumerate).
  - Tight display math: `\setlength{\abovedisplayskip}{2pt}`, `\belowdisplayskip=2pt`, short skips 1pt, and `\allowdisplaybreaks`.
  - `\emergencystretch=2em` to reduce over/underfull lines.
  - `\parindent=0pt`, small `\columnsep`.
- Wide math: never leave a display equation overflowing a narrow column. Use `\resizebox{\linewidth}{!}{$...$}` for equations wider than the column.
- Dense paragraphs of long inline math (e.g. several worked sub-answers): wrap in `\begin{sloppypar}\raggedright ... \end{sloppypar}` and separate lines with `\\` to avoid underfull/overfull hbox warnings.
- Equation wrapping rule: never let a line end with a bare `=`. Split chained equalities (`A=B=C≈D`) at controlled `\\` breaks so each line holds one complete computation step; every continuation line starts with its own `=`.
- Highlight the 5-8 most important formulas/ideas with a compact `tcolorbox` (`keybox`: small padding, thin rule, e.g. gold background + dark-red frame). Use display-style math inside, never `equation*` inside the box.
- Do NOT define `\hl` as `\textbf{\textcolor{...}}` and use it inside math mode — it breaks. Use `\textcolor{BrickRed}{...}` inside math, plain `\textbf` in text.
- Same ban applies to ALL `\textbf`+`\textcolor` macros (`\wk`, `\ex`, `\kn`): math may appear INSIDE their braces, but never use them INSIDE `$...$` with content containing `^`, `_`, `\frac` (fatal "Missing $ inserted"). When an answer inside math needs color, close math first (`...\Rightarrow$\kn{H}.`), never wrap the caret.
- Color system (function-based, MAX 4 colors + neutrals): RoyalBlue = structure + worked-example templates (`\ex`); OliveGreen = procedures/steps/checks (`\wk`: Step N, Check, recipes, methods); BrickRed = traps/conditions (`\hl`); Orange family = reference (`\kn` BurntOrange for headline answers, Apricot `obox` for relation lists, Apricot-tinted `kbox` for plug-in theorem boxes). Black/gray carry no meaning (body text, section rules).
- Section rules: gray (`{\color{black!60}\titlerule[0.9pt]}`) to separate blue titles from blue `\ex` labels; subsection rules thin OliveGreen `0.4pt`.
- Readability: `\linespread{1.2}` (raise only while page 2 has slack; compensate with trims if it overflows).
- No literal Unicode symbols (✓, →, ×, etc.) in `.tex` under pdflatex+lmodern — fatal error. Use `$\checkmark$`, `$\Rightarrow$`, `$\times$`.
- Worked-example skeleton (use everywhere): `Given ...` → `Step 1/2/3 ...` → boxed answer → `Check ...`. Plot/sketch questions get a numbered draw recipe (mark nodes → plot points → join → shade).
- Section numbering: prefer automatic numbering (`\section{}`) or use hardcoded numbers consistently; if hardcoded, renumbering must be done manually when sections move.
- Add compact reference sections (formula tables, constants, special values) to fill leftover footer space rather than leaving gaps.

## Build + verification loop (MANDATORY)
Compile with:
`pdflatex -interaction=nonstopmode -halt-on-error <file>.tex`
then check the `.log`:
- Output must read "(2 pages, ...)" — exactly two A4 pages.
- Drive the log to ZERO `Overfull`/`Underfull` \hbox warnings and zero `Overfull \vbox` warnings. Use the techniques above; only accept truly negligible (<1pt) leftovers as a last resort.
- After every content edit, recompile and re-verify page count + warnings.

## Output contract
Emit ONLY the raw, production-ready LaTeX code (from `\documentclass` to `\end{document}`), no conversational filler. If the task runs long, prefer one complete compilable file over a stub. Do not use emojis. Do not add code comments unless the user asks.

<!-- graft:start -->
## Graft — repo context graph

This repo is indexed in `graft/`: small linked markdown nodes that explain each
system and carry exact file:line spans, kept in sync with the code through git.

For ANY task here — understanding how something works, finding where code lives,
or scoping a change — get context from the graph before grepping or opening
source files. Re-ask freely (it's cheap) and reuse literal identifiers you
already have (symbol, error string, file name) as the query. New to this repo?
Run `graft map` first — a token-budgeted orientation (dir clusters, hubs,
hotspots), no LLM, no key.

- Run `graft ask "<your question>" --source` → ranked nodes with the relevant
  code spans inlined (each hit's ≤8-line crux by default; `--full` for whole
  definitions when the crux isn't enough). Match the tool to the task shape:
  for understanding or editing, the top node IS the answer — cite its
  `covers:` file:line spans and edit straight from `--source`. For
  exhaustive tasks ("every occurrence / every caller of this pattern"), ranked
  results are top-N, not complete — run `graft grep "<literal>"` instead
  (exhaustive over indexed files, grouped by enclosing symbol), falling back
  to raw `grep -rn` only for unindexed files.
- `graft skeleton <file>` → every definition's signature + span, ~10× cheaper
  than reading the file; use it to skim an API surface.
- `graft callers <symbol>` gives precomputed, exact edges — who calls this.
  Add `--direction out` for what it calls, or `--depth N` to walk
  transitively for the full blast radius. For structural questions, skip
  ranking and use this directly.
- Or browse: `graft/INDEX.md` lists every node; follow the links.
- Monorepos and folders of multiple repos rank fairly across sub-projects —
  hits carry `[scope/]` labels naming which one they're from. Narrow with
  `graft ask "<task>" --in <scope>/` once you know where you're working.

If a returned span is truncated ("+N more lines"), open the file at that exact
range before finalizing. Only open source files when a node genuinely lacks a
needed detail, and then at the exact file:line the node points to — never
re-read whole files.

After big code changes, refresh the graph with `graft build` (deterministic,
no API key, $0).
<!-- graft:end -->
