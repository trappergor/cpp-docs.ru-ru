---
title: Ошибка компилятора C3675 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3675
dev_langs:
- C++
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4b6656753ab4a611dcb80d1473e0b44bf47a270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094784"
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