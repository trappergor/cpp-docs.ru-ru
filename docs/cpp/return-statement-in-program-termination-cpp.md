---
title: Оператор return при прерывании программы (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613049"
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