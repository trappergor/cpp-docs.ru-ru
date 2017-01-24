---
title: "_fcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fcvt_s"
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
  - "fcvt_s"
  - "_fcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fcvt_s - функция"
  - "преобразование чисел с плавающей запятой, к строкам"
  - "fcvt_s - функция"
  - "функции с плавающей запятой, преобразование числа в строку"
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует число с плавающей точкой в строку.  Это версия [\_fcvt](../Topic/_fcvt.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `buffer`  
 Предоставленный буфер, в который помещается результат преобразования.  
  
 \[входящий\] `sizeInBytes`  
 Размер буфера в байтах.  
  
 \[входящий\] `value`  
 Число, которое нужно преобразовать.  
  
 \[входящий\] `count`  
 Количество цифр после десятичного знака.  
  
 \[исходящий\] `dec`  
 Указатель на сохраненную позицию десятичной точкой.  
  
 \[исходящий\] `sign`  
 Указатель на сохраненный индикатор знака.  
  
## Возвращаемое значение  
 Ноль, если успешно.  Возвращаемое значение — код ошибки в случае сбоя.  Коды ошибок определенны в Errno.h.  Список этих ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 В случае недопустимого параметра, как перечислено в таблице ниже, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, функция устанавливает `errno` в `EINVAL` и возвращает `EINVAL`.  
  
### Условия возникновения ошибки  
  
|`buffer`|`sizeInBytes`|value|count|dec|sign|Return|Значение в `buffer`|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-------------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Без изменений.|  
|Не `NULL` \(указывает на допустимый адрес памяти\)|\<\=0|any|any|any|any|`EINVAL`|Без изменений.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Без изменений.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Без изменений.|  
  
 **Проблемы безопасности**  
  
 `_fcvt_s` может создать ошибку нарушения прав доступа, если `buffer` не указывает на допустимый адрес памяти и не `NULL`.  
  
## Заметки  
 Функция `_fcvt_s` преобразует число с плавающей точкой в строку, завершенную нулевым символом.  Параметр `value` число с плавающей точкой, которое требуется преобразовать.  `_fcvt_s` хранит цифры `value` в виде строки и добавляет нуль\-символ \('\\0'\).  Параметр `count` определяет количество цифр, сохраняемых после десятичной запятой.  Избыточные цифры округляются до `count` знаков.  Если количество цифр точности меньше, чем `count`, строка дополняется нулями.  
  
 Только цифры хранятся в строке.  Положение десятичной точкой и знак `value` можно получить из `dec` и `sign` после вызова.  Параметр `dec` указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки.  Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры.  Параметр `sign` указывает на целое число, указывающее знак `value`.  Целое число имеет значение 0, если `value` положительное, и ненулевое число, если `value` отрицательное.  
  
 Буфер длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой.  
  
 Различие между `_ecvt_s` и `_fcvt_s` в интерпретации параметра `count`.  `_ecvt_s` интерпретирует `count` как общее число цифр в выходной строке, а `_fcvt_s` интерпретирует c`ount` как количество цифр после десятичной точкой.  
  
 В C\+\+ использование этой функции упрощено шаблонной перегрузкой; перегрузка может определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочная версия этой функции сначала заполняет буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|-------------|----------------------------|------------------------------|  
|`_fcvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** Все версии [Особенности библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Преобразованное значение: 120000**   
## Эквивалент в .NET Framework  
 <xref:System.Convert.ToString%2A>  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../Topic/_ecvt_s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)   
 [\_fcvt](../Topic/_fcvt.md)