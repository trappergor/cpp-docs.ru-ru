---
title: Ошибка компилятора C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: 3b0ad3aa7395f5f423c8c36f547d4a0e2ad792c1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777107"
---
# <a name="compiler-error-c3669"></a>Ошибка компилятора C3669

«член»: спецификатор переопределения «override» не допускаются статические функции-члены или конструкторы

Переопределения указан неправильно. Дополнительные сведения см. в разделе [явное переопределение](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3669.

```
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```