---
title: прагма функции
ms.date: 08/29/2019
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: f99f3c878789a6c47fdb0d48e0a8690d65fa8062
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220136"
---
# <a name="function-pragma"></a>прагма функции

Указывает компилятору создавать вызовы функций, указанных в списке аргументов директивы pragma, вместо встраивания их.

## <a name="syntax"></a>Синтаксис

> **функция #pragma (** *функция1* [ **,** *функция2* ...] **)**

## <a name="remarks"></a>Примечания

Встроенные функции обычно создаются как встроенный код, а не как вызовы функций. Если используется встроенная [директива pragma](intrinsic.md) или параметр компилятора [/Oi](../build/reference/oi-generate-intrinsic-functions.md) , чтобы сообщить компилятору о необходимости создания встроенных функций, можно использовать **функцию** pragma для явного принудительного вызова функции. После того как прагма-директива обнаружена, она вступает в силу в первом определении функции, которая содержит указанную подставляемую функцию. Действие переходит к концу исходного файла или к внешнему виду `intrinsic` директивы pragma, указывающей ту же встроенную функцию. **Функцию** pragma можно использовать только за пределами функции на глобальном уровне.

Список функций, имеющих встроенные формы, см. в разделе [встроенная директива pragma](intrinsic.md).

## <a name="example"></a>Пример

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
