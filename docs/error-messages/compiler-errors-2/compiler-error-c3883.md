---
title: Ошибка компилятора C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 51ecf5fbc793c02a23e2aa02fb08e37ebe4b0ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559774"
---
# <a name="compiler-error-c3883"></a>Ошибка компилятора C3883

«var»: статические данные-член initonly должен быть инициализирован

Переменная, помеченная как с [initonly](../../dotnet/initonly-cpp-cli.md) не был правильно инициализирован.

Следующий пример приводит к возникновению ошибки C3883:

```
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

В следующем примере показано возможное решение:

```
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

Ниже приведен пример, как инициализировать в статическом конструкторе:

```
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```