---
title: Ошибка компилятора C2555 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f91ec33db2d3a7b6772556233a3c99b501ede76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017343"
---
# <a name="compiler-error-c2555"></a>Ошибка компилятора C2555

«class1::function1»: переопределение виртуальной функции возвращают тип отличается и не является ковариантным «класс2::функция 2»

Виртуальная функция и производная переопределенной функции имеют идентичные списки параметров, кроме различные возвращаемые типы. Функцию переопределения в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого.

Чтобы устранить эту ошибку, необходимо привести возвращаемое значение после вызова виртуальной функции.

Эта ошибка может также возникает при компиляции с параметром/CLR.   Например в Visual C++ эквивалентно следующее объявление C#:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

является

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Дополнительные сведения о C2555 см. в статье базы знаний Q240862.

Следующий пример приводит к возникновению ошибки C2555:

```
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```