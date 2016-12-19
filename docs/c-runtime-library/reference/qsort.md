---
title: "qsort | Microsoft Docs"
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
  - "qsort"
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
  - "qsort"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Функция qsort"
  - "алгоритм быстрой сортировки"
  - "сортировка массивов"
  - "массивы [CRT], сортировка"
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# qsort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет быструю сортировку.  Существует более безопасная версия этой функции; см. раздел [qsort\_s](../../c-runtime-library/reference/qsort-s.md).  
  
## Синтаксис  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### Параметры  
 `base`  
 Начало целевого массива.  
  
 `num`  
 Размер массива в элементах.  
  
 `width`  
 Размер элементов в байтах.  
  
 `compare`  
 Указатель на предоставленную пользователем процедуру, которая сравнивает два элемента массива и возвращает значение, которое указывает их отношение.  
  
## Заметки  
 Функция `qsort` реализует алгоритм быстрой сортировки для сортировки массива `num` элементов, каждый из которых имеет размер `width` байт.  Аргумент `base` является указателем на начало массива для сортировки.  `qsort` перезапишет этот массив отсортированными элементами.  
  
 `qsort` вызывает процедуру `compare` один или несколько раз во время сортировки, передавая указатели на два элемента массива при каждом вызове.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 Процедура сравнивает элементы и возвращает одно из следующих значений.  
  
|Возвращаемое значение функции сравнения|Описание|  
|---------------------------------------------|--------------|  
|\< 0|`elem1` меньше чем `elem2`.|  
|0|`elem1` равен `elem2`|  
|\> 0|`elem1` больше чем `elem2`.|  
  
 Массив сортируется по возрастанию, как определено функцией сравнения.  Для сортировки массива по убыванию, измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.  
  
 Эта функция проверяет свои параметры.  Если `compare` или `num` имеют значение `NULL` или `base` имеет значение `NULL` и \*`num` отлично от нуля, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция устанавливает `errno` в значение `EINVAL` и завершается.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`qsort`|\<stdlib.h\> и \<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
  **boy deserves every favor good**   
## Эквивалент в .NET Framework  
 [System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)