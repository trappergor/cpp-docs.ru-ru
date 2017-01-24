---
title: "_mktemp, _wmktemp | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmktemp"
  - "_mktemp"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tmktemp"
  - "wmktemp"
  - "tmktemp"
  - "_wmktemp"
  - "_mktemp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktemp - функция"
  - "_tmktemp - функция"
  - "_wmktemp - функция"
  - "файлы [C++], временные"
  - "mktemp - функция"
  - "временные файлы [C++]"
  - "tmktemp - функция"
  - "wmktemp - функция"
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mktemp, _wmktemp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает уникальное имя файла.  Существуют более безопасные версии этих функций; см. раздел [\_mktemp\_s, \_wmktemp\_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## Синтаксис  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### Параметры  
 `template`  
 Шаблон имени файла.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на измененный шаблон.  Функция возвращает `NULL`, если `template` неправильно сформирован или больше нельзя создать уникальные имена из заданного шаблона.  
  
## Заметки  
 Функция `_mktemp` создает уникальное имя файла, изменив аргумент `template`.  `_mktemp` автоматически обрабатывает аргументы многобайтовые строки аргументов как подходящие, распознавая многобайтовые последовательности символов в соответствии с многобайтовой кодовой странице в настоящий момент используется системой среды выполнения.  `_wmktemp` — это двухбайтовая версия функции `_mktemp`; аргумент и возвращаемое значение `_wmktemp` являются строками двухбайтовых символов.  В остальных случаях поведение `_wmktemp` и `_mktemp` идентично, за исключением того, что `_wmktemp` не обрабатывает многобайтовые строки.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 Аргумент `template` имеет форму `base`XXXXXX, где `base` это часть нового имени файла, и каждый X прототип для символа указанного в `_mktemp`.  Каждый символ заполнителя в `template` должен быть прописным X.  `_mktemp` сохраняет `base` и заменяет первый замыкающий X на символ алфавита.  `_mktemp` заменяет следующие конечные X пятизначным значением; это значение — уникальное число, определяющее вызывающий процесс или, в многопоточных программах, вызывающий поток.  
  
 Каждый успешный вызов `_mktemp` изменяет `template`.  В каждом последующем вызове из одного и того же процесса или потока с тем же аргументом `template`, проверка `_mktemp` имен файлов, которые соответствуют, возвращаемых в предыдущих вызовах `_mktemp`.  Если не существует файла с данным именем, `_mktemp` возвращает это имя.  Если файлы существуют для всех ранее возвращенных имен, `_mktemp` создает новое имя, заменив алфавитный символ, используемый ранее, следующей доступной буквой нижнего регистра, в порядке от "a" до "z".  Например, если: `base` это:  
  
```  
fn  
```  
  
 и пятизначное значение, возвращенное `_mktemp` — 12345, первое возвращенное имя:  
  
```  
fna12345  
```  
  
 Если это имя используется для создания файла FNA12345 и этот файл все еще существует, то следующее имя, возвращенное при вызове из этого же процесса или потока с тем же `base` для `template`:  
  
```  
fnb12345  
```  
  
 Если FNA12345 не существует, следующее возвращенное имя снова будет:  
  
```  
fna12345  
```  
  
 `_mktemp` может создать максимум 26 уникальных имен файлов для всех заданных сочетаний значений base и template.  Поэтому FNZ12345 последнее уникальное имя файла, которое `_mktemp` может создать для значений `base` и `template`, используемых в данном примере.  
  
 В случае сбоя, устанавливается `errno`.  Если `template` имеет недопустимый формат \(например, менее 6 X\), то `errno` установлено в `EINVAL`.  Если `_mktemp` не удалось создать уникальное имя, поскольку все 26 возможных имен файла уже существуют, `_mktemp` задает шаблон равным пустой строке и возвращает `EEXIST`.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mktemp`|\<io.h\>|  
|`_wmktemp`|\<io.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
  **Unique filename is fna03912**  
**Unique filename is fnb03912**  
**Unique filename is fnc03912**  
**Unique filename is fnd03912**  
**Unique filename is fne03912**  
**Unique filename is fnf03912**  
**Unique filename is fng03912**  
**Unique filename is fnh03912**  
**Unique filename is fni03912**  
**Unique filename is fnj03912**  
**Unique filename is fnk03912**  
**Unique filename is fnl03912**  
**Unique filename is fnm03912**  
**Unique filename is fnn03912**  
**Unique filename is fno03912**  
**Unique filename is fnp03912**  
**Unique filename is fnq03912**  
**Unique filename is fnr03912**  
**Unique filename is fns03912**  
**Unique filename is fnt03912**  
**Unique filename is fnu03912**  
**Unique filename is fnv03912**  
**Unique filename is fnw03912**  
**Unique filename is fnx03912**  
**Unique filename is fny03912**  
**Unique filename is fnz03912**  
**Problem creating the template.**  
**Out of unique filenames.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../Topic/_getpid.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)