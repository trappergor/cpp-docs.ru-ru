---
title: Ошибка компилятора C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 50148f4fb5c3af33d8de8b005f75f491b0540271
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225505"
---
# <a name="compiler-error-c2388"></a>Ошибка компилятора C2388

"символ": символ не может быть объявлен одновременно с __declspec (AppDomain) и \_ _declspec (Process)

`appdomain` `process` **`__declspec`** Модификаторы и не могут использоваться для одного и того же символа. Память для хранения переменной выделяется для каждого процесса или каждого домена приложений.

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

При компиляции следующего примера возникнет ошибка C2388:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
