---
title: "Функции to | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "To"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "регистр знаков, преобразование"
  - "знаки, преобразование"
  - "строчные буквы, преобразование строк"
  - "преобразование строк, регистр знаков"
  - "преобразование строк, в другие знаки"
  - "к функциям"
  - "прописные буквы, преобразование строк"
ms.assetid: f636a4c6-8c9f-4be2-baac-064f9dbae300
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Функции to
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждая из функций **to** и её соответствующий макрос, если таковые имеются, преобразуют символ в другой символ.  
  
|||  
|-|-|  
|[\_\_toascii](../c-runtime-library/reference/toascii-toascii.md)|[toupper, \_toupper, towupper](../Topic/toupper,%20_toupper,%20towupper,%20_toupper_l,%20_towupper_l.md)|  
|[tolower, \_tolower, towlower](../Topic/tolower,%20_tolower,%20towlower,%20_tolower_l,%20_towlower_l.md)||  
  
## Заметки  
 Функции **to** и макросы преобразования выглядят следующим образом.  
  
|Подпрограмма|Макрос|Описание|  
|------------------|------------|--------------|  
|`__toascii`|`__toascii`|Преобразует `c` в ASCII символ|  
|`tolower`|`tolower`|Преобразует `c` в нижний регистр при необходимости|  
|`_tolower`|`_tolower`|Преобразует `c` в нижний регистр|  
|`towlower`|Нет|Преобразует `c` в соответствующий расширенный символ нижнего регистра|  
|`toupper`|`toupper`|Преобразует `c` в верхний регистр при необходимости|  
|`_toupper`|`_toupper`|Преобразует `c` в верхний регистр|  
|`towupper`|Нет|Преобразует c в соответствующий расширенный символ верхнего регистра|  
  
 Чтобы использовать функциональные версии процедур **to**, которые также определены как макросы, либо удалите определения макросов с помощью директив `#undef`, либо не включайте CTYPE.H.  Если используется параметр компилятора \/Za, то компилятор использует версию функции `toupper` или `tolower`.  Объявления функций `toupper` и `tolower` находятся в STDLIB.H.  
  
 Процедура `__toascii` устанавливает все, кроме младших 7 бит `c`, в 0, поэтому преобразованное значение представляет символ в кодировке ASCII.  Если `c` уже представляет символ ASCII, `c` не изменяется.  
  
 Процедуры `tolower` и `toupper`:  
  
-   Зависят от категории `LC_CTYPE` текущего языкового стандарта \(`tolower` вызывает `isupper` и `toupper` вызывает `islower`\).  
  
-   Преобразует `c`, если `c` представляет конвертируемую букву соответствующего регистра текущего языкового стандарта и если существует обратный регистр для данного языкового стандарта.  В противном случае `c` не изменяется.  
  
 Процедуры `_tolower` и `_toupper`:  
  
-   Не зависят от языкового стандарта, намного быстрые версии `tolower` и **toupper.**  
  
-   Могут использоваться только когда **isascii\(**`c`**\)** и либо **isupper\(**`c`**\)**, либо **islower\(**`c`**\)** соответственно, отличны от нуля.  
  
-   Имеют неопределенные результаты, если `c` не является буквой ASCII соответствующего регистра для преобразования.  
  
 Функции `towlower` и `towupper` возвращают преобразованную копию `c` только в том случае, если выполняются оба приведенных ниже условия.  В противном случае `c` не изменяется.  
  
-   `c` является расширенным символом соответствующего регистра \(то есть, для которого `iswupper` или **iswlower,** соответственно, не равны нулю\).  
  
-   Существует соответствующий расширенный символ нужного регистра \(то есть, для которого `iswlower` или **iswupper,** соответственно, не равны нулю\).  
  
## Пример  
  
```  
// crt_toupper.c  
/* This program uses toupper and tolower to  
 * analyze all characters between 0x0 and 0x7F. It also  
 * applies _toupper and _tolower to any code in this  
 * range for which these functions make sense.  
 */  
  
#include <ctype.h>  
#include <string.h>  
  
char msg[] = "Some of THESE letters are Capitals.";  
char *p;  
  
int main( void )  
{  
   printf( "%s\n", msg );  
  
   /* Reverse case of message. */  
   for( p = msg; p < msg + strlen( msg ); p++ )  
   {  
      if( islower( *p ) )  
         putchar( _toupper( *p ) );  
      else if( isupper( *p ) )  
         putchar( _tolower( *p ) );  
      else  
         putchar( *p );  
   }  
}  
```  
  
  **Some of THESE letters are Capitals.**  
**sOME OF these LETTERS ARE cAPITALS.**   
## См. также  
 [Преобразование данных](../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../c-runtime-library/locale.md)   
 [Процедуры is, isw](../c-runtime-library/is-isw-routines.md)