---
title: Глобальные константы в C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00d033c1c4fc8fc3e534c8e4ee0c3d7867b83834
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103177"
---
# <a name="global-constants-in-c"></a>Глобальные константы в C++

Глобальные константы в C++ имеют статическую связь. Это отличается от C. Если вы попытаетесь использовать глобальный константы в C++ в нескольких файлах отобразится неразрешенная внешняя ошибка. Компилятор оптимизирует глобальные константы, не оставляя места для переменной.

Один из способов устранения этой ошибки является включение инициализации констант в файле заголовка и ввести этот заголовок в CPP-файлов при необходимости, как если бы это был прототип функции. Другой вариант — сделать переменную неконстантное и использовать ссылку на константу, оценивая ее.

Следующий пример приводит к возникновению ошибки C2019:

```
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

Затем:

```
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>См. также

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)