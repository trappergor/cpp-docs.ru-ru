---
title: "_lfind_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lfind_s
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
- lfind_s
- _lfind_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
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
ms.openlocfilehash: c50893f1dc73db9f928eaea346a381d1bd991d2f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="lfinds"></a>_lfind_s
Выполняет линейный поиск указанного ключа. Версия функции [_lfind](../../c-runtime-library/reference/lfind.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало данных, где будет производиться поиск.  
  
 `num`  
 Число элементов массива.  
  
 `size`  
 Размер элементов массива в байтах.  
  
 `compare`  
 Указатель на подпрограмму сравнения. Первый параметр — это указатель `context`. Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.  
  
 `context`  
 Указатель на объект, доступ к которому может получить функция сравнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если ключ найден, функция `_lfind_s` возвращает указатель на элемент массива `base`, соответствующий `key`. Если ключ не найден, функция `_lfind_s` возвращает значение `NULL`.  
  
 Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL` , и функция возвращает значение `NULL`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|клавиша|базовые|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|любые|любые|любые|любые|`EINVAL`|  
|любые|`NULL`|любые|!= 0|любые|`EINVAL`|  
|любые|любые|любые|any|нуль|`EINVAL`|  
|any|любые|`NULL`|любой|любые|`EINVAL`|  
  
## <a name="remarks"></a>Примечания  
 Функция `_lfind_s` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width` каждый. В отличие от функции `bsearch_s`, `_lfind_s` не требует, чтобы массив был отсортирован. Аргумент `base` является указателем на начало массива, в котором осуществляется поиск. Аргумент `compare` является указателем на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения. Во время поиска функция `_lfind_s` вызывает подпрограмму `compare` один или несколько раз, передавая указатель `context` и указатели на два элемента массива при каждом вызове. Подпрограмма `compare` должна сравнивать элементы и возвращать либо отличное от нуля значение (если элементы различаются), либо 0 (если элементы идентичны).  
  
 Функция `_lfind_s` схожа с `_lfind`, однако добавляет указатель `context` к аргументам функции сравнения и списку параметров функции. Указатель `context` может быть полезен, если структура данных, в которой производится поиск, является частью объекта и функции `compare` требуется доступ к членам объекта. Функция `compare` может привести указатель void к соответствующему типу объекта и получить доступ к членам этого объекта. Добавление параметра `context` делает функцию `_lfind_s` более безопасной, так как наличие дополнительного контекста может использоваться для предотвращения ошибок повторного входа, связанных с использованием статических переменных для предоставления функции `compare` доступа к данным.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_lfind_s`|\<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
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
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)
