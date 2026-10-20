# opencode-trace

This is an OpenCode V2 plugin designed to capture the raw json requests sent to the LLM, and the raw responses back (after streaming-delta consolidation). It saves them into ~/opencode-trace.
- It uses the V2 `ctx.session.hook("http.request")` / `ctx.session.hook("http.response")` hooks. It does not patch `globalThis.fetch`.
- End users should install it as an npm plugin via `"plugins": ["@rmkarasev/opencode-trace"]` in `~/.config/opencode/opencode.json`, or via `opencode plugin add @rmkarasev/opencode-trace`.
- For iterating on the viewer, you can copy `viewer.js` into your ~/opencode-trace directory, or copy examples into this directory, and they'll preferentially pick up `viewer.js` over their embedded viewer code.
- To deploy, `npm version patch`, `npm login`, `npm publish --dry-run`, `npm publish`. Verify with `npm view "@rmkarasev/opencode-trace"`, then test it by installing as above.

# Development
- Run `npm install` once
- Add the local plugin directory to `plugins` in your OpenCode config, e.g. `["D:/Projects-opencode/opencode-trace"]` (V2 expects a directory, not an `index.ts` path)

Then each time you edit:
- `npm run typecheck`
- `npm run lint`
- Exercise it `opencode run --standalone --model opencode/big-pickle "Reply exactly with OK"`
