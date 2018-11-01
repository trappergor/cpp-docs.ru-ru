---
title: Ошибка компилятора C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: c7cbc12bff4e00613032a9d28b5be7533dce9612
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608005"
---
# <a name="compiler-error-c2650"></a>Ошибка компилятора C2650

«operator»: не может быть виртуальная функция

Объект `new` или `delete` оператор объявлен `virtual`. Эти операторы являются `static` члена функции и не может быть `virtual`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2650:

```
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```