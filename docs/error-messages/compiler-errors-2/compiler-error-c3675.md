---
title: Ошибка компилятора C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: e29e536bf89aef887dc043327e4b4596703d0538
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363899"
---
# <a name="compiler-error-c3675"></a>Ошибка компилятора C3675

«функция»: зарезервировано, поскольку определен «свойство»

При объявлении простого свойства компилятор создает get и методы доступа set и их имена присутствуют в рамках программы.  Имена созданных компилятором формируются путем добавления get_ и set_ к имени свойства.  Таким образом нельзя объявлять функции с тем же именем, что созданные компилятором методы доступа.

Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md) .

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