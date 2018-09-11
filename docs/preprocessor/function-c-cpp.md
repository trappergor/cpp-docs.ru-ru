---
title: функции (C/C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs:
- C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76ab5b2911d349c62ff18967e7a660cdc3589ddd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539476"
---
# <a name="function-cc"></a>function (C/C++)
Указывает, что для функций из списка аргументов директивы #pragma будут создаваться вызовы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>Примечания  

При использовании `intrinsic` pragma (или /Oi), чтобы сообщить компилятору требуется создавать встроенные функции (встроенные функции создаются как встроенный код, а не как вызовы функций), можно использовать **функция** директиву pragma, чтобы явно принудительно задать вызов функции. После появления директивы #pragma она действует на первое определение функции, содержащее указанную встроенную функцию. Ее действие продолжается до конца исходного файла, или на внешний вид `intrinsic` pragma, указав ту же встроенную функцию. **Функция** директива pragma может использоваться только за пределами функции — на глобальном уровне.  
  
Списки функций, имеющих встроенные формы, см. в разделе [#pragma intrinsic](../preprocessor/intrinsic.md).  
  
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

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)