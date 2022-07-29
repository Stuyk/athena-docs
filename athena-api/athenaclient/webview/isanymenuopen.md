---
description: AthenaClient.webview.isAnyMenuOpen
---

# isAnyMenuOpen

Checks if any menu is open.

### Usage

Arguments

* excludeChat -> boolean = false (optional)
  * If true, ignore if the chat is open.

Returns

* Returns a boolean. True if any menu is open, false if not.

```typescript
const isAnyMenuOpen = AthenaClient.webview.isAnyMenuOpen();
if (isAnyMenuOpen) {
  return;
}

```
