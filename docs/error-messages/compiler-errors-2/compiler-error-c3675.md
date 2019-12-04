---
title: Ошибка компилятора C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 6772572d29765370d6cdbf52ed8470ff2f3f054e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758077"
---
# <a name="compiler-error-c3675"></a>Ошибка компилятора C3675

"функция": зарезервировано, так как определено "свойство"

При объявлении простого свойства компилятор создает методы доступа get и Set, и эти имена находятся в области программы.  Создаваемые компилятором имена формируются с помощью предустановленного get_ и set_ к имени свойства.  Поэтому нельзя объявлять функции с тем же именем, что и методы доступа, создаваемые компилятором.

Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3675.

```cpp
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```
