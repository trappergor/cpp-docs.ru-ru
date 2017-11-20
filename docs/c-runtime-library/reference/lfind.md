---
title: "_lfind | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lfind
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
- lfind
- _lfind
dev_langs: C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f883aa9f17c8272335a91ebf333e050888be8257
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lfind"></a>_lfind
Выполняет линейный поиск указанного ключа. Существует более безопасная версия этой функции; см. раздел [_lfind_s](../../c-runtime-library/reference/lfind-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало данных, где будет производиться поиск.  
  
 `num`  
 Число элементов массива.  
  
 `width`  
 Ширина элементов массива.  
  
 `compare`  
 Указатель на подпрограмму сравнения. Первый параметр — это указатель на ключ для поиска. Второй параметр — это указатель на элемент массива, который будет сравниваться с ключом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если ключ найден, функция `_lfind` возвращает указатель на элемент массива `base`, соответствующий `key`. Если ключ не найден, функция `_lfind` возвращает значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_lfind` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width` каждый. В отличие от функции `bsearch`, `_lfind` не требует, чтобы массив был отсортирован. Аргумент `base` является указателем на начало массива, в котором осуществляется поиск. Аргумент `compare` является указателем на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения. Во время поиска функция `_lfind` вызывает подпрограмму `compare` один или несколько раз, передавая указатели на два элемента массива при каждом вызове. Подпрограмма `compare` должна сравнивать элементы и возвращать либо отличное от нуля значение (если элементы различаются), либо 0 (если элементы идентичны).  
  
 Эта функция проверяет свои параметры. Если параметр `compare`, `key` или `num` имеет значение `NULL`, или параметр `base` имеет значение NULL и параметр *`num` не равен нулю, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` , и функция возвращает значение `NULL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_lfind`|\<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
Hello found  
```  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)