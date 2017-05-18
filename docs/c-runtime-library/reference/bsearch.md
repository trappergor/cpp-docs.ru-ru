---
title: "bsearch | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- bsearch
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
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- bsearch
dev_langs:
- C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 431bb94e27397f8a0242c45db83e00250e5c82f3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="bsearch"></a>bsearch
Выполняет двоичный поиск по отсортированному массиву. Существует более безопасная версия этой функции, см. раздел [bsearch_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### <a name="parameters"></a>Параметры  
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
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `bsearch` возвращает указатель на вхождение `key` в массиве, на который указывает `base`. Если `key` не найден, функция возвращает `NULL`. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.  
  
## <a name="remarks"></a>Примечания  
 Функция `bsearch` выполняет двоичный поиск по отсортированному массиву, состоящему из `num` элементов размером `width` байт каждый. Значение `base` — это указатель на начало массива, в котором должен производиться поиск, а `key` — искомое значение. Параметр `compare` — это указатель на предоставляемую пользователем подпрограмму, которая сравнивает заданный ключ с элементом массива и возвращает одно из следующих значений, показывающих, как соотносятся значения ключа и элемента массива:  
  
|Значение, возвращаемое подпрограммой `compare`|Описание|  
|-----------------------------------------|-----------------|  
|\< 0|Ключ меньше, чем элемент массива.|  
|0|Ключ равен элементу массива.|  
|> 0|Ключ больше, чем элемент массива.|  
  
 Эта функция проверяет свои параметры. Если `compare`, `key` или `num` имеет значение `NULL`, или если параметр `base` имеет значение `NULL` , а`num` не равен нулю, или если `width` равен нулю, вызывается обработчик недопустимого параметра, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` , и функция возвращает значение `NULL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`bsearch`|\<stdlib.h> и \<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
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
cat cow dog goat horse human pig rat  
cat found at 002F0F04  
```  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)
