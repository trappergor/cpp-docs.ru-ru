---
title: Ошибка компилятора C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: d05a861a2baedb86482503b6860098f12c41bd78
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767178"
---
# <a name="compiler-error-c3399"></a>Ошибка компилятора C3399

"тип": не удается предоставить аргументы при создании экземпляра универсального параметра

При указании ограничения `gcnew()` можно указать что тип ограничения будет иметь конструктор без параметров. Таким образом, при попытке создания экземпляра этого типа и передачи параметра возникает эта ошибка.

См. в разделе [ограничений для параметров универсального типа (C++выполняет)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) Дополнительные сведения.

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