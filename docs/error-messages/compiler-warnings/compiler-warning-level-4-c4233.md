---
title: Предупреждение компилятора (уровень 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 361e00b7361aab51ea077d7e248503f3654e5e58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401063"
---
# <a name="compiler-warning-level-4-c4233"></a>Предупреждение компилятора (уровень 4) C4233

> использовано нестандартное расширение: "*ключевое слово*" поддерживается только в C++, C не ключевое слово

Исходный код компилируется как C, а не C++, и вы использовали ключевое слово, которое является допустимым только в C++. Компилятор компилирует исходный файл как C, если имеет расширение исходного файла c или вы используете [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4233 в предупреждение уровня 4, добавьте следующую строку в файле исходного кода:

```cpp
#pragma warning(4:4233)
```
