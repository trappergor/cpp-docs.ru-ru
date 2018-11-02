---
title: _lfind_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
ms.openlocfilehash: 08c04d9d1ca69998d54304c96468298013907179
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648449"
---
# <a name="lfinds"></a>_lfind_s

Выполняет линейный поиск указанного ключа. Версия функции [_lfind](lfind.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lfind_s(
   const void *key,
   const void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*номер*<br/>
Число элементов массива.

*size*<br/>
Размер элементов массива в байтах.

*compare*<br/>
Указатель на подпрограмму сравнения. Первый параметр — *контекст* указатель. Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.

*context*<br/>
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lfind_s** возвращает указатель на элемент массива в *базового* , соответствующий *ключ*. Если ключ не найден, **_lfind_s** возвращает **NULL**.

Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **NULL**.

### <a name="error-conditions"></a>Условия ошибок

|клавиша|базовые|compare|num|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**NULL**|any|any|any|any|**EINVAL**|
|any|**NULL**|any|!= 0|any|**EINVAL**|
|any|any|any|any|нуль|**EINVAL**|
|any|any|**NULL**|любой|any|**EINVAL**|

## <a name="remarks"></a>Примечания

**_Lfind_s** функция выполняет линейный поиск значения *ключ* массива *номер* элементов, каждый из которых *ширины* байт. В отличие от **bsearch_s**, **_lfind_s** не требует, чтобы сортировать массив. *Базового* аргумент является указателем на базовый массив для поиска. *Сравнения* аргумент — указатель на предоставляемую пользователем подпрограмму, которая сравнивает два элемента массива и возвращает значение, указывающее их связь. **_lfind_s** вызовы *сравнения* рутинных один или несколько раз во время поиска, передавая *контекст* указателей и указатели на два элемента массива при каждом вызове. *Сравнения* подпрограмма должна сравнивать элементы и возвращать ненулевое значение (это означает, что элементы различаются) или 0 (если элементы идентичны).

**_lfind_s** аналогичен **_lfind** за исключением добавления *контекст* указатель на аргументы функции сравнения и список параметров функции. *Контекст* указатель может быть полезно, если структура которой выполняется поиск данных является частью объекта и *сравнения* функции требуется доступ к членам объекта. *Сравнения* функции может привести указатель void в соответствующий объект типа и доступа к членам этого объекта. Добавление *контекст* делает **_lfind_s** более безопасной, поскольку дополнительного контекста может использоваться для предотвращения ошибок повторного входа, связанных с использованием статических переменных для предоставление доступа к данным *сравнения* функции.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
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

[Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
