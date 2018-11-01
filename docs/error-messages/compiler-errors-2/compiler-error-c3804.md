---
title: Ошибка компилятора C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: e83380696aca3d6d45c235925b830bef9e3061a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544590"
---
# <a name="compiler-error-c3804"></a>Ошибка компилятора C3804

«метод_доступа_свойства»: методы доступа для свойства должны либо быть статическими, либо не статическими

При определении нетривиального свойства, функции доступа могут быть либо статическими или экземпляр, но не оба.

Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3804.

```
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```