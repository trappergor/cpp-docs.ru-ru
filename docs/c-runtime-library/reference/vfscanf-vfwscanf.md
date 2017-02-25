---
title: "vfscanf, vfwscanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vfwscanf"
  - "vfscanf"
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
  - "vfwscanf"
  - "_vftscanf"
  - "vfscanf"
dev_langs: 
  - "C++"
ms.assetid: c06450ef-03f1-4d24-a8ac-d2dd98847918
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vfscanf, vfwscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из потока.  Существуют более безопасные версии этих функций; см. раздел [vfscanf\_s, vfwscanf\_s](../../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md).  
  
## Синтаксис  
  
```  
int vfscanf(   
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int vfwscanf(   
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `format`  
 Строка управления форматом.  
  
 `arglist`  
 Список аргументов переменных.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые успешно преобразуются и назначаются; возвращаемое значение не включает поля, которые считываются, но не присваиваются.  Возвращаемое значение 0 указывает, что поля не были присвоены.  При возникновении ошибки или достижении конца файлового потока перед первым преобразованием возвращается значение `EOF` для `vfscanf` и `vfwscanf`.  
  
 Эти функции проверяют свои параметры.  Если `stream` или `format` является пустым указателем, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
## Заметки  
 Функция `vfscanf` считывает данные из текущей позиции в `stream` в расположения, заданные списком аргументов `arglist`.  Каждый аргумент в списке должен быть указателем на переменную, которая имеет тип, который соответствует спецификатору типа в `format`.  `format` управляет интерпретация полей ввода и имеет те же форму и функциональные возможности, что и аргумент `format` для `scanf`. см. [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), там описание `format`.  
  
 `vfwscanf` — двухбайтовая версия `vfscanf`; аргумент формата для `vfwscanf` \- строка двухбайтовых знаков.  Поведение этих функций идентично, если поток открыт в режиме ANSI\-совместимости.  `vfscanf` не поддерживает входные данные из потока ЮНИКОДА.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_vftscanf`|`vfscanf`|`vfscanf`|`vfwscanf`|  
  
 Для получения дополнительной информации см. [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`vfscanf`|\<stdio.h\>|  
|`vfwscanf`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_vfscanf.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses vfscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
FILE *stream;  
  
int call_vfscanf(FILE * istream, char * format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vfscanf(istream, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main(void)  
{  
    long l;  
    float fp;  
    char s[81];  
    char c;  
  
    if (fopen_s(&stream, "vfscanf.out", "w+") != 0)  
    {  
        printf("The file vfscanf.out was not opened\n");  
    }  
    else  
    {  
        fprintf(stream, "%s %ld %f%c", "a-string",  
            65000, 3.14159, 'x');  
        // Security caution!  
        // Beware loading data from a file without confirming its size,  
        // as it may lead to a buffer overrun situation.  
  
        // Set pointer to beginning of file:  
        fseek(stream, 0L, SEEK_SET);  
  
        // Read data back from file:  
        call_vfscanf(stream, "%s %ld %f%c", s, &l, &fp, &c);  
  
        // Output data read:   
        printf("%s\n", s);  
        printf("%ld\n", l);  
        printf("%f\n", fp);  
        printf("%c\n", c);  
  
        fclose(stream);  
    }  
}  
  
```  
  
  **a\-string**  
**65000**  
**3.141590**  
**x**   
## Эквивалент в .NET Framework  
 [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx). См. также методы `Parse`, такие как [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [vfscanf\_s, vfwscanf\_s](../../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)