---
title: Ошибка компилятора C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: efe882db447b9ebc69d02e3b10d9e484a3cfd8a8
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520452"
---
# <a name="compiler-error-c3386"></a>Ошибка компилятора C3386

> "*Type-Name*": `__declspec(dllexport)` / `__declspec(dllimport)` не может применяться к типу управляемого или WinRT

[`dllimport`](../../cpp/dllexport-dllimport.md) [`dllexport`](../../cpp/dllexport-dllimport.md) **`__declspec`** Модификаторы и не являются допустимыми для управляемого или среда выполнения Windowsого типа.

В следующем примере показано возникновение ошибки C3386 и приводятся сведения по ее устранению.

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
