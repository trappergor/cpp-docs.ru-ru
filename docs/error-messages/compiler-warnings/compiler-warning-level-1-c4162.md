---
title: Предупреждение компилятора (уровень 1) C4162
ms.date: 11/04/2016
f1_keywords:
- C4162
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
ms.openlocfilehash: 7e70898065a40a965b08b090bc59263acd918515
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624850"
---
# <a name="compiler-warning-level-1-c4162"></a>Предупреждение компилятора (уровень 1) C4162

"идентификатор": функция с компоновкой C не найдена

Функция с компоновкой C объявлена, но не может быть найдена.

Чтобы устранить это предупреждение, скомпилируйте файл в c (вызовите компилятор C).  Если необходимо вызвать C++ компилятор, поместите внешний "C" перед объявлением функции.

Следующий пример приводит к возникновению ошибки C4162

```cpp
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

```cpp
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