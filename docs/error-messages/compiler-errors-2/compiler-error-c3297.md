---
title: Ошибка компилятора C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 6fed01b0dcf50a657b6eb457ab8e546d0648beec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760103"
---
# <a name="compiler-error-c3297"></a>Ошибка компилятора C3297

"ограничение_2": невозможно использовать "ограничение_1" как ограничение, поскольку "ограничение_1" имеет ограничение значения

Классы значений являются запечатанными. Если ограничение является классом значений, другое ограничение не может производиться от него.

Дополнительные сведения см. в статье [Constraints on Generic Type Parameters (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) (Ограничения, применяемые к параметрам универсальных типов (C++/CLI)).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3297:

```cpp
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```
