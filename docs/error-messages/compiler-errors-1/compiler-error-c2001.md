---
title: Ошибка компилятора C2001 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71048a706678e4d9e6906972ebf148748927e829
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088246"
---
# <a name="compiler-error-c2001"></a>Ошибка компилятора C2001

NewLine в константе

Строковая константа не может быть продолжено на следующую строку, пока вы не выполните следующее:

- Окончание первую строку начинают с обратной косой черты.

- Закройте строками на первую строку начинают с двойной кавычки и откройте строки на следующую строку с другой двойные кавычки.

Завершение первую строку начинают с \n недостаточно.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2001:

```
// C2001.cpp
// C2001 expected
#include <stdio.h>

int main()
{
    printf_s("Hello,
             world");
    printf_s("Hello,\n
             world");
}
```

## <a name="example"></a>Пример

Пробелы в начале следующей строки после символа продолжения строки включаются в строковой константы. Ни один из приведенных выше примеров внедрения символа новой строки в строковой константы. Вы можете внедрить символ новой строки, как показано ниже:

```
// C2001b.cpp
#include <stdio.h>

int main()
{
    printf_s("Hello,\n\
             world");

    printf_s("Hello,\
             \nworld");

    printf_s("Hello,\n"
             "world");

    printf_s("Hello,"
             "\nworld");

    printf_s("Hello,"
             " world");

    printf_s("Hello,\
             world");
}
```