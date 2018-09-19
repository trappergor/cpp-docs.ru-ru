---
title: Оператор Return при прерывании программы (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfcf65258767178c0f74f63ca6e938e1d940e3be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061140"
---
# <a name="return-statement-in-program-termination-c"></a>Оператор return при прерывании программы (C++)

Выдача **возвращают** инструкции от `main` является функционально эквивалентна вызову `exit` функции. Рассмотрим следующий пример.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit` И **возвращают** инструкции в предыдущем примере функционально идентичны. Однако C++ требует, что функции, которые имеют возвращать типы, отличные от **void** возвращают значение. **Возвращают** инструкция позволяет возвращать значение из `main`.

## <a name="see-also"></a>См. также

[Завершение программы](../cpp/program-termination.md)