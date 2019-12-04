---
title: Ошибка компилятора C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 21658a659468a6e2a0d911af70eefdaed320446c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745061"
---
# <a name="compiler-error-c2388"></a>Ошибка компилятора C2388

"символ": символ нельзя объявить одновременно с __declspec (AppDomain) и \__declspec (Process)

Одновременное использование модификаторов `appdomain` и `process` `__declspec` для одного символа не допускается. Память для хранения переменной выделяется для каждого процесса или каждого домена приложений.

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

При компиляции следующего примера возникнет ошибка C2388:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
