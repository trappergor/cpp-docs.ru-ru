---
title: "lfind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind"
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
  - "lfind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lfind - функция"
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _lfind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет линейный поиск указанного ключа.  Существует более безопасная версия этой функции; см. раздел [\_lfind\_s](../Topic/_lfind_s.md).  
  
## Синтаксис  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало данных для поиска.  
  
 `num`  
 Количество элементов массива.  
  
 `width`  
 Ширина элементов массива.  
  
 `compare`  
 Указатель на процедуру сравнения.  Первый параметр — указатель на ключ для поиска.  Второй параметр — указатель на элемент массива, который будет сравниваться с ключом.  
  
## Возвращаемое значение  
 Если ключ найден, `_lfind` возвращает указатель на элемент массива `base`, соответствующий `key`.  Если ключ не найден, `_lfind` возвращает `NULL`.  
  
## Заметки  
 Функция `_lfind` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width`.  В отличие от `bsearch`, `_lfind` не требует сортированный массив.  Аргумент `base` является указателем на начало массива для поиска.  Аргумент `compare` является указателем на пользовательскую процедуру, которая сравнивает два элемента массива и возвращает значение, которое показывает, как соотносятся их значения.  `_lfind` вызывает процедуру `compare` один или несколько раз во время поиска, передавая указатели на два элемента массива при каждом вызове:  Процедура `compare` должна сравнивать элементы и возвращать или отличное от нуля \(то есть элементы различаются\) или 0 \(если элементы совпадают\).  
  
 Эта функция проверяет свои параметры.  Если `compare`, `key` или `num` имеют значение `NULL`, или если `base` имеет значение NULL и \*`num` отлично от нуля, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL` и функция возвращает `NULL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_lfind`|\<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
  **Hello found**   
## Эквивалент в .NET Framework  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind\_s](../Topic/_lfind_s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)