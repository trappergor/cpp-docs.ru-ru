---
title: Ошибка компилятора C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 94c50ccd223567281e02c407e7ee22df75f859d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648803"
---
# <a name="compiler-error-c3454"></a>Ошибка компилятора C3454

в объявлении класса [attribute] не допускается

Чтобы класс был атрибутом, его необходимо определить.

Для получения дополнительной информации см. [attribute](../../windows/attributes/attribute.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3454:

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```