---
title: Предупреждение компилятора (уровень 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 91e836c9bb606d7759206788d1e3abd63b293fa8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175315"
---
# <a name="compiler-warning-level-1-c4716"></a>Предупреждение компилятора (уровень 1) C4716

Функция "функция" должна возвращать значение

Данная функция не вернула значение.

Только функции с возвращаемым типом void могут использовать возвращаемую команду без сопутствующего возвращаемого значения.

При вызове этой функции будет возвращено неопределенное значение.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma предупреждение](../../preprocessor/warning.md).

Следующий пример приводит к возникновению ошибки C4716:

```cpp
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```
