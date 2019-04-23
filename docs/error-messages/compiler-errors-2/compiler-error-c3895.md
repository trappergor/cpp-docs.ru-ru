---
title: Ошибка компилятора C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: c4b1cad9ef48f1f16b411aab46e1bb9285d69ff3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779302"
---
# <a name="compiler-error-c3895"></a>Ошибка компилятора C3895

«var»: элементы данных типа не может быть «volatile»

Некоторые виды элементов данных, например [литерала](../../extensions/literal-cpp-component-extensions.md) или [initonly](../../dotnet/initonly-cpp-cli.md), не может быть [volatile](../../cpp/volatile-cpp.md).

В следующем примере возникает ошибка C3895:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```