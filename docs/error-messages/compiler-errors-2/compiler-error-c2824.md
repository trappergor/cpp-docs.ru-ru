---
title: Ошибка компилятора C2824
ms.date: 11/04/2016
f1_keywords:
- C2824
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
ms.openlocfilehash: 226fc078312a214c561e80064474ee237245c0f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406942"
---
# <a name="compiler-error-c2824"></a>Ошибка компилятора C2824

возвращаемый тип для «operator new» должен быть "void *"

Не на основе указателей, при перегрузке оператора `new` должен возвращать `void *`.

Следующий пример приводит к возникновению ошибки C2824:

```
// C2824.cpp
// compile with: /c
class   A {
   A* operator new(size_t i, char *m);   // C2824
   // try the following line instead
   // void* operator new(size_t i, char *m);
};
```