---
title: Предупреждение компилятора (уровень 1) C4627 | Документация Майкрософт
ms.custom: ''
ms.date: 09/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fef8d0ab55205d2377fc52049c40a1c50151b93e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024181"
---
# <a name="compiler-warning-level-1-c4627"></a>Предупреждение компилятора (уровень 1) C4627

> "*header_file*": пропущен при поиске использования предкомпилированного заголовка

Если у текущего файла исходного кода [/Yu \(использование предкомпилированного файла заголовка)](../../build/reference/yu-use-precompiled-header-file.md) параметр, то компилятор игнорирует все, что в файле, прежде чем предкомпилированный заголовок включен. Предупреждение **C4627** создается в Visual Studio 2015 и более ранних версий, если *header_file* включен перед предкомпилированного файла заголовка, и если предкомпилированный заголовок не следует включать *header_file*.

## <a name="example"></a>Пример

В этом примере демонстрируется, как может произойти ошибка и показаны способы ее устранения:

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>См. также

[Создание предварительно скомпилированных файлов заголовков](../../build/reference/creating-precompiled-header-files.md)
