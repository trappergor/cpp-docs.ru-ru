---
title: "bsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch_s"
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
  - "bsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [CRT], двоичный поиск"
  - "bsearch_s - функция"
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# bsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет двоичный поиск по отсортированному массиву. Это версия функции [bsearch](../../c-runtime-library/reference/bsearch.md) с усовершенствованиями в части безопасности, описанными в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
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
 Функция обратного вызова, которая сравнивает два элемента. Первый аргумент — это указатель `context`. Второй аргумент — указатель на ключ `key` для поиска. Третий аргумент — указатель на элемент массива, который будет сравниваться со значением `key`.  
  
 `context`  
 Указатель на объект, доступ к которому может получить функция сравнения.  
  
## Возвращаемое значение  
 Функция `bsearch_s` возвращает указатель на вхождение`key` в массиве, на который указывает `base`. Если `key` не найден, функция возвращает `NULL`. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.  
  
 Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для `errno`задается значение `EINVAL`, и функция возвращает значение `NULL`. Дополнительные сведения см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
### Условия ошибок  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|любые|any|any|any|`EINVAL`|  
|any|`NULL`|любые|\!\= 0|любые|`EINVAL`|  
|any|any|any|any|\= 0|`EINVAL`|  
|любые|любые|`NULL`|любой|любые|`EINVAL`|  
  
## Заметки  
 Функция `bsearch_s` выполняет двоичный поиск по отсортированному массиву, состоящему из `num` элементов размером `width` байт каждый. Значение `base` — это указатель на начало массива, в котором должен производиться поиск, а `key` — искомое значение. Параметр `compare` — это указатель на предоставляемую пользователем подпрограмму, которая сравнивает заданный ключ с элементом массива и возвращает одно из следующих значений, показывающих, как соотносятся значения ключа и элемента массива:  
  
|Значение, возвращаемое подпрограммой `compare`|Описание|  
|----------------------------------------------------|--------------|  
|\< 0|Ключ меньше, чем элемент массива.|  
|0|Ключ равен элементу массива.|  
|\> 0|Ключ больше, чем элемент массива.|  
  
 Указатель `context` может быть полезен, если структура данных, в которой производится поиск, является частью объекта, и функции сравнения требуется доступ к членам этого объекта. Функция `compare` может привести указатель void к соответствующему типу объекта и получить доступ к членам этого объекта. Добавление параметра `context` делает `bsearch_s` более безопасной, поскольку наличие дополнительного контекста может использоваться для предотвращения ошибок повторного входа, связанных с использованием статических переменных для предоставления функции `compare` доступа к данным.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`bsearch_s`|\<stdlib.h\> и \<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 Программа сортирует массив строк с помощью функции [qsort\_s](../../c-runtime-library/reference/qsort-s.md), а затем использует bsearch\_s для поиска слова cat.  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
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
 <xref:System.Collections.ArrayList.BinarySearch%2A>  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)