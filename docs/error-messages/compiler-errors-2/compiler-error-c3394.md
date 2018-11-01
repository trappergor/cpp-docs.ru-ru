---
title: Ошибка компилятора C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: 4eba2c9f34f1cfcaf97733f914520043ee1124bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557417"
---
# <a name="compiler-error-c3394"></a>Ошибка компилятора C3394

синтаксическая ошибка в предложении ограничения: для найденного "идентификатор" требуется тип

Ограничение было неправильно сформировано.  Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3394:

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```