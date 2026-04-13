# ECC TLDR - Day-to-Day Usage & Capabilities

## Daily Drivers

### Planning & Implementation
| Command | What it does |
|---------|-------------|
| `/plan "description"` | Creates an implementation plan before you code |
| `/feature-dev` | Full feature development workflow |
| `/build-fix` | Diagnoses and fixes build errors automatically |
| `/checkpoint` | Saves a checkpoint of your current progress |

### Code Quality
| Command | What it does |
|---------|-------------|
| `/code-review` | Reviews your changes for quality, security, patterns |
| `/review-pr 123` | Reviews a GitHub PR by number |
| `/tdd` | Test-driven development workflow (write test first, then implement) |
| `/e2e` | Generates and runs end-to-end tests |
| `/test-coverage` | Analyzes and improves test coverage |
| `/quality-gate` | Runs a full quality check before merging |

### Language-Specific Reviews & Builds
| Command | What it does |
|---------|-------------|
| `/go-review`, `/go-build`, `/go-test` | Go-specific workflows |
| `/rust-review`, `/rust-build`, `/rust-test` | Rust-specific workflows |
| `/python-review` | Python-specific code review |

### Refactoring & Cleanup
| Command | What it does |
|---------|-------------|
| `/refactor-clean` | Cleans up code after refactoring |
| `/prune` | Removes dead code and unused imports |
| `/update-docs` | Updates documentation to match code changes |

### Session & Context
| Command | What it does |
|---------|-------------|
| `/save-session` | Persists session context for later |
| `/resume-session` | Picks up where you left off |
| `/context-budget` | Shows how much context window you're using |
| `/learn` | Extracts reusable patterns from your current session |

### Multi-Agent / Orchestration
| Command | What it does |
|---------|-------------|
| `/multi-plan` | Plans work across multiple agents |
| `/multi-execute` | Executes a multi-agent plan |
| `/devfleet` | Spins up a fleet of specialized agents |
| `/orchestrate` | Coordinates complex multi-step workflows |

---

## Installed Agents (Auto-Delegated)

These are subagents Claude can spawn automatically when the task fits:

- **planner** - Breaks down complex tasks into steps
- **code-reviewer** - Deep code review with security focus
- **build-error-resolver** - Diagnoses build failures
- **tdd-guide** - Guides test-driven development
- **architect / code-architect** - System design decisions
- **security-reviewer** - Security-focused analysis
- **performance-optimizer** - Performance profiling
- **refactor-cleaner** - Safe refactoring
- **Language-specific reviewers** - `csharp-reviewer`, `go-reviewer`, `python-reviewer`, `rust-reviewer`, `typescript-reviewer`
- **Language-specific build resolvers** - `go-build-resolver`, `rust-build-resolver`
- **database-reviewer** - Schema and query review
- **e2e-runner** - End-to-end test execution
- **doc-updater** - Documentation maintenance

---

## Rules (Always Active)

Rules are loaded automatically per-project. You have:

- **common/** - Security, testing, coding style, git workflow, performance, patterns
- **csharp/** - C# conventions, patterns, security, testing
- **golang/** - Go idioms, patterns, security, testing
- **python/** - Python standards, patterns, security, testing
- **rust/** - Rust patterns, ownership, security, testing
- **typescript/** - TS/JS patterns, security, testing

These guide Claude's behavior without you needing to prompt for them.

---

## Skills (Domain Knowledge)

Skills are deeper workflow guides Claude draws from:

- **coding-standards** - Enforced style consistency
- **tdd-workflow** - Full TDD cycle methodology
- **verification-loop** - Continuous verification patterns
- **continuous-learning** - Auto-extracts patterns from sessions
- **api-design** - API design best practices
- **backend-patterns** / **frontend-patterns** - Architecture patterns
- **golang-patterns** / **python-patterns** / **rust-patterns** - Language idioms
- **golang-testing** / **python-testing** / **rust-testing** / **csharp-testing** - Test strategies
- **dotnet-patterns** - .NET ecosystem patterns
- **e2e-testing** - E2E test strategies
- **eval-harness** - Evaluation and benchmarking
- **strategic-compact** - Context window optimization
- **mcp-server-patterns** - MCP server development

---

## What This Can Evolve Into

### Short-Term (Your `internal` Branch)
- **Org-specific rules** - Add your team's coding standards, naming conventions, architecture decisions to `rules/`
- **Internal workflow skills** - Deploy processes, internal tool usage, CI/CD patterns specific to your org
- **Custom agents** - Agents tuned to your codebase (e.g., a reviewer that knows your domain model)
- **Project-specific CLAUDE.md** - Per-repo instructions that reference ECC skills

### Medium-Term
- **Hooks for automation** - Auto-format on save, auto-link Jira tickets, enforce PR templates, run security scans before commit
- **Session learning** - Use `/learn` regularly to build up org-specific patterns that compound over time
- **Custom commands** - `/deploy`, `/release`, `/hotfix`, `/incident` - whatever your team's workflows are
- **Multi-agent workflows** - Orchestrate code review + security scan + test generation in parallel

### Long-Term
- **Self-improving system** - Skills evolve based on session feedback (`/evolve`)
- **Team-wide knowledge base** - Shared skills repo that captures institutional knowledge
- **CI/CD integration** - ECC agents running in pipelines for automated review, test gen, doc updates
- **Cross-project orchestration** - Manage microservices, monorepos, or multi-repo setups with coordinated agents
- **Custom MCP servers** - Connect Claude to your internal APIs, databases, monitoring (see `mcp-configs/`)

---

## Quick Reference

```
# Before coding
/plan "what you want to build"

# While coding
/build-fix          # when something breaks
/checkpoint         # save progress

# Before committing
/code-review        # review your changes
/quality-gate       # full quality check
/tdd                # if you want tests first

# After sessions
/learn              # extract patterns
/save-session       # persist context
```
