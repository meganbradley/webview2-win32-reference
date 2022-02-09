---
description: This interface is an extension of the ICoreWebView2CompositionController.
title: WebView2 Win32 C++ ICoreWebView2ExperimentalCompositionController4
ms.date: 01/14/2022
keywords: IWebView2, IWebView2WebView, webview2, webview, win32 apps, win32, edge, ICoreWebView2, ICoreWebView2Controller, browser control, edge html, ICoreWebView2ExperimentalCompositionController4
---

# interface ICoreWebView2ExperimentalCompositionController4

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCompositionController4
  : public IUnknown
```

This interface is an extension of the [ICoreWebView2CompositionController](icorewebview2compositioncontroller.md).

## Summary

 Members                        | Descriptions
--------------------------------|---------------------------------------------
[CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) | A helper function to convert a pointerId received from the system into an ICoreWebView2ExperimentalPointerInfo.
[get_UIAProvider](#get_uiaprovider) | Returns the UI Automation Provider for the WebView.
[COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND](#corewebview2_context_menu_item_kind) | Specifies the menu item kind for the [ICoreWebView2ExperimentalContextMenuItem::get_Kind](icorewebview2experimentalcontextmenuitem.md) method.
[COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND](#corewebview2_context_menu_target_kind) | Indicates the kind of context for which the context menu was created for the `ICoreWebView2ContextMenuTarget::get_Kind` method.
[COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4) | Matrix that represents a 3D transform.
[COREWEBVIEW2_MEMORY_USAGE_TARGET_LEVEL](#corewebview2_memory_usage_target_level) | Specifies memory usage target level of WebView.
[COREWEBVIEW2_PDF_TOOLBAR_ITEMS](#corewebview2_pdf_toolbar_items) | Specifies the PDF toolbar item types used for the `ICoreWebView2ExperimentalSettings::put_HiddenPdfToolbarItems` method.
[COREWEBVIEW2_PROCESS_KIND](#corewebview2_process_kind) | 
[COREWEBVIEW2_UPDATE_RUNTIME_STATUS](#corewebview2_update_runtime_status) | Status of UpdateRuntime operation result.

An object implementing ICoreWebView2ExperimentalCompositionController4 interface will also implement [ICoreWebView2CompositionController](icorewebview2compositioncontroller.md).

## Applies to

Product                         | Introduced
--------------------------------|---------------------------------------------
WebView2 Win32            |    N/A
WebView2 Win32 Prerelease |    1.0.790

## Members

#### CreateCoreWebView2PointerInfoFromPointerId

A helper function to convert a pointerId received from the system into an ICoreWebView2ExperimentalPointerInfo.

> public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT pointerId, HWND parentWindow, struct [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4) transform, [ICoreWebView2PointerInfo](icorewebview2pointerinfo.md) ** pointerInfo)

parentWindow is the HWND that contains the WebView. This can be any HWND in the hwnd tree that contains the WebView. The [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4) is the transform from that HWND to the WebView. The returned ICoreWebView2ExperimentalPointerInfo is used in SendPointerInfo. The pointer type must be either pen or touch or the function will fail.

#### get_UIAProvider

Returns the UI Automation Provider for the WebView.

> public HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown ** provider)

#### COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND

Specifies the menu item kind for the [ICoreWebView2ExperimentalContextMenuItem::get_Kind](icorewebview2experimentalcontextmenuitem.md) method.

> enum [COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND](#corewebview2_context_menu_item_kind)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND_COMMAND            | Specifies a command menu item kind.
COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND_CHECK_BOX            | Specifies a check box menu item kind.
COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND_RADIO            | Specifies a radio button menu item kind.
COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND_SEPARATOR            | Specifies a separator menu item kind.
COREWEBVIEW2_CONTEXT_MENU_ITEM_KIND_SUBMENU            | Specifies a submenu menu item kind.

#### COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND

Indicates the kind of context for which the context menu was created for the `ICoreWebView2ContextMenuTarget::get_Kind` method.

> enum [COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND](#corewebview2_context_menu_target_kind)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND_PAGE            | Indicates that the context menu was created for the page without any additional content.
COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND_IMAGE            | Indicates that the context menu was created for an image element.
COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND_SELECTED_TEXT            | Indicates that the context menu was created for selected text.
COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND_AUDIO            | Indicates that the context menu was created for an audio element.
COREWEBVIEW2_CONTEXT_MENU_TARGET_KIND_VIDEO            | Indicates that the context menu was created for a video element.

This enum will always represent the active element that caused the context menu request. If there is a selection with multiple images, audio and text, for example, the element that the end user right clicks on within this selection will be the option represented by this enum.

#### COREWEBVIEW2_MATRIX_4X4

Matrix that represents a 3D transform.

> typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)

This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId. This is equivalent to a D2D1_MATRIX_4X4_F

#### COREWEBVIEW2_MEMORY_USAGE_TARGET_LEVEL

Specifies memory usage target level of WebView.

> enum [COREWEBVIEW2_MEMORY_USAGE_TARGET_LEVEL](#corewebview2_memory_usage_target_level)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_MEMORY_USAGE_TARGET_LEVEL_NORMAL            | Specifies normal memory usage target level.
COREWEBVIEW2_MEMORY_USAGE_TARGET_LEVEL_LOW            | Specifies low memory usage target level.

#### COREWEBVIEW2_PDF_TOOLBAR_ITEMS

Specifies the PDF toolbar item types used for the `ICoreWebView2ExperimentalSettings::put_HiddenPdfToolbarItems` method.

> enum [COREWEBVIEW2_PDF_TOOLBAR_ITEMS](#corewebview2_pdf_toolbar_items)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_PDF_TOOLBAR_ITEMS_NONE            | No item.
COREWEBVIEW2_PDF_TOOLBAR_ITEMS_SAVE            | The save button.
COREWEBVIEW2_PDF_TOOLBAR_ITEMS_PRINT            | The print button.
COREWEBVIEW2_PDF_TOOLBAR_ITEMS_SAVE_AS            | The save as button.

#### COREWEBVIEW2_PROCESS_KIND

> enum [COREWEBVIEW2_PROCESS_KIND](#corewebview2_process_kind)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_PROCESS_KIND_BROWSER            | Indicates the browser process kind.
COREWEBVIEW2_PROCESS_KIND_RENDERER            | Indicates the render process kind.
COREWEBVIEW2_PROCESS_KIND_UTILITY            | Indicates the utility process kind.
COREWEBVIEW2_PROCESS_KIND_SANDBOX_HELPER            | Indicates the sandbox helper process kind.
COREWEBVIEW2_PROCESS_KIND_GPU            | Indicates the GPU process kind.
COREWEBVIEW2_PROCESS_KIND_PPAPI_PLUGIN            | Indicates the PPAPI plugin process kind.
COREWEBVIEW2_PROCESS_KIND_PPAPI_BROKER            | Indicates the PPAPI plugin broker process kind.

#### COREWEBVIEW2_UPDATE_RUNTIME_STATUS

Status of UpdateRuntime operation result.

> enum [COREWEBVIEW2_UPDATE_RUNTIME_STATUS](#corewebview2_update_runtime_status)

 Values                         | Descriptions
--------------------------------|---------------------------------------------
COREWEBVIEW2_UPDATE_RUNTIME_STATUS_LATEST_VERSION_INSTALLED            | Latest version of Edge WebView2 Runtime is installed.
COREWEBVIEW2_UPDATE_RUNTIME_STATUS_UPDATE_ALREADY_RUNNING            | Edge WebView2 Runtime update is already running, which could be triggered by auto update or by other UpdateRuntime request from some app.
COREWEBVIEW2_UPDATE_RUNTIME_STATUS_BLOCKED_BY_POLICY            | Edge WebView2 Runtime update is blocked by group policy.
COREWEBVIEW2_UPDATE_RUNTIME_STATUS_FAILED            | Edge WebView2 Runtime update failed.
