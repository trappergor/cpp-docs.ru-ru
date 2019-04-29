---
title: Предупреждение компилятора (уровни 1 и 4) C4112
ms.date: 11/04/2016
f1_keywords:
- C4112
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
ms.openlocfilehash: 3678d0ce5d9eb9568f0272da4173e72502b0557f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280338"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Предупреждение компилятора (уровни 1 и 4) C4112

\#строке требуется целое число от 1 до числа

Директива [#Line](../../preprocessor/hash-line-directive-c-cpp.md) указывает целочисленный параметр, который не входит в допустимый диапазон.

Если указанный параметр имеет значение меньше 1, счетчик строк сбрасывается до 1. Если указанный параметр больше, чем *номер*, представляющий определенный компилятором предел, то счетчик строк не изменяется. Это предупреждение уровня 1 в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение уровня 4 в расширениях Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Следующий пример приводит к возникновению ошибки C4112:

```
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```