---
title: "qsort | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- qsort
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a39f6edf9dfdf2130bfe9d00cc2a9453f48ad9f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="qsort"></a>qsort
Выполняет быструю сортировку. Существует более безопасная версия этой функции, см. раздел [qsort_s](../../c-runtime-library/reference/qsort-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `base`  
 Начало целевого массива.  
  
 `num`  
 Размер массива в элементах.  
  
 `width`  
 Размер элементов в байтах.  
  
 `compare`  
 Указатель на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения.  
  
## <a name="remarks"></a>Примечания  
 Функция `qsort` реализует алгоритм быстрой сортировки для сортировки массива из `num` элементов, каждый из которых имеет размер `width` байт. Аргумент `base` является указателем на начало сортируемого массива. Функция `qsort` перезаписывает этот массив с использованием отсортированных элементов.  
  
 Во время сортировки функция `qsort` вызывает подпрограмму `compare` один или несколько раз и передает указатели на два элемента массива при каждом вызове.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 Подпрограмма сравнивает элементы и возвращает одно из следующих значений.  
  
|Сравнение возвращаемого значения функции|Описание:|  
|-----------------------------------|-----------------|  
|< 0|`elem1` меньше `elem2`|  
|0|`elem1` эквивалентен `elem2`|  
|> 0|`elem1` больше `elem2`|  
  
 Массив сортируется по возрастанию, как определено функцией сравнения. Для сортировки массива по убыванию измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.  
  
 Эта функция проверяет свои параметры. Если параметр `compare` или `num` имеет значение `NULL`, или параметр `base` имеет значение `NULL`, а параметр `num` не равен нулю, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает управление и устанавливает для `errno` значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h> и \<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
boy deserves every favor good  
```  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)