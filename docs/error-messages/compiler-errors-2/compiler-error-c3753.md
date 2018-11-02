---
title: Ошибка компилятора C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: b6b1e8c3241a778b29045e734fffebb663554e62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498375"
---
# <a name="compiler-error-c3753"></a>Ошибка компилятора C3753

универсальное свойство не допускается

Списки универсальных параметров могут отображаться только в управляемых классах, структурах или функциях.

Дополнительные сведения см. в разделе [универсальные шаблоны](../../windows/generics-cpp-component-extensions.md) и [свойство](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3753.

```
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```