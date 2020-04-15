---
title: _lfind_s
ms.date: 4/2/2020
api_name:
- _lfind_s
- _o__lfind_s
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 8f2983bee93c623eb936ed12422134281418076b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342187"
---
# <a name="_lfind_s"></a>_lfind_s

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

*Ключ*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*число*<br/>
Число элементов массива.

*Размер*<br/>
Размер элементов массива в байтах.

*Сравнить*<br/>
Указатель на подпрограмму сравнения. Первый параметр — это указатель *контекста.* Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.

*context*<br/>
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lfind_s** возвращает указатель элементу массива на *базе,* которая соответствует *ключу.* Если ключ не найден, **_lfind_s** возвращает **NULL**.

Если недействительные параметры передаются функции, вызовуется обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|ключ|base|compare|num|size|errno|
|---------|----------|-------------|---------|----------|-----------|
|**Null**|any|any|any|any|**EINVAL**|
|any|**Null**|any|!= 0|any|**EINVAL**|
|any|any|any|any|нуль|**EINVAL**|
|any|any|**Null**|любой|any|**EINVAL**|

## <a name="remarks"></a>Remarks

Функция **_lfind_s** выполняет линейный поиск *ключа* значения в массиве *элементов числа,* каждый из байтов *ширины.* В отличие от **bsearch_s,** **_lfind_s** не требует отсортировки массива. *Базовым* аргументом является указатель на основание массива для поиска. Аргумент *сравнения* является указателем на рутину, поставляемую пользователем, которая сравнивает два элемента массива, а затем возвращает значение, определяющее их отношение. **_lfind_s** вызывает *рутину сравнения* один или несколько раз во время поиска, передавая указатель *контекста* и указатели на два элемента массива на каждом вызове. *Режим сравнения* должен сравнить элементы, а затем вернуть ненулевой (имеется в виду, что элементы отличаются) или 0 (имеется в виду элементы идентичны).

**_lfind_s** аналогична **_lfind,** за исключением добавления указателя *контекста* к аргументам функции сравнения и списка параметров функции. Указатель *контекста* может быть полезен, если поисковая структура данных является частью объекта и функция *сравнения* должна получить доступ к членам объекта. Функция *сравнения* может бросить указатель пустоты в соответствующий тип объекта и доступ к членам этого объекта. Добавление параметра *контекста* делает **_lfind_s** более безопасным, поскольку дополнительный контекст может быть использован для предотвращения ошибок повторного использования статических переменных для обеспечения доступности данных для функции *сравнения.*

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lfind_s**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort_s](qsort-s.md)<br/>
[_lfind](lfind.md)<br/>
