---
title: Предупреждение компилятора (уровень 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: be79c664f09f80d8f0c8779babf236dccac90ea8
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626232"
---
# <a name="compiler-warning-level-1-c4183"></a>Предупреждение компилятора (уровень 1) C4183

"идентификатор": отсутствует возвращаемый тип; предполагается функция-член, возвращающая "int"

Встроенное определение функции-члена в классе или структуре не имеет возвращаемого типа. Предполагается, что эта функция-член имеет тип возвращаемого значения по умолчанию `int`.

Следующий пример приводит к возникновению ошибки C4183:

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```