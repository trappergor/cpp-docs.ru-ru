---
title: Ошибка компилятора C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 62afcb1fafc19d3d61a86f2fbc10cb99e095afc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393666"
---
# <a name="compiler-error-c2388"></a>Ошибка компилятора C2388

«символ»: символ не может объявляться с обоих параметрами __declspec(appdomain) и \__declspec(process)

Одновременное использование модификаторов `appdomain` и `process` `__declspec` для одного символа не допускается. Память для хранения переменной выделяется для каждого процесса или каждого домена приложений.

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

При компиляции следующего примера возникнет ошибка C2388:

```
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```