---
title: Ошибка компилятора C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: b917c0a2c15aeb70222c948bce9a6fb275c91068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207250"
---
# <a name="compiler-error-c2144"></a>Ошибка компилятора C2144

> Синтаксическая ошибка: перед "*Type*" должен стоять "*Token*"

Компилятор ожидал *токен* и не обнаружил *тип* .

Эта ошибка может быть вызвана отсутствием закрывающей фигурной скобки, правой круглой скобкой или точкой с запятой.

C2144 также может возникнуть при попытке создать макрос из ключевого слова CLR, содержащего символ пробела.

Если вы пытаетесь выполнить перенаправление, можно также увидеть C2144. Дополнительные сведения см. в разделе [Переадресация типов (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2144 и демонстрирует способ исправления:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Следующий пример приводит к возникновению ошибки C2144 и демонстрирует способ исправления:

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
