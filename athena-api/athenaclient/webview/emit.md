---
description: AthenaClient.webview.emit
---

# emit

Emits an event to the webview.

### Usage

Arguments

* eventName -> string
  * Name of the event.
* ... -> (...args: any[]) => void
  * Arguments to pass to the callback.

Returns

* Returns a void.

```typescript
AthenaClient.webview.emit(ExampleWebViewEvents.ClientToWebView.LOAD_PLAYERS, players);
```
