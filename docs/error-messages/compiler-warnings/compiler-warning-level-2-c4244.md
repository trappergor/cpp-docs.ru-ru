---
title: Предупреждение компилятора (уровень 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: a07adf37314a11cceb72d6675a66d82f7554bbb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162066"
---
# <a name="compiler-warning-level-2-c4244"></a>Предупреждение компилятора (уровень 2) C4244

"аргумент": преобразование из "тип1" в "тип2", возможна утрата данных

Тип с плавающей запятой был преобразован в целочисленный тип.  Возможна потеря данных.

При возникновении ошибки C4244 следует изменить программу так, чтобы использовались совместимые типы, или добавить в код логику, чтобы диапазон возможных значений всегда был совместим с типами, которые вы используете.

Предупреждение C4244 также может срабатывать на уровне 3 и 4; Дополнительные сведения см. в разделе [Предупреждение компилятора (уровни 3 и 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4244.

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
