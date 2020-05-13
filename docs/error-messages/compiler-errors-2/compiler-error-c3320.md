---
title: Ошибка компилятора C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 0289d49ebbb0e30153beb6b0b2bc758bff5ef118
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201309"
---
# <a name="compiler-error-c3320"></a>Ошибка компилятора C3320

"тип": имя типа не может совпадать со свойством name модуля

Экспортированный определяемый пользователем тип (UDT), который может быть структурой, классом, перечислением или объединением, не может иметь то же имя, что и параметр, передаваемый свойству Name атрибута [module](../../windows/module-cpp.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3320:

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```
