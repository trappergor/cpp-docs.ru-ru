---
title: bsearch_s
ms.date: 10/22/2019
api_name:
- bsearch_s
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
ms.openlocfilehash: fc86576dbbe73f63da6bf0e28e7166ef7c552e55
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811141"
---
# <a name="bsearch_s"></a>bsearch_s

Выполняет двоичный поиск по отсортированному массиву. Эта функция представляет собой версию [bsearch](bsearch.md) с усовершенствованиями безопасности, как описано в разделе [функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*ключевые* \
Указатель на ключ для поиска.

*base*\
Указатель на базу данных поиска.

*число*\
Число элементов.

*ширина*\
Ширина элементов.

*сравнить*\
Функция обратного вызова, которая сравнивает два элемента. Первым аргументом является указатель *контекста* . Второй аргумент — это указатель на *ключ* для поиска. Третий аргумент — это указатель на элемент массива, который будет сравниваться с *ключом*.

*контекстный*\
Указатель на объект, доступ к которому может получить функция сравнения.

## <a name="return-value"></a>Возвращаемое значение

**bsearch_s** возвращает указатель на вхождение *ключа* в массиве, на который указывает *base*. Если *ключ* не найден, функция возвращает **значение NULL**. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.

Если функции передаются недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а функция возвращает **значение NULL**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибки

|||||||
|-|-|-|-|-|-|
|*key*|*base*|*compare*|*Нумерация*|*width*|**errno**|
|**NULL**|Любое действие|Любое действие|Любое действие|Любое действие|**EINVAL**|
|Любое действие|**NULL**|Любое действие|!= 0|Любое действие|**EINVAL**|
|Любое действие|Любое действие|Любое действие|Любое действие|= 0|**EINVAL**|
|Любое действие|Любое действие|**NULL**|пример|Любое действие|**EINVAL**|

## <a name="remarks"></a>Заметки

Функция **bsearch_s** выполняет двоичный поиск отсортированного массива *числовых* элементов, каждый из которых имеет размер *в байтах* . *Базовое* значение — это указатель на базовую часть массива для поиска, а *ключ* — искомое значение. Параметр *Compare* — это указатель на предоставляемую пользователем подпрограммы, которая сравнивает запрошенный ключ с элементом массива и возвращает одно из следующих значений, задающее их связь:

|Значение, возвращаемое подпрограммы *сравнения*|Описание|
|-----------------------------------------|-----------------|
|\< 0|Ключ меньше, чем элемент массива.|
|0|Ключ равен элементу массива.|
|> 0|Ключ больше, чем элемент массива.|

Указатель *контекста* может быть полезен, если искомая структура данных является частью объекта, а функции Compare требуется доступ к членам объекта. Функция *Compare* может привести указатель void к соответствующему типу объекта и получить доступ к членам этого объекта. Добавление параметра *контекста* делает **bsearch_s** более безопасным, поскольку можно использовать дополнительный контекст, чтобы избежать ошибок повторного входа, связанных с использованием статических переменных, чтобы сделать данные доступными для функции *сравнения* .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**bsearch_s**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
