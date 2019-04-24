---
title: Ошибка компилятора C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: 7c9c078e72babc85dc7092b8d6414625e9c0db7b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778830"
---
# <a name="compiler-error-c3753"></a>Ошибка компилятора C3753

универсальное свойство не допускается

Списки универсальных параметров могут отображаться только в управляемых классах, структурах или функциях.

Дополнительные сведения см. в разделе [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md) и [свойство](../../extensions/property-cpp-component-extensions.md).

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