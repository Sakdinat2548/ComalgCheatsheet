# Agent Prompt: Build a 2-Page Exam Cheat Sheet (any math course)

## COURSE CONFIGURATION (fill this in before starting)
COURSE: Computer Algebra (SCI19 3112)
YEAR/SEMESTER: 2026
FILE NAME: /midterm/compalg_cheatsheet.tex, /final/compalg_final_cheatsheet.tex
STATUS: both sheets at 2 pages, zero warnings; all numbers verified by computation and cross-checked against official quiz answers (Quizzes 5-8, in /study_materials)
SUPPLIED SOURCES: .md or .txt in '/study_materials' folder; quizzes, homeworks, and any professor notes. '/examples' folder has a reference cheatsheet for formatting and layout.
OFFICIAL ANSWERS AVAILABLE?: in '/study_materials' 

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
- quiz answer-extraction can mangle notation: Quiz6 Q1(c) "z1z2 = 5+i" is actually conj(z1*z2) = conj(z1)*conj(z2) (overline spans the whole product) — recompute before trusting
- quizzes hand you a sin/cos standard-values table; the final may not — keep a compact one on the sheet
- quiz6 C3 = {1, (-1±sqrt3 i)/2}: recognize (−1+sqrt3 i)/2 = omega_3 = e^{2pii/3}; table/gens follow the same iso recipe as C4/C5
- D3 (HW09 triangle symmetries): only HW problem type with no quiz analog — compact fill-recipe on sheet (rot*rot=rot, refl*refl=rot, mixed=refl, r^3=l^2=e, track one vertex)
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
- Equation wrapping rule: never let a line end with a bare `=`. Split chained equalities (`A=B=C≈D`) at controlled `\\` breaks so each line holds one complete computation step; every continuation line starts with its own `=` or operator.
- Parallel computations (find-x lists, sums, splits, tables-with-steps) that wrap raggedly: rebuild as a small inline `$\begin{array}{l}...\end{array}$` (or `{ll}` grid) with a label line above — one item per row, all starting at the same left edge. Costs ~1-3 lines; fund with trims if the page overflows.
- Worked-solutions architecture (midterm mirror): one blue `\section{Worked Solutions (Step-by-Step)}` containing green `\subsection`s per topic block; body uses black `\textbf` labels + red/green inline. Downgrading sections to subsections SAVES space (smaller title + thinner rule + tighter spacing).
- Highlight the 5-8 most important formulas/ideas with a compact `tcolorbox` (`keybox`: small padding, thin rule, e.g. gold background + dark-red frame). Use display-style math inside, never `equation*` inside the box.
- Do NOT define `\hl` as `\textbf{\textcolor{...}}` and use it inside math mode — it breaks. Use `\textcolor{BrickRed}{...}` inside math, plain `\textbf` in text.
- Same ban applies to ALL `\textbf`+`\textcolor` macros (`\wk`, `\ex`, `\kn`): math may appear INSIDE their braces, but never use them INSIDE `$...$` with content containing `^`, `_`, `\frac` (fatal "Missing $ inserted"). When an answer inside math needs color, close math first (`...\Rightarrow$\kn{H}.`), never wrap the caret.
- Color system (function-based, MAX 4 colors + neutrals): RoyalBlue = structure + worked-example templates (`\ex`); OliveGreen = procedures/steps/checks (`\wk`: Step N, Check, recipes, methods); BrickRed = traps/conditions/answers (`\hl`); Goldenrod `kbox` = plug-in theorem boxes. Theory labels stay plain black `\textbf`. Black/gray carry no meaning (body text, section rules). (Retired: orange `\kn`/`obox` merged out — answers went back to red, all boxes goldenrod.)
- After ANY bulk color/label swap, grep for stragglers (e.g. leftover `\textbf{Worked`, `\hl{Check}` vs `\wk{Check}`) — a scanner looking for one color will skip miscolored labels.
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
- First-page timestamp: eso-pic shipout stamp (`\AddToShipoutPicture*` + `\AtTextUpperLeft` + `\raisebox{6pt}` into the margin, right-aligned via `\makebox[\textwidth][r]`) — applied AFTER page composition, so it provably moves nothing (verified: title baselines identical with/without; earlier in-flow and fancyhdr attempts shifted or hid it; 12pt sat on the edge, 6pt clears it). Single compile run suffices (no `remember picture`). Format: `{\scriptsize\textcolor{black!60}{Updated: 23 Sep 2026 06:45}}` (date + 24h local). Bump on EVERY content change.
- After every content edit, recompile and re-verify page count + warnings.

## Output contract
Emit ONLY the raw, production-ready LaTeX code (from `\documentclass` to `\end{document}`), no conversational filler. If the task runs long, prefer one complete compilable file over a stub. Do not use emojis. Do not add code comments unless the user asks.
