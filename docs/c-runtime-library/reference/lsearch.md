---
title: "lsearch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lsearch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lsearch - функция"
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _lsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет линейный выполняет поиск значения; добавляет в конец списка, если значение не найдено.  Существует более безопасная версия этой функции; см. раздел [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## Синтаксис  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало массива для поиска.  
  
 `num`  
 Количество элементов.  
  
 `width`  
 Ширина каждого элемента массива.  
  
 `compare`  
 Указатель на процедуру сравнения.  Первый параметр — указатель на ключ для поиска.  Второй параметр — указатель на элемент массива, который будет сравниваться с ключом.  
  
## Возвращаемое значение  
 Если ключ найден, `_lsearch` возвращает указатель на элемент массива `base`, соответствующий `key`.  Если ключ не найден, `_lsearch` возвращает указатель на вновь добавленный в конец массива элемент.  
  
## Заметки  
 Функция `_lsearch` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width`.  В отличие от `bsearch`, `_lsearch` не требует сортированный массив.  Если `key` не найден, `_lsearch` добавляет его в конец массива и увеличивает `num`.  
  
 Аргумент `compare` является указателем на пользовательскую процедуру, которая сравнивает два элемента массива и возвращает значение, которое показывает, как соотносятся их значения.  `_lsearch` вызывает процедуру `compare` один или несколько раз во время поиска, передавая указатели на два элемента массива при каждом вызове:  `compare` должна сравнивать элементы и возвращать или отличное от нуля \(то есть элементы различаются\) или 0 \(если элементы совпадают\).  
  
 Эта функция проверяет свои параметры.  Если `compare`, `key` или `num` имеют значение `NULL`, или если `base` имеет значение NULL и \*`num` отлично от нуля, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `NULL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_lsearch`|\<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
  **wordlist before \_lsearch: hello thanks bye**  
**wordlist after \_lsearch: hello thanks bye extra**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)