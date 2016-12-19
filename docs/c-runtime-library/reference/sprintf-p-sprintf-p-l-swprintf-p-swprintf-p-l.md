---
title: "_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l | Microsoft Docs"
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
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_swprintf_p"
  - "_sprintf_p_l"
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
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_sprintf_p_l"
  - "_swprintf_p"
  - "sprintf_p"
  - "swprint_p_l"
  - "swprintf_p"
  - "swprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "sprintf_p_l - функция"
  - "swprintf_p - функция"
  - "swprintf_p_l - функция"
  - "_sprintf_p - функция"
  - "_sprintf_p_l - функция"
  - "_swprintf_p - функция"
  - "sprintf_p - функция"
  - "_stprintf_p - функция"
  - "stprintf_p - функция"
  - "_swprintf_p_l - функция"
  - "stprintf_p_l - функция"
  - "форматированный текст [C++]"
  - "_stprintf_p_l - функция"
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Записывает форматированные данные в строку с возможностью указать порядок, в котором параметры используются в строке формата.  
  
## Синтаксис  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] …   
);  
```  
  
#### Параметры  
 `buffer`  
 Место хранения выходных данных  
  
 `sizeOfBuffer`  
 Наибольшее число символов для хранения.  
  
 `format`  
 Строка управления форматом  
  
 `argument`  
 Необязательные аргументы  
  
 `locale`  
 Используемый языковой стандарт.  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md).  
  
## Возвращаемое значение  
 Записанное число символов или –1 в случае возникновения ошибки.  
  
## Заметки  
 Функция `_sprintf_p` форматирует и сохраняет набор символов и значений в `buffer`.  Каждый `argument` \(если он есть\) преобразуется и выводится согласно соответствующей спецификацией формата в `format`.  Формат состоит из обычных символов и имеет те же форму и функциональные возможности, что и аргумент `format` для `printf_p`.  После последнего написанного символа добавляется символ `NULL`.  Если копирование производится между перекрывающимися строками, поведение не определено.  Различие между `_sprintf_p` и `sprintf_s`, `_sprintf_p` заключается в поддержке позиционных параметров, которые позволяют определить порядок, в котором аргументы используются для форматирования строки.  Для получения дополнительной информации см. [Позиционные параметры printf\_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_swprintf_p` — это двухбайтовая версия `_sprintf_p`; аргументы указателя для `_swprintf_p` представляют собой двухбайтовые строки.  Обнаружение ошибок кодирования в `_swprintf_p` может отличаться от обнаружения ошибок в `_sprintf_p`.  `_swprintf_p` и `fwprintf_p` ведут себя идентично за исключением случаев, когда `_swprintf_p` записывает вывод в строку, а не в назначение типа `FILE`, и `_swprintf_p` требует, чтобы параметр `count`задавал максимальное число знаков для записи.  Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 `_sprintf_p` возвращает число байтов, сохраненных в `buffer` без учета завершающего символа `NULL`.  `_swprintf_p`возвращает число расширенных символов, сохраненных в `buffer`, без учета завершающего расширенного символа `NULL`.  Если `buffer` или `format` \- пустой указатель, или если строка формата содержит недопустимые символы форматирования, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции возвращают \-1 и устанавливают `errno` в значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h\>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
  **Выходные данные:**  
 **Строка: компьютер**  
 **Символ: l**  
 **Целое число: 35**  
 **Real: 1,732053**  
**число символов \= 79**   
## Пример  
  
```  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
  **Wrote 24 characters**  
**Wrote \-1 characters**   
## Эквивалент в .NET Framework  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)   
 [Функции vprintf](../../c-runtime-library/vprintf-functions.md)   
 [Позиционные параметры printf\_p](../../c-runtime-library/printf-p-positional-parameters.md)