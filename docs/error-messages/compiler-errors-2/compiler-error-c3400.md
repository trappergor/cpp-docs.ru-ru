---
title: Ошибка компилятора C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: cb4b9d03e10155383f2c58cca07253ae69c2c69a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737508"
---
# <a name="compiler-error-c3400"></a>Ошибка компилятора C3400

циклическая зависимость ограничения, включающая "ограничение_1" и "ограничение_2"

Компилятор обнаружил циклическую зависимость ограничений.

Дополнительные сведения см. в статье [Constraints on Generic Type Parameters (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) (Ограничения, применяемые к параметрам универсальных типов (C++/CLI)).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3400:

```cpp
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```
