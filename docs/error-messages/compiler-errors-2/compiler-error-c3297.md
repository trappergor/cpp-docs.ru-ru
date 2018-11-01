---
title: Ошибка компилятора C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 6df8fd3df023602f65c872dedd74da36bbbc6bd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649921"
---
# <a name="compiler-error-c3297"></a>Ошибка компилятора C3297

"ограничение_2": невозможно использовать "ограничение_1" как ограничение, поскольку "ограничение_1" имеет ограничение значения

Классы значений являются запечатанными. Если ограничение является классом значений, другое ограничение не может производиться от него.

Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3297:

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```