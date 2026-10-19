# opencode-trace

This is a plugin designed to capture the raw json requests sent to the LLM, and the raw responses back (after streaming-delta consolidation). It saves them into ~/opencode-trace
- End users should install it as an npm plugin via `"plugin": ["@ljw1004/opencode-trace"]` in `~/.config/opencode/opencode.json`.
- For iterating on the viewer, you can copy `viewer.js` into your ~/opencode-trace directory, or copy examples into this directory, and they'll preferentially pick up `viewer.js` over their embedded viewer code.
- To deploy, `npm version patch`, `npm login`, `npm publish --dry-run`, `npm publish`. Verify with `npm view "@ljw1004/opencode-trace"`, then test it by installing as above.

# Development
- Run `npm install` once
- Change the plugin line to `["/path/to/opencode-trace/index.ts"]`

Then each time you edit:
- `npm run typecheck`
- `npm run lint`
- Exercise it `opencode run --model opencode/big-pickle "Short question: what your model name?"`