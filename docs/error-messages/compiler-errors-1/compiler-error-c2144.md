---
title: Ошибка компилятора C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: a75330d26b0924e60f7e46d10d617341709d7e23
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778290"
---
# <a name="compiler-error-c2144"></a>Ошибка компилятора C2144

> Синтаксическая ошибка: "*тип*«должно предшествовать»*маркера*"

Компилятор ожидал *маркера* и найти *тип* вместо этого.

Эта ошибка может быть вызвана отсутствует закрывающую фигурную скобку, правая круглая скобка или точка с запятой.

C2144 также может возникать при попытке создать макрос из CLR ключевое слово, которое содержит символ пробела.

C2144 может отображаться также в том случае, если вы пытаетесь передачи типа. См. в разделе [Переадресация типа (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md) Дополнительные сведения.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2144 и показывает способ ее устранения:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Следующий пример приводит к возникновению ошибки C2144 и показывает способ ее устранения:

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```