---
title: Ошибка компилятора C3065
ms.date: 11/04/2016
f1_keywords:
- C3065
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
ms.openlocfilehash: 026a6d5191f5bf7969dd2c8217b624d44b8ca345
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761433"
---
# <a name="compiler-error-c3065"></a>Ошибка компилятора C3065

не допускается объявление свойства не в области класса

Модификатор [свойства](../../cpp/property-cpp.md) __declspec использовался вне класса.  Свойства могут объявляться только внутри класса.

Следующий пример приводит к возникновению ошибки C3065:

```cpp
// C3065.cpp
// compile with: /c
__declspec(property(get=get_i)) int i;   // C3065

class x {
public:
   __declspec(property(get=get_i)) int i;   // OK
};
```
