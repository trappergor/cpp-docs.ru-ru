---
title: "vsscanf_s, vswscanf_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vswscanf_s"
  - "vsscanf_s"
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
  - "vsscanf_s"
  - "vswscanf_s"
  - "_vstscanf_s"
dev_langs: 
  - "C++"
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vsscanf_s, vswscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из строки.  В этих версиях [vsscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int vsscanf_s(  
   const char *buffer,  
   const char *format,  
   va_list argptr  
);   
int vswscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);   
```  
  
#### Параметры  
 `buffer`  
 Сохраненные данные  
  
 `format`  
 Строка управления форматом.  Для получения дополнительной информации см. [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
 `arglist`  
 Список аргументов переменных.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые успешно преобразуются и назначаются; возвращаемое значение не включает поля, которые были считаны, но не присваиваются.  Возвращаемое значение 0 указывает, что поля не были присвоены.  Возвращаемое значение равно `EOF` в случае ошибки или если конец строки достигнут до первого преобразования.  
  
 Если параметр `buffer` или `format` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают \-1 и устанавливают для `errno` значение `EINVAL`.  
  
 Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `vsscanf_s` считывает данные из `buffer` в расположения, заданные каждым аргументом в списке аргументов `arglist`.  Аргументы в списке аргументов задают указатели на переменные, имеющие тип, который соответствует спецификатору типа в `format`.  В отличие от менее безопасной версии `vsscanf`, параметр размера буфера является обязательным при использовании символов поля типа `c`, `C`, `s`, `S` или наборов строковых элементов управления, заключенных в `[]`.  Размер буфера в символах следует указывать в качестве дополнительного параметра сразу после каждого параметра буфера, для которого он требуется.  
  
 Размер буфера включает конечное значение NULL.  Поле спецификации ширины может использоваться, чтобы гарантировать, что считываемый токен поместится в буфер.  Если не используется поле спецификации ширины, и токен считанный слишком велик чтобы влезть в буфер, ничего не записывается в этот буфер.  
  
 Дополнительные сведения см. в разделах [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) и [Символы поля типа scanf](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Параметр размера — типа `unsigned`, а не `size_t`.  
  
 Аргумент `format` управляет интерпретацией полей ввода и имеет те же форму и функциональные возможности, что и аргумент `format` для функции `scanf_s`.  Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 `vswscanf_s` — это двухбайтовая версия `vsscanf_s`; аргументы для `vswscanf_s` представляют собой двухбайтовые строки.  `vsscanf_s` не обрабатывает многобайтовые шестнадцатеричные символы.  `vswscanf_s` не обрабатывает полноширинные шестнадцатеричные символы юникода или символы "зоны совместимости".  В противном случае поведение `vswscanf_s` и `vsscanf_s` идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vstscanf_s`|`vsscanf_s`|`vsscanf_s`|`vswscanf_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`vsscanf_s`|\<stdio.h\>|  
|`vswscanf_s`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_vsscanf_s.c  
// compile with: /W3  
// This program uses vsscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vsscanf_s(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf_s(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));  
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));  
    call_vsscanf_s(tokenstring, "%d", &i);  
    call_vsscanf_s(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
  **Строка    \= 15**  
**Знак \= 1**  
**Целое число:  \= 15**  
**Real:     \= 15.000000**   
## Эквивалент в .NET Framework  
 См. методы `Parse`, такие как [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md)