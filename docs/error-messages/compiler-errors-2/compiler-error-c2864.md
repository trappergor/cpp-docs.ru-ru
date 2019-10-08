---
title: Ошибка компилятора C2864
ms.date: 10/04/2019
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 122e0455f84d8940eda04f3968e883dd1f0cd444
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998666"
---
# <a name="compiler-error-c2864"></a>Ошибка компилятора C2864

> "*member-Name*": статический элемент данных с инициализатором в классе должен иметь постоянный целочисленный тип const

## <a name="remarks"></a>Примечания

Чтобы инициализировать элемент данных `static`, который определен как `volatile`, non-`const` или не является целочисленным типом, используйте оператор определения члена. Они не могут быть инициализированы в объявлении.

## <a name="example"></a>Пример

Этот пример приводит к возникновению ошибки C2864:

```cpp
// C2864.cpp
// compile with: /c
class B  {
private:
   int a = 3;   // OK
   static int b = 3;   // C2864
   volatile static int c = 3;   // C2864
   volatile static const int d = 3;   // C2864
   static const long long e = 3;   // OK
   static const double f = 3.33;   // C2864
};
```

В этом примере показано, как исправить ошибку C2864:

```cpp
// C2864b.cpp
// compile with: /c
class C  {
private:
   int a = 3;
   static int b; // = 3; C2864
   volatile static int c; // = 3; C2864
   volatile static const int d; // = 3; C2864
   static const long long e = 3;
   static const double f; // = 3.33; C2864
};

// Initialize static volatile, non-const, or non-integral
// data members when defined, not when declared:
int C::b = 3;
volatile int C::c = 3;
volatile const int C::d = 3;
const double C::f = 3.33;
```
