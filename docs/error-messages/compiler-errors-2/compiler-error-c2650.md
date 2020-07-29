---
title: Ошибка компилятора C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: 102c6f713027917104cd46894fad0775076359c9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216145"
---
# <a name="compiler-error-c2650"></a>Ошибка компилятора C2650

"оператор": не может быть виртуальной функцией

**`new`** **`delete`** Объявлен оператор или **`virtual`** . Эти операторы являются **`static`** функциями членов и не могут быть **`virtual`** .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2650:

```cpp
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```
