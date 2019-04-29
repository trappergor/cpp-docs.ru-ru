---
title: Компилятор предупреждение (уровень 1) C4162
ms.date: 11/04/2016
f1_keywords:
- C4162
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
ms.openlocfilehash: 6c6b675fd47cb6e98255515c7cd77c6dd48ea02b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391820"
---
# <a name="compiler-warning-level-1-c4162"></a>Компилятор предупреждение (уровень 1) C4162

«Идентификатор»: функция с компоновкой C найден не

Функция с компоновкой C объявлен, но не удается найти.

Чтобы устранить это предупреждение, компиляцию в c-файла (вызвать компилятор C).  Если необходимо вызвать компилятор C++, поместите extern «C», перед объявлением функции.

Следующий пример приводит к возникновению ошибки C4162

```
// C4162.cpp
// compile with: /c /W1
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)   // C4162

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```

Возможное решение

```
// C4162b.cpp
// compile with: /c
extern "C"
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```