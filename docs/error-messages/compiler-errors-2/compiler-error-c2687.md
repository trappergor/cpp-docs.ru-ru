---
title: Ошибка компилятора C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: f3e728033a3230d628242aab341377be2f6670ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760261"
---
# <a name="compiler-error-c2687"></a>Ошибка компилятора C2687

"тип": объявление исключения не может быть "void" или заметкой неполного типа, указателя или ссылки на неполный тип

Чтобы тип был частью объявления исключения, он должен быть определен, а не void.

Следующий пример приводит к возникновению ошибки C2687:

```cpp
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Возможное решение

```cpp
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```
