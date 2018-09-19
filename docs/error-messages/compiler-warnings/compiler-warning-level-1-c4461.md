---
title: Предупреждение компилятора (уровень 1) C4461 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86c12208c6992b97f30bc36ea821ba26148ff751
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081406"
---
# <a name="compiler-warning-level-1-c4461"></a>Предупреждение компилятора (уровень 1) C4461

«Тип»: этот класс содержит метод завершения «метод_завершения», но нет деструктора «dtor»

Метод завершения в типе предполагает удаление ресурсов. Если метод завершения явно вызывается из деструктора типа, среда CLR определяет время запуска метода завершения, после объект выходит за пределы области.

Если определить деструктор в типе и явным образом вызывать метод завершения из деструктора, определенно можно использовать метод завершения.

Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4461.

```
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```