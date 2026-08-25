# inngest-docs — local mirror

**This is the source of truth for Inngest behaviour. Verify against these files
before writing or reviewing any Inngest / `@mastra/inngest` code. Never guess.**

Same pattern as `~/Sites/mastra-docs`, `~/Sites/exa-docs`, `~/Sites/firecrawl-docs`.

## What this is

A **partial, sparse** clone of `github.com/inngest/website` — the repo that
renders <https://www.inngest.com/docs>. Upstream docs source, not a scrape.

- Cloned: **2026-08-05**
- `git clone --depth 1 --filter=blob:none --sparse`
- Sparse set excludes `/public`, `/images`, `/assets`. 35 MB.
- Docs live under `pages/docs/**`; marketing blog under `content/blog/**`
  (blog posts are opinion, not contract — cite `pages/docs` for behaviour).

## Where the answers live

| Question | File |
|---|---|
| **Total step-output budget (4MB across ALL steps) and the 1,000-step cap** | `pages/docs/guides/step-parallelism.mdx:230` |
| Per-step output limit, event size, run duration | `pages/docs/usage-limits/inngest.mdx` |
| Per-platform limits (Vercel body size, step cap, fn timeout) | `pages/docs/usage-limits/providers.mdx` |
| **Duplicate step IDs are auto-indexed (`think:0`, `think:1`)** | `pages/docs/learn/inngest-steps.mdx:110` |
| How memoization/replay works, why steps must be deterministic | `pages/docs/learn/how-functions-are-executed.mdx` |
| Changing a function's steps between deploys | `pages/docs/learn/versioning.mdx` |
| Concurrency limits, keys, scopes | `pages/docs/guides/concurrency.mdx` |
| Long-running work, checkpointing, `maxRuntime` | `pages/docs/setup/checkpointing.mdx` |
| Cancellation (`cancelOn`) | `pages/docs/features/inngest-functions/cancellation/` |
| TypeScript SDK reference (v4) | `pages/docs/reference/typescript/v4/**` |

## Refresh

```bash
cd ~/Sites/inngest-docs && git fetch --depth 1 origin main && git reset --hard origin/main
```
