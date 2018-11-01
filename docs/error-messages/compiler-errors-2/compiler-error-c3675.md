---
title: Ошибка компилятора C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: c154a0fe1989c92bb5e07c0710d3846883d1a113
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546331"
---
# <a name="compiler-error-c3675"></a>Ошибка компилятора C3675

«функция»: зарезервировано, поскольку определен «свойство»

При объявлении простого свойства компилятор создает get и методы доступа set и их имена присутствуют в рамках программы.  Имена созданных компилятором формируются путем добавления get_ и set_ к имени свойства.  Таким образом нельзя объявлять функции с тем же именем, что созданные компилятором методы доступа.

Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3675.

```
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```