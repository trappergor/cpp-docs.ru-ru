---
title: "fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l | Microsoft Docs"
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
  - "fwscanf_s"
  - "_fscanf_s_l"
  - "_fwscanf_s_l"
  - "fscanf_s"
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
  - "_fwscanf_s_l"
  - "_fscanf_s_l"
  - "fscanf_s"
  - "_ftscanf_s_l"
  - "_ftscanf_s"
  - "fwscanf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fscanf_s_l - функция"
  - "_ftscanf_s - функция"
  - "_ftscanf_s_l - функция"
  - "_fwscanf_s_l - функция"
  - "данные [CRT], чтение из потоков"
  - "форматированные данные [C++], чтение из потоков"
  - "fscanf_s - функция"
  - "fscanf_s_l - функция"
  - "ftscanf_s - функция"
  - "ftscanf_s_l - функция"
  - "fwscanf_s - функция"
  - "fwscanf_s_l - функция"
  - "потоки [C++], чтение форматированных данных из"
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтение форматированных данных из потока.  В этих версиях [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int fscanf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...   
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `format`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые успешно преобразуются и назначаются; возвращаемое значение не включает поля, которые были считаны, но не присваиваются.  Возвращаемое значение 0 указывает, что поля не были присвоены.  При возникновении ошибки или если достигнут конец файлового потока перед первым преобразованием, возвращенное значение `EOF` для `fscanf_s` и `fwscanf_s`.  
  
 Эти функции проверяют свои параметры.  Если параметр `stream` или `format` указывает на файл или на NULL, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
## Заметки  
 Функция `fscanf_s` считывает данные из текущей позиции в `stream` в расположения, заданные в `argument` \(если он есть\).  Каждый `argument` должен быть указателем на переменную, которая имеет тип, который соответствует спецификатору типа в `format`.  `format` управляет интерпретацией полей ввода и имеет те же форму и функцию, как и аргумент `format` для `scanf_s`; см. раздел [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md) для описания `format`.  `fwscanf_s` \- версия `fscanf_s` для расширенных символов; аргумент формата в `fwscanf_s` строка расширенных символов.  Поведение этих функций идентично, если поток открыт в режиме ANSI\-совместимости.  `fscanf_s` сейчас не поддерживает входные данные из потока ЮНИКОДА.  
  
 Основное различие между более безопасными функциями \(которые имеют суффикс `_s`\) и другими версиями состоит в том, что более безопасные функции требуют размер в символах каждого поля типа `c`, `C`, `s`, `S` и `[`, который должен передаваться в качестве аргумента сразу же за переменной.  Дополнительные сведения см. в разделах [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) и [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Параметр размера — типа `unsigned`, а не `size_t`.  
  
 Версии этих функций, имеющие суффикс `_l`, идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ftscanf_s`|`fscanf_s`|`fscanf_s`|`fwscanf_s`|  
|`_ftscanf_s_l`|`_fscanf_s_l`|`_fscanf_s_l`|`_fwscanf_s_l`|  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fscanf_s`, `_fscanf_s_l`|\<stdio.h\>|  
|`fwscanf_s`, `_fwscanf_s_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_fscanf_s.c  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );  
   if( err )  
      printf_s( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf_s( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf_s( stream, "%s", s, _countof(s) );  
      fscanf_s( stream, "%ld", &l );  
  
      fscanf_s( stream, "%f", &fp );  
      fscanf_s( stream, "%c", &c, 1 );  
  
      // Output data read:  
      printf( "%s\n", s );  
      printf( "%ld\n", l );  
      printf( "%f\n", fp );  
      printf( "%c\n", c );  
  
      fclose( stream );  
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
 [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)