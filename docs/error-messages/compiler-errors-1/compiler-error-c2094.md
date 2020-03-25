---
title: Ошибка компилятора C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 022fca01706fefca2a14ea952586ec91b0c5b240
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207688"
---
# <a name="compiler-error-c2094"></a>Ошибка компилятора C2094

метка "идентификатор" не определена

Метка, используемая оператором [goto](../../cpp/goto-statement-cpp.md) , не существует в функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2094:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Возможное решение

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```
