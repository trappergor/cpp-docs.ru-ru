---
title: Ошибка компилятора C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: d7c55ede285d027b1a65b33adbf6407df243f068
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635643"
---
# <a name="compiler-error-c3824"></a>Ошибка компилятора C3824

«член»: этот тип не может использоваться в этом контексте (параметр функции, тип возвращаемого значения или статический член)

Закрепляющие указатели не может иметь параметры функции, типы возвращаемых значений или объявлен `static`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3824:

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
