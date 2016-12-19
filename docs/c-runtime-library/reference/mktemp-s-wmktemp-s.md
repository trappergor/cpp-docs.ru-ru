---
title: "_mktemp_s, _wmktemp_s | Microsoft Docs"
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
  - "_mktemp_s"
  - "_wmktemp_s"
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
  - "wmktemp_s"
  - "mktemp_s"
  - "_mktemp_s"
  - "_wmktemp_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mktemp_s - функция"
  - "_tmktemp_s - функция"
  - "_wmktemp_s - функция"
  - "файлы [C++], временные"
  - "mktemp_s - функция"
  - "временные файлы [C++]"
  - "tmktemp_s - функция"
  - "wmktemp_s - функция"
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mktemp_s, _wmktemp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает уникальное имя файла.  Здесь представлены версии [\_mktemp, \_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### Параметры  
 `template`  
 Шаблон имени файла.  
  
 `sizeInChars`  
 Размер буфера в однобайтовых символах в `_mktemp_s`; в расширенных символах в `_wmktemp_s`, включая конечный символ null.  
  
## Возвращаемое значение  
 Обе эти функции возвращают ноль в случае успеха; код ошибки при сбое.  
  
### Условия возникновения ошибки  
  
|`template`|`sizeInChars`|**возвращаемое значение**|**новое значение в шаблоне**|  
|----------------|-------------------|-------------------------------|----------------------------------|  
|`NULL`|any|`EINVAL`|`NULL`|  
|Неверный формат \(см. раздел `Remarks` по правильному формату\)|any|`EINVAL`|пустая строка|  
|any|\<\= число символов X|`EINVAL`|пустая строка|  
  
 Если случается какая\-либо из выше перечисленных ошибок, то вызывается обработчик недопустимых параметров, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, `errno` устанавливается в значение `EINVAL`, и функции возвращают `EINVAL`.  
  
## Заметки  
 Функция `_mktemp_s` создает уникальное имя файла, изменив аргумент `template`, поэтому после вызова указатель `template` указывает на строку, содержащую новое имя файла.  `_mktemp_s` автоматически обрабатывает аргументы многобайтовые строки аргументов как подходящие, распознавая многобайтовые последовательности символов в соответствии с многобайтовой кодовой странице в настоящий момент используется системой среды выполнения.  `_wmktemp_s` — версия `_mktemp_s` для расширенных символов; аргумент для `_wmktemp_s` представляют строку расширенных символов.  В остальных случаях поведение `_wmktemp_s` и `_mktemp_s` идентично, за исключением того, что `_wmktemp_s` не обрабатывает многобайтовые строки.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 Аргумент `template` имеет форму `baseXXXXXX`, где `base` \- это часть нового имени файла, и каждый X \- заполнитель для символа, указанного в `_mktemp_s`.  Каждый символ заполнителя в `template` должен быть прописным X.  `_mktemp_s` сохраняет `base` и заменяет первый замыкающий X на символ алфавита.  `_mktemp_s` заменяет следующие конечные X пятизначным значением; это значение — уникальное число, определяющее вызывающий процесс или, в многопоточных программах, вызывающий поток.  
  
 Каждый успешный вызов `_mktemp_s` изменяет `template`.  В каждом последующем вызове из одного и того же процесса или потока с тем же аргументом `template`, проверка `_mktemp_s` имен файлов, которые соответствуют, возвращаемых в предыдущих вызовах `_mktemp_s`.  Если не существует файла с данным именем, `_mktemp_s` возвращает это имя.  Если файлы существуют для всех ранее возвращенных имен, `_mktemp_s` создает новое имя, заменив алфавитный символ, используемый ранее, следующей доступной буквой нижнего регистра, в порядке от "a" до "z".  Например, если: `base` это:  
  
```  
fn  
```  
  
 и пятизначное значение, возвращенное `_mktemp_s` — 12345, первое возвращенное имя:  
  
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
  
 `_mktemp_s` может создать максимум 26 уникальных имен файлов для всех заданных сочетаний значений base и template.  Поэтому FNZ12345 последнее уникальное имя файла, которое `_mktemp_s` может создать для значений `base` и `template`, используемых в данном примере.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mktemp_s`|\<io.h\>|  
|`_wmktemp_s`|\<io.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## Пример результатов выполнения  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
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
 [tmpfile\_s](../Topic/tmpfile_s.md)