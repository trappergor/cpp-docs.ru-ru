---
title: Ошибка компилятора C2382
ms.date: 11/04/2016
f1_keywords:
- C2382
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
ms.openlocfilehash: 4115a01f9e4dcab31a05bb3994109e97694121e6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344859"
---
# <a name="compiler-error-c2382"></a>Ошибка компилятора C2382

"функция": переопределение; разные спецификации исключений

При использовании параметра [/Za](../../build/reference/za-ze-disable-language-extensions.md)эта ошибка означает, что предпринята попытка перегрузки функции только в [спецификации исключений](../../cpp/exception-specifications-throw-cpp.md).

Следующий пример приводит к возникновению ошибки C2382:

```
// C2382.cpp
// compile with: /Za /c
void f1(void) throw(int) {}
void f1(void) throw(char) {}   // C2382
void f2(void) throw(char) {}   // OK
```