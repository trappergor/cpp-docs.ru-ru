---
title: Предупреждение компилятора (уровень 1) C4441
ms.date: 11/04/2016
f1_keywords:
- C4441
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
ms.openlocfilehash: 45d7a6af09677c1e63dab5ffcc55c35d8203b40b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408242"
---
# <a name="compiler-warning-level-1-c4441"></a>Предупреждение компилятора (уровень 1) C4441

соглашения о вызове «соглашение1» игнорируется; Вместо него используется «соглашение2»

Необходимо использовать функции-члены в управляемом определяемых пользователем типов и универсальных шаблонов глобальных функций [__clrcall](../../cpp/clrcall.md) соглашение о вызовах.  Компилятор, используемый `__clrcall`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4441.

```
// C4441.cpp
// compile with: /clr /W1 /c
generic <class ItemType>
void __cdecl Test(ItemType item) {}   // C4441
// try the following line instead
// void Test(ItemType item) {}

ref struct MyStruct {
   void __cdecl Test(){}   // C4441
   void Test2(){}   // OK
};
```