---
title: "bsearch | Microsoft Docs"
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
  - "bsearch"
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
  - "bsearch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "массивы [CRT], двоичный поиск"
  - "bsearch -функция"
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет двоичный поиск по отсортированному массиву. Существует более безопасная версия этой функции, см. раздел [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## Синтаксис  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало данных, где будет производиться поиск.  
  
 `num`  
 Число элементов.  
  
 `width`  
 Ширина элементов.  
  
 `compare`  
 Функция обратного вызова, которая сравнивает два элемента. Первый — это указатель на ключ для поиска, а второй — указатель на элемент массива, который будет сравниваться с ключом.  
  
## Возвращаемое значение  
 Функция `bsearch` возвращает указатель на вхождение `key` в массиве, на который указывает `base`. Если `key` не найден, функция возвращает `NULL`. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.  
  
## Заметки  
 Функция `bsearch` выполняет двоичный поиск по отсортированному массиву, состоящему из `num` элементов размером `width` байт каждый. Значение `base` — это указатель на начало массива, в котором должен производиться поиск, а `key` — искомое значение. Параметр `compare` — это указатель на предоставляемую пользователем подпрограмму, которая сравнивает заданный ключ с элементом массива и возвращает одно из следующих значений, показывающих, как соотносятся значения ключа и элемента массива:  
  
|Значение, возвращаемое подпрограммой `compare`|Описание|  
|----------------------------------------------------|--------------|  
|\< 0|Ключ меньше, чем элемент массива.|  
|0|Ключ равен элементу массива.|  
|\> 0|Ключ больше, чем элемент массива.|  
  
 Эта функция проверяет свои параметры. Если параметр `compare`, `key` или `num` имеет значение `NULL`, или если параметр `base` имеет значение `NULL`, а `num` не равен нулю, или если `width` равен нулю, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `NULL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`bsearch`|\<stdlib.h\> и \<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Программа сортирует массив строк с помощью qsort, а затем использует bsearch для поиска слова "cat".  
  
```  
// crt_bsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( char **arg1, char **arg2 )  
{  
   /* Compare all of both strings: */  
   return _strcmpi( *arg1, *arg2 );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
   char **result;  
   char *key = "cat";  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const   
   void*, const void*))compare );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),  
                              sizeof( char * ), (int (*)(const void*, const void*))compare );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
cat cow dog goat horse human pig rat cat found at 002F0F04  
```  
  
## Эквивалент в .NET Framework  
 [System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)