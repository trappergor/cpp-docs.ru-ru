---
title: Ошибка компилятора C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 8c7f4a2861825a35d676328b5e283a5e4087d85b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519786"
---
# <a name="compiler-error-c3904"></a>Ошибка компилятора C3904

«метод_доступа_свойства»: необходимо указать номера следующими параметрами:

Проверьте число параметров в вашей `get` и `set` методы с измерениями свойства.

- Число параметров для `get` метод должен быть равно числу измерений свойства или равняться нулю для неиндексируемых свойств.

- Число параметров `set` метод должен быть один больше, чем количество измерений свойства.

Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3904.

```
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3904.

```
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```