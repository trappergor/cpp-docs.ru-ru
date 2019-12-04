---
title: Ошибка компилятора C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: fdfd2200503f80addb120117ce06f5f837d6b9f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752019"
---
# <a name="compiler-error-c2844"></a>Ошибка компилятора C2844

"член": не может быть членом интерфейса "интерфейс"

[Класс интерфейса](../../extensions/interface-class-cpp-component-extensions.md) не может содержать элемент данных, если только он не является также свойством.

В интерфейсе не допускается ничего, кроме свойства или функции-члена. Более того, конструкторы, деструкторы и операторы не допускаются.

Следующий пример приводит к возникновению ошибки C2844:

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
