---
title: bsearch_s
ms.date: 4/2/2020
api_name:
- bsearch_s
- _o_bsearch_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- bsearch_s
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch_s function
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
ms.openlocfilehash: ef8a68f0db45e718af6b17fe0d08c33a6fd61d6c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333846"
---
# <a name="bsearch_s"></a>bsearch_s

Выполняет двоичный поиск по отсортированному массиву. Эта функция представляет собой версию [bsearch](bsearch.md) с улучшениями безопасности, как описано в [функциях безопасности в CRT.](../../c-runtime-library/security-features-in-the-crt.md)

## <a name="syntax"></a>Синтаксис

```C
void *bsearch_s(
   const void *key,
   const void *base,
   size_t number,
   size_t width,
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),
   void * context
);
```

### <a name="parameters"></a>Параметры

*Ключ*\
Указатель на ключ для поиска.

*Базы*\
Указатель на базу данных поиска.

*Номер*\
Число элементов.

*Ширина*\
Ширина элементов.

*Сравнить*\
Функция обратного вызова, которая сравнивает два элемента. Первым аргументом является указатель *контекста.* Второй аргумент — указатель на *ключ* для поиска. Третий аргумент — это указатель на элемент массива, который следует сравнивать с *ключом.*

*Контексте*\
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

**bsearch_s** возвращает указатель на появление *ключа* в массиве, на который указывает *база.* Если *ключ* не найден, функция возвращает **NULL**. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.

Если недействительные параметры передаются функции, он вызывает недействительный обработчик параметров, описанный в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибок

|||||||
|-|-|-|-|-|-|
|*Ключ*|*base*|*Сравнить*|*число*|*width*|**errno**|
|**Null**|any|any|any|any|**EINVAL**|
|any|**Null**|any|!= 0|any|**EINVAL**|
|any|any|any|any|= 0|**EINVAL**|
|any|any|**Null**|любой|any|**EINVAL**|

## <a name="remarks"></a>Remarks

Функция **bsearch_s** выполняет двоичный поиск отсортированного массива *численных* элементов, каждый из *байтов ширины* в размерах. *Базовое* значение является указателем на базу массива для поиска, а *ключом* является испрашиваемый значение. Параметр *сравнения* является указателем на рутину, поставляемую пользователем, которая сравнивает запрашиваемый ключ с элементом массива и возвращает одно из следующих значений, определяющих их связь:

|Значение возвращается *по сравнению* рутины|Описание|
|-----------------------------------------|-----------------|
|\< 0|Ключ меньше, чем элемент массива.|
|0|Ключ равен элементу массива.|
|> 0|Ключ больше, чем элемент массива.|

Указатель *контекста* может быть полезен, если поисковая структура данных является частью объекта, а функция сравнения должна получить доступ к членам объекта. Функция *сравнения* может бросить указатель пустоты в соответствующий тип объекта и доступ к членам этого объекта. Добавление параметра *контекста* делает **bsearch_s** более безопасным, поскольку дополнительный контекст может быть использован для предотвращения ошибок повторного использования статических переменных для обеспечения доступности данных для функции *сравнения.*

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Программа сортирует массив строк с помощью функции [qsort_s](qsort-s.md), а затем использует bsearch_s для поиска слова cat.

```cpp
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
cat cow dog goat horse human pig rat
cat found at 002F0F04
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
