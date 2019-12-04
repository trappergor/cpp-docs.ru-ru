---
title: Ошибка компилятора C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: d20b5e816930969278536fe3771df4ad38c3c86b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737521"
---
# <a name="compiler-error-c3399"></a>Ошибка компилятора C3399

"тип": не удается предоставить аргументы при создании экземпляра универсального параметра

При указании ограничения `gcnew()` можно указать что тип ограничения будет иметь конструктор без параметров. Таким образом, при попытке создания экземпляра этого типа и передачи параметра возникает эта ошибка.

Дополнительные сведения см. [в разделе ограниченияC++для параметров универсального типа (/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3399.

```cpp
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```
