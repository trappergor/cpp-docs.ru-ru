---
title: Глобальные константы в C++
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 2f0621f52fe445f8f2058ef902824ddc1f5e2bb5
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856108"
---
# <a name="global-constants-in-c"></a>Глобальные константы в C++

Глобальные константы в C++ имеют статическую связь. Это отличается от C. Если вы попытаетесь использовать глобальный константы в C++ в нескольких файлах отобразится неразрешенная внешняя ошибка. Компилятор оптимизирует глобальные константы, не оставляя места для переменной.

Один из способов устранения этой ошибки является включение инициализации констант в файле заголовка и ввести этот заголовок в CPP-файлов при необходимости, как если бы это был прототип функции. Другой вариант — сделать переменную неконстантное и использовать ссылку на константу, оценивая ее.

Следующий пример приводит к возникновению ошибки C2019:

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

Затем:

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>См. также

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)