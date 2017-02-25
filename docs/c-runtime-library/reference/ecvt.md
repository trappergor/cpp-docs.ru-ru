---
title: "ecvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ecvt - функция"
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _ecvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует значение типа `double` в строку.  Существует более безопасная версия этой функции; см. раздел [\_ecvt\_s](../Topic/_ecvt_s.md).  
  
## Синтаксис  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### Параметры  
 `value`  
 Число, которое нужно преобразовать.  
  
 `count`  
 Количество сохраненных цифр.  
  
 `dec`  
 Сохраненная позиция десятичной запятой.  
  
 `sign`  
 Знак преобразованного числа.  
  
## Возвращаемое значение  
 `_ecvt` возвращает указатель на строку цифр; NULL в случае возникновения ошибки.  
  
## Заметки  
 Функция `_ecvt` преобразует число с плавающей запятой в строку символов.  Параметр `value` число с плавающей запятой, которое требуется преобразовать.  Эта функция сохраняет до `count` цифр `value` в виде строки и добавляет нулевой символ \('\\0'\).  Если число цифр в `value` превышает `count`, разряды нижних порядков округляются.  Если количество цифр меньше, чем `count`, строка дополняется нулями.  
  
 Общее число цифр, возвращаемое `_ecvt` не превысит `_CVTBUFSIZE`.  
  
 Только цифры хранятся в строке.  Положение десятичной запятой и знак `value` можно получить из `dec` и `sign` после вызова.  Параметр `dec` указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки.  Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры.  Параметр `sign` указывает на целое число, указывающее знак преобразованного числа.  Если целочисленное значение 0, то число положительно.  В противном случае число будет отрицательным.  
  
 Различие между `_ecvt` и `_fcvt` в интерпретации параметра `count`.  `_ecvt` интерпретирует `count` как общее число цифр в выходной строке, тогда как `_fcvt` интерпретирует `count` как количество цифр после десятичной запятой.  
  
 `_ecvt` и `_fcvt` используют один статически выделенный буфер для преобразования.  Каждый вызов одной из этих процедур уничтожает результат предыдущего вызова.  
  
 Эта функция проверяет свои параметры.  Если параметр `dec` или `sign` имеет значение NULL или `count` равен 0, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, `errno` устанавливается в значение `EINVAL`, и возвращается NULL.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`_ecvt`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
  **source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0**   
## Эквивалент в .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)