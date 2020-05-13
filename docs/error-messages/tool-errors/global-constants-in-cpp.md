---
title: Глобальные константы в C++
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: cabe5e92a496181d60536d7274eca388aba5c068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195478"
---
# <a name="global-constants-in-c"></a>Глобальные константы в C++

C++глобальные константы имеют статическую компоновку. Это отличается от C. Если вы попытаетесь использовать глобальную константу C++ в нескольких файлах, вы получаете неразрешенную внешнюю ошибку. Компилятор оптимизирует глобальные константы, не освобождая пространство, зарезервированное для переменной.

Одним из способов устранения этой ошибки является включение инициализации констант в файл заголовка и включение этого заголовка в CPP-файлы при необходимости, точно так же, как если бы он был прототипом функции. Другая возможность — сделать переменную неконстантной и использовать постоянную ссылку при оценке.

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

## <a name="see-also"></a>См. также раздел

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
