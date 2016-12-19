---
title: "sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l | Microsoft Docs"
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
  - "_swprintf_s_l"
  - "_sprintf_s_l"
  - "swprintf_s"
  - "sprintf_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "swprintf_s"
  - "sprintf_s"
  - "stdio/sprintf_s"
  - "stdio/swprintf_s"
  - "stdio/_sprintf_s_l"
  - "stdio/_swprintf_s_l"
  - "_sprintf_s_l"
  - "_swprintf_s_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "stprintf_s - функция"
  - "stprintf_s_l - функция"
  - "swprintf_s_l - функция"
  - "sprintf_s - функция"
  - "swprintf_s - функция"
  - "_swprintf_s_l - функция"
  - "sprintf_s_l - функция"
  - "_stprintf_s_l - функция"
  - "_stprintf_s - функция"
  - "_sprintf_s_l - функция"
  - "форматированный текст [C++]"
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Запись форматированных данных в строку. Здесь представлены версии [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int sprintf_s(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   ...   
);  
int _sprintf_s_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale,  
   ...   
);  
int swprintf_s(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   ...  
);  
int _swprintf_s_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale,  
   ...  
);  
template <size_t size>  
int sprintf_s(  
   char (&buffer)[size],  
   const char *format,  
   ...   
); // C++ only  
template <size_t size>  
int swprintf_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   ...  
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения выходных данных  
  
 `sizeOfBuffer`  
 Наибольшее число символов для хранения.  
  
 `format`  
 Строка управления форматом  
  
 `...`  
 Необязательные аргументы для форматирования  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## Возвращаемое значение  
 Записанное число символов или –1 в случае возникновения ошибки. Если `buffer` или `format` является пустым указателем, `sprintf_s` и `swprintf_s` возвращают значение \-1 и задают `errno` равным `EINVAL`.  
  
 `sprintf_s` возвращает число байтов, сохраненных в `buffer` без учета завершающего символа null.`swprintf_s` возвращает число расширенных символов, сохраненных в `buffer`, без учета завершающего расширенного символа null.  
  
## Заметки  
 Функция `sprintf_s` форматирует и сохраняет набор символов и значений в `buffer`. Каждый `argument` \(если он есть\) преобразуется и выводится согласно соответствующей спецификацией формата в `format`. Формат состоит из обычных символов и имеет те же форму и функциональные возможности, что и аргумент `format` для [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). После последнего написанного символа добавляется символ null. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 Основное различие между `sprintf_s` и `sprintf` заключается в том, что `sprintf_s` проверяет строку форматирования на наличие допустимых символов форматирования, тогда как `sprintf` только проверяет, является ли строка формата или буфер указателем `NULL`. Если проверка завершается с ошибкой, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает \-1 и устанавливает `errno` в значение `EINVAL`.  
  
 Другое основное различие между `sprintf_s` и `sprintf` в том, что `sprintf_s` принимает параметр длины, определяющий размер буфера вывода в символах. Если буфер слишком мал для форматированного текста, включая завершающий символ null, то ему присваивается пустая строка путем размещения символа null в `buffer``[0]` и вызывается обработчик недопустимого параметра. В отличие от `_snprintf`, `sprintf_s` гарантирует, что буфер будет завершен символом null \(если размер буфера не равен нулю\).  
  
 `swprintf_s` — это двухбайтовая версия `sprintf_s`; аргументы указателя для `swprintf_s` представляют собой двухбайтовые строки. Обнаружение ошибок кодирования в `swprintf_s` может отличаться от обнаружения ошибок в `sprintf_s`. Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 В C\+\+ использование этих функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера, что исключает необходимость указания аргумента с размером буфера, а также они могут автоматически заменять более старые незащищенные функции их новыми безопасными аналогами. Для получения дополнительной информации см. [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Существуют версии `sprintf_s`, которые обеспечивают дополнительный контроль над происходящим, если буфер слишком мал. Дополнительные сведения см. в разделе [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_stprintf_s`|`sprintf_s`|`sprintf_s`|`swprintf_s`|  
|`_stprintf_s_l`|`_sprintf_s_l`|`_sprintf_s_l`|`_swprintf_s_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`sprintf_s`, `_sprintf_s_l`|C: \<stdio.h\><br /><br /> C\+\+: \<cstdio\> или \<stdio.h\>|  
|`swprintf_s`, `_swprintf_s_l`|C: \<stdio.h\> или \<wchar.h\><br /><br /> C\+\+: \<cstdio\>, \<cwchar\>, \<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_sprintf_s.c  
// This program uses sprintf_s to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );  
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );  
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );  
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );  
  
   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
}  
```  
  
```Output  
Выходные данные: строка: computer символ: l целое число: 35 действительное число: 1,732053 число символов = 79  
```  
  
## Пример  
  
```  
// crt_swprintf_s.c  
// wide character example  
// also demonstrates swprintf_s returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf_s fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
```Output  
запись 11 символов запись -1 символ  
```  
  
## Эквивалент в .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)