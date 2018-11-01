---
title: Ошибка компилятора C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 63817c4181edb942f43f41c24fb10278d14f397e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474742"
---
# <a name="compiler-error-c2665"></a>Ошибка компилятора C2665

«функция»: ни одна из перегрузок Число1 число2 параметра может выполнить преобразование из типа «тип»

Параметр перегруженной функции не может быть преобразован в требуемый тип.  Возможные решения:

- Введите оператор преобразования.

- Используйте явное преобразование.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2665.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```