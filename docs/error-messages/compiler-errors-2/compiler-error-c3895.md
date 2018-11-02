---
title: Ошибка компилятора C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: 61dd280caa3c8c9b28dd77ecab2ed50ab9532d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501288"
---
# <a name="compiler-error-c3895"></a>Ошибка компилятора C3895

«var»: элементы данных типа не может быть «volatile»

Некоторые виды элементов данных, например [литерала](../../windows/literal-cpp-component-extensions.md) или [initonly](../../dotnet/initonly-cpp-cli.md), не может быть [volatile](../../cpp/volatile-cpp.md).

В следующем примере возникает ошибка C3895:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```