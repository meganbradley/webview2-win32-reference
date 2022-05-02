---
description: Receives `WebResourceResponseReceived` events.
title: WebView2 Win32 C++ ICoreWebView2WebResourceResponseReceivedEventHandler
ms.date: 05/02/2022
keywords: IWebView2, IWebView2WebView, webview2, webview, win32 apps, win32, edge, ICoreWebView2, ICoreWebView2Controller, browser control, edge html, ICoreWebView2WebResourceResponseReceivedEventHandler
---

# interface ICoreWebView2WebResourceResponseReceivedEventHandler

```
interface ICoreWebView2WebResourceResponseReceivedEventHandler
  : public IUnknown
```

Receives `WebResourceResponseReceived` events.

## Summary

 Members                        | Descriptions
--------------------------------|---------------------------------------------
[Invoke](#invoke) | Provides the event args for the corresponding event.

## Applies to

Product                         | Introduced
--------------------------------|---------------------------------------------
WebView2 Win32            |    1.0.705.50
WebView2 Win32 Prerelease |    1.0.721

## Members

#### Invoke

Provides the event args for the corresponding event.

> public HRESULT [Invoke](#invoke)(ICoreWebView2 * sender, ICoreWebView2WebResourceResponseReceivedEventArgs * args)
