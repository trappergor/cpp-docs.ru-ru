---
title: Ошибка компилятора C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: 5c725d9648a7800c68a2fbff20e594a400c296c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632557"
---
# <a name="compiler-error-c2821"></a>Ошибка компилятора C2821

первый формальный параметр в «operator new» должен быть «unsigned int»

Первый формальный параметр [оператор new](../../standard-library/new-operators.md#op_new) должно быть беззнаковым `int`.

## <a name="example"></a>Пример

Следующий пример приводит C2821:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```