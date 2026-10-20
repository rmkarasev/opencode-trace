# opencode-trace

This OpenCode V2 plugin lets you see the raw json requests made to the LLM, and the responses.
* Example: https://ljw1004.github.io/opencode-trace/example.html

## Installation

Add the package to your OpenCode config:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "plugins": ["@rmkarasev/opencode-trace"]
}
```

Or install it with the CLI:

```sh
opencode plugin add @rmkarasev/opencode-trace
```

Restart OpenCode and you'll see each transcript stored in `~/opencode-trace`.

To update the plugin later:

```sh
opencode plugin update
```
