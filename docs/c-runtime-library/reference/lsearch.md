---
title: "_lsearch | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch
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
- _lsearch
- lsearch
dev_langs:
- C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 86dd9925775d50a8e1c79f677f3e5b1d9ad3ae37
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="lsearch"></a>_lsearch
Выполняет линейный поиск значения и добавляет значение в конец списка, если оно не найдено. Существует более безопасная версия этой функции; см. раздел [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало массива, где будет производиться поиск.  
  
 `num`  
 Число элементов.  
  
 `width`  
 Ширина каждого элемента массива.  
  
 `compare`  
 Указатель на подпрограмму сравнения. Первый параметр — это указатель на ключ для поиска. Второй параметр — это указатель на элемент массива, который будет сравниваться с ключом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если ключ найден, функция `_lsearch` возвращает указатель на элемент массива `base`, соответствующий `key`. Если ключ `_lsearch` не найден, возвращает указатель на вновь добавленный в конец массива элемент.  
  
## <a name="remarks"></a>Примечания  
 Функция `_lsearch` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width` каждый. В отличие от функции `bsearch`, `_lsearch` не требует, чтобы массив был отсортирован. Если `key` не найден, `_lsearch` добавляет его в конец массива и увеличивает `num` на единицу.  
  
 Аргумент `compare` является указателем на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения. Во время поиска функция `_lsearch` вызывает подпрограмму `compare` один или несколько раз, передавая указатели на два элемента массива при каждом вызове. Функция `compare` должна сравнивать элементы и возвращать либо отличное от нуля значение (если элементы различаются), либо 0 (если элементы идентичны).  
  
 Эта функция проверяет свои параметры. Если параметр `compare`, `key` или `num` имеет значение `NULL`, или параметр `base` имеет значение NULL и параметр *`num` не равен нулю, или если `width` меньше нуля, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` , и функция возвращает значение `NULL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_lsearch`|\<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)
