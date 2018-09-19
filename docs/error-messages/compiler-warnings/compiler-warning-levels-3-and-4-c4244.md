---
title: Предупреждение компилятора (уровни 3 и 4) C4244 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55c862ee304c0ad0d95cbde34a5b6bb9b52798d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039508"
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Предупреждение компилятора (уровни 3 и 4) C4244

conversion: преобразование из type1 в type2, возможна потеря данных

Целочисленный тип преобразуется в меньший целочисленный тип. Это предупреждение уровня 4, если *тип1* — `int` и *тип2* меньше, чем `int`. В противном случае это уровень 3 (назначено значение типа [__int64](../../cpp/int8-int16-int32-int64.md) для переменной типа `unsigned int`). Возможна потеря данных.

При возникновении ошибки C4244 следует изменить программу так, чтобы использовались совместимые типы, или добавить в код логику, чтобы диапазон возможных значений всегда был совместим с типами, которые вы используете.

Предупреждение C4244 также могут запускать на уровне 2. см. в разделе [Предупреждение компилятора (уровень 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) Дополнительные сведения.

Это преобразование может вызвать проблемы из-за неявных преобразований.

Следующий пример приводит к возникновению ошибки C4244.

```
// C4244_level4.cpp
// compile with: /W4
int aa;
unsigned short bb;
int main() {
   int b = 0, c = 0;
   short a = b + c;   // C4244

   bb += c;   // C4244
   bb = bb + c;   // C4244
   bb += (unsigned short)aa;   // C4244
   bb = bb + (unsigned short)aa;   // OK
}
```

Дополнительные сведения см. в разделе [обычные арифметические преобразования](../../c-language/usual-arithmetic-conversions.md).

```
// C4244_level3.cpp
// compile with: /W3
int main() {
   __int64 i = 8;
   unsigned int ii = i;   // C4244
}
```

Предупреждение C4244 может возникнуть при создании кода для 64-разрядных сред, который не вызывает предупреждение при построении для 32-разрядных сред. Например, указатели 32-разрядных платформах представлены 32-разрядными значениям, а на 64-разрядных платформах — 64-разрядными.

Следующий пример приводит к возникновению ошибки C4244 при компиляции для 64-разрядных сред:

```
// C4244_level3_b.cpp
// compile with: /W3
int main() {
   char* p1 = 0;
   char* p2 = 0;
   int x = p2 - p1;   // C4244
}
```