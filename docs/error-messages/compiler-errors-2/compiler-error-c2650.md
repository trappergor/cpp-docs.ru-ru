---
title: Ошибка компилятора C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: c7cbc12bff4e00613032a9d28b5be7533dce9612
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152570"
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