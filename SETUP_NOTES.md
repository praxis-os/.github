# Setup Notes

GitHub organization settings that are not fully expressed in git-tracked files. These require manual configuration through the GitHub UI.

## Organization profile

- [ ] Set organization avatar / logo
- [ ] Set organization display name
- [ ] Set organization bio (suggested below)
- [ ] Set organization website URL
- [ ] Set contact email
- [ ] Optionally set location

### Suggested organization bio

> Production-grade Go ecosystem for building and operating agentic systems. Current focus: `praxis`, the runtime kernel.

## Pinned repositories

**Current** (while only the kernel exists):

1. `praxis`

**When additional repos are available:**

1. `praxis`
2. docs repo
3. examples repo
4. benchmarks repo
5. `praxis-os`

Do not pin `.github` unless there are too few meaningful repos to show.

## Repository metadata

For each public repository, set:

- [ ] Repository description (concise, accurate)
- [ ] Topics (e.g., `go`, `agents`, `llm`, `observability`, `runtime`)
- [ ] Social preview image

## Branch protection

- [ ] Protect `main` branch on this repository
- [ ] Protect `main` on `praxis` and all future public repositories
- [ ] Require pull request reviews before merging
- [ ] Require status checks to pass before merging (when CI is configured)

## GitHub Projects / roadmap

For now, keep the roadmap in `ROADMAP.md`. Consider a lightweight public GitHub Project only when there is enough issue volume to justify it.

## Additional settings

- [ ] Verify organization email domain (when a custom domain is ready)
- [ ] Configure default repository permissions for organization members
- [ ] Review GitHub Actions permissions and allowed actions for public repos
