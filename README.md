# @zatarain/json-tools

Defensive JSON helpers for Genesis, wrapping `@std/json`'s `JsonValue`
with null-returning accessors for probing untrusted documents.

```genesis
import { tryParse, getString, getNumber, keysOf } from "@pkg/json-tools";

const document = tryParse("{\"name\":\"keyboard\",\"price\":49.99}");
if (document != null) {
    console.log(getString(document, "name"));   // "keyboard"
    console.log(getNumber(document, "price"));  // 49.99
    console.log(getString(document, "missing")); // null
}
```

Exports: `tryParse`, `kindOf`, `hasKey`, `keysOf`, `getString`,
`getNumber`, `getBoolean`. For strict shape validation prefer
`JsonValue.validateAs(Interface)` from `@std/json`.

Install with `gpm`:

```sh
gpm add github:Zatarain-Software-Services/genesis-json-tools@v0.1.0 --alias json-tools
```

License: GPL-3.0 (same as Genesis).
