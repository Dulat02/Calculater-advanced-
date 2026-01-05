# Advanced Calculator

A polished, accessible calculator built with plain HTML, CSS, and JavaScript.

This project provides:
- A senior-style expression pipeline (tokenizer → parser (shunting-yard) → RPN evaluator)
- Support for unary minus, exponentiation (^), parentheses, functions, and constants
- Built-in functions: sin, cos, tan, sqrt, ln, log, exp, abs
- Memory (MC, MR, M+, M-), answer recall (ANS), and a small history panel
- Keyboard support and basic accessibility (ARIA)
- No use of eval — safer parsing and evaluation

Demo
- Open `index.html` in a modern browser. If you have the single-file `index.html` (CSS inline), you can open it directly by double-clicking.
- If you use the separate-file variant, serve the folder with a simple static server (recommended) to avoid module/CORS issues:
  - Python 3: `python -m http.server 8000` → http://localhost:8000
  - VS Code: Live Server extension
  - Node: `npx serve` or a similar static server

Features
- Arithmetic: +, -, *, /, ^
- Parentheses and operator precedence
- Unary minus (e.g., -3)
- Functions: sin(x), cos(x), tan(x), sqrt(x), ln(x), log(x), exp(x), abs(x)
- Constants: π (pi), e
- Memory operations: MC, MR, M+, M-
- ANS token (last evaluated result)
- History of previous expressions with clickable entries
- Robust error messages (e.g., division by zero, malformed expression)

Files
- `index.html` — app markup (single-file or loads `script.js`)
- `styles.css` — styling
- `script.js` — tokenizer / parser / evaluator and UI orchestration
- `README.md` — this file
- `LICENSE` — MIT license (recommended)

Quick start (local)
1. Clone the repo:
   ```
   git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
   cd YOUR-REPO
   ```
2. Open directly:
   - If you have the single-file `index.html`, double-click it or open it in your browser.
3. Serve locally (recommended if using separated files or modules):
   ```
   python -m http.server 8000
   # then open http://localhost:8000
   ```

Usage
- Click buttons or type on the keyboard.
- Keyboard controls:
  - Numbers: 0–9
  - Decimal: `.`
  - Operators: `+ - * / ^`
  - Parentheses: `( )`
  - Enter or `=` to evaluate
  - Backspace to delete
  - Esc to clear
  - Type function names (e.g., `sin(1.57)`) directly

Examples
- Basic: `2+2` → `4`
- Precedence: `2+3*4` → `14`
- Unary minus: `-5+3` → `-2`
- Power: `2^3` → `8`
- Functions: `sqrt(9)`, `sin(pi/2)`, `log(100)`

Development notes
- The code avoids `eval` and uses a tokenizer → parser → RPN evaluator pipeline for safety and maintainability.
- To extend functions or constants, update the `Evaluator` and `Tokenizer` classes in `script.js`.
- Suggested improvements:
  - Add unit tests for tokenizer/parser/evaluator (Jest/Vitest)
  - Convert to TypeScript for stronger tooling and types
  - Add linting (ESLint + Prettier) and GitHub Actions CI
  - Add input caret & selection support for editing expressions

Contributing
- Contributions welcome. Open issues for bugs or feature requests.
- If you plan to submit a PR, please:
  - Add tests for new parsing/evaluation behavior
  - Keep changes small and focused
  - Include a short description of the change and why it's needed

Deployment (GitHub Pages)
- To publish with GitHub Pages from `main`:
  1. Push your repo to GitHub.
  2. In repository Settings → Pages, set source to `main` branch and `/ (root)` or `/docs` if you place files there.
  3. Your site will be published at `https://<your-username>.github.io/<your-repo>/`.

License
- MIT License by default. See the `LICENSE` file for details.

Credits
- Built with vanilla HTML, CSS, and JavaScript.
- Author: Dulat02

If you'd like, I can:
- Add screenshots or a demo GIF to this README,
- Add unit test examples and a CI workflow,
- Produce a small changelog or release notes template.
