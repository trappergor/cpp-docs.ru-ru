---
title: Ошибка компилятора C3455
ms.date: 11/04/2016
f1_keywords:
- C3455
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
ms.openlocfilehash: 4451ddbd8d5a7125112ef8e1c58e8843095bffd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614400"
---
# <a name="compiler-error-c3455"></a>Ошибка компилятора C3455

"атрибут": ни один из конструкторов атрибута не соответствует аргументам

Недопустимое значение использовалось для объявления атрибута.  Дополнительные сведения см. в разделе [attribute](../../windows/attributes/attribute.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3455:

```
// C3455.cpp
// compile with: /clr /c
using namespace System;

[attribute("MyAt")]   // C3455
// try the following line instead
// [attribute(All)]
ref struct MyAttr {
   MyAttr() {}
};
```