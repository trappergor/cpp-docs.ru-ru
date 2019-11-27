---
title: Предупреждение компилятора (уровень 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: 43d8a992801d556ce85577f5f9da1bec584cb173
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052132"
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