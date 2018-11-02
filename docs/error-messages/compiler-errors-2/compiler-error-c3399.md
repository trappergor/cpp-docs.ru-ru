---
title: Ошибка компилятора C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: e400c181f987a83588f8aedc63ecdedb82be310f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568688"
---
# <a name="compiler-error-c3399"></a>Ошибка компилятора C3399

"тип": не удается предоставить аргументы при создании экземпляра универсального параметра

При указании ограничения `gcnew()` можно указать что тип ограничения будет иметь конструктор без параметров. Таким образом, при попытке создания экземпляра этого типа и передачи параметра возникает эта ошибка.

См. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3399.

```
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```