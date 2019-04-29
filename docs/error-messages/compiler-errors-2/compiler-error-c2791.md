---
title: Ошибка компилятора C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 66a111ea6fe2ca5acfbc473d19da62d9de67372a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360168"
---
# <a name="compiler-error-c2791"></a>Ошибка компилятора C2791

Недопустимое использование «Super»: «класс» не имеет базовых классов

Ключевое слово [super](../../cpp/super.md) было использовано в контексте функции-члена класса, который не имеет базовых классов.

Следующий пример приводит к возникновению ошибки C2791:

```
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```