---
title: Предупреждение компилятора (уровень 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 246eed6592b892c3bd233d9217e26e7bf7a49ff8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502312"
---
# <a name="compiler-warning-level-3-c4645"></a>Предупреждение компилятора (уровень 3) C4645

функция, объявленная с атрибутом __declspec(noreturn) имеет оператор return

В функции, помеченной модификатором " [noreturn](../../cpp/noreturn.md) ", обнаружена инструкция [return](../../cpp/program-termination.md) **`__declspec`** . **`return`** Инструкция была пропущена.

Следующий пример приводит к возникновению ошибки C4645.

```cpp
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```
