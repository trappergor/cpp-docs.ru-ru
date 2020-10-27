---
title: qsort
description: Описывает API быстрого сортировки среды выполнения Microsoft C `qsort`
ms.date: 10/23/2020
api_name:
- qsort
- _o_qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
ms.openlocfilehash: c658ffae69cd662809eb4dac09c06b6a13f4e051
ms.sourcegitcommit: faecabcdd12ff53eb79dc0df193fc3567f2f037c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92639124"
---
# <a name="qsort"></a>qsort

Выполняет быструю сортировку. Существует более безопасная версия этой функции, см. раздел [qsort_s](qsort-s.md).

## <a name="syntax"></a>Синтаксис

```C
void qsort(
   void *base,
   size_t number,
   size_t width,
   int (__cdecl *compare )(const void *, const void *)
);
```

### <a name="parameters"></a>Параметры

*`base`*\
Начало целевого массива.

*`number`*\
Размер массива в элементах.

*`width`*\
Размер элементов в байтах.

*`compare`*\
Указатель на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения.

## <a name="remarks"></a>Remarks

**`qsort`** Функция реализует алгоритм быстрой сортировки для сортировки массива *`number`* элементов, каждый из которых равен *`width`* байтам. Аргумент *`base`* — это указатель на базовую часть массива, который необходимо отсортировать. **`qsort`** перезаписывает этот массив с помощью отсортированных элементов.

**`qsort`** вызывает *`compare`* подпрограммы один или несколько раз во время сортировки и передает указатели на два элемента массива при каждом вызове. Если *`compare`* параметр указывает, что два элемента одинаковы, их порядок в результирующем отсортированном массиве не определен.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Подпрограмма сравнивает элементы и возвращает одно из следующих значений.

|Сравнение возвращаемого значения функции|Описание|
|-----------------------------------|-----------------|
|< 0|**`elem1`** меньше **`elem2`**|
|0|**`elem1`** эквивалентно **`elem2`**|
|> 0|**`elem1`** больше **`elem2`**|

Массив сортируется по возрастанию, как определено функцией сравнения. Для сортировки массива по убыванию измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.

Эта функция проверяет свои параметры. Если параметр или имеет значение или имеет значение *`compare`* *`number`* **`NULL`** *`base`* **`NULL`** и *`number`* является ненулевым или значение *`width`* меньше нуля, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает и **`errno`** устанавливается в значение **`EINVAL`** .

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**`qsort`**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)\
[`bsearch`](bsearch.md)\
[`_lsearch`](lsearch.md)
