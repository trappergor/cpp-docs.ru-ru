---
title: Ошибка компилятора C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 03b54fe2373063c8c0f9905da93822928392998d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209027"
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