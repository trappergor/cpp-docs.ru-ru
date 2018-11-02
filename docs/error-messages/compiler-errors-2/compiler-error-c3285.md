---
title: Ошибка компилятора C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: 6bc211fb2394a9a2989702c13e19bd63ea8a5ad7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444633"
---
# <a name="compiler-error-c3285"></a>Ошибка компилятора C3285

Оператор for each не может работать с переменными типа "тип"

Оператор `for each` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов.

Дополнительные сведения см. в разделе [for each, in](../../dotnet/for-each-in.md) .

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3285.

```
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```