---
title: "_gcvt_s | Microsoft Docs"
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
  - "_gcvt_s"
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
  - "_gcvt_s"
  - "gcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt_s - функция"
  - "преобразования, значения с плавающей запятой к строкам"
  - "CVTBUFSIZE"
  - "функции с плавающей запятой, преобразование числа в строку"
  - "gcvt_s - функция"
  - "числа, преобразование в строки"
  - "строки [C++], преобразование из чисел с плавающей запятой"
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _gcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразует значение с плавающей запятой в строку.  Это версия [\_gcvt](../../c-runtime-library/reference/gcvt.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `buffer`  
 Буфер для хранения результата преобразования.  
  
 \[входящий\] `sizeInBytes`  
 Размер буфера.  
  
 \[входящий\] `value`  
 Преобразуемое значение.  
  
 \[входящий\] `digits`  
 Количество хранящихся значащих цифр.  
  
## Возвращаемое значение  
 Ноль, если успешно.  В случае возникновения ошибки из\-за недопустимого параметра \(см. следующую таблицу для недопустимых значений\) обработчик недопустимого параметра вызывается как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнение разрешено, возвращается код ошибки.  Коды ошибок определенны в Errno.h.  Список этих ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
### Условия возникновения ошибки  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Return|Значение в `buffer`|  
|--------------|-------------------|-------------|--------------|------------|-------------------------|  
|`NULL`|any|any|any|`EINVAL`|Без изменений.|  
|Не `NULL` \(указывает на допустимый адрес памяти\)|нуль|any|any|`EINVAL`|Без изменений.|  
|Не `NULL` \(указывает на допустимый адрес памяти\)|any|any|\>\= `sizeInBytes`|`EINVAL`|Без изменений.|  
  
 **Проблемы безопасности**  
  
 `_gcvt_s` может создать ошибку нарушения прав доступа, если `buffer` не указывает на допустимый адрес памяти и не `NULL`.  
  
## Заметки  
 Функция `_gcvt_s` преобразует `value` с плавающей запятой на символьную строку \(которая включает десятичную запятую и возможный байт знака\) и запоминает строку в `buffer`.  `buffer` должен быть достаточным для размещения преобразованного значения и конечного нулевого символа, который добавляется автоматически.  Буфер длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой.  Если используется размер буфера `digits` \+ 1, то функция не перезапишет конец буфера, поэтому убедитесь, что предоставлен достаточный буфер для данной операции.  `_gcvt_s` пытается создать числа `digits` в десятичном формате.  Если не удается, он создает числа `digits` в степенном формате.  Замыкающие нули можно отключить при преобразовании.  
  
 В C\+\+ использование этой функции упрощено шаблонной перегрузкой; перегрузка может определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочная версия этой функции сначала заполняет буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_gcvt_s`|\<stdlib.h\>|\<error.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
  **Преобразованное значение: 1,2**   
## Эквивалент в .NET Framework  
 <xref:System.Convert.ToString%2A>  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, \_atof\_l, \_wtof, \_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../Topic/_ecvt_s.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)