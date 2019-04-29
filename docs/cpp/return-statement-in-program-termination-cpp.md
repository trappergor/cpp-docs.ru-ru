---
title: Оператор return при прерывании программы (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267617"
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