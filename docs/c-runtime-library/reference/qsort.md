---
title: qsort
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 09de57e206eb6fd4a75a0a9444332136aeee0e9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338249"
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

*base*<br/>
Начало целевого массива.

*число*<br/>
Размер массива в элементах.

*width*<br/>
Размер элементов в байтах.

*Сравнить*<br/>
Указатель на пользовательскую подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения.

## <a name="remarks"></a>Remarks

Функция **qsort** реализует алгоритм быстрого сортировки для сортировки массива *элементов чиней,* каждый из байтов *ширины.* *База* аргументов является указателем на основание массива для сортировки. **qsort** перезаписывает этот массив с помощью отсортированных элементов.

**qsort** вызывает *рутину сравнения* один или несколько раз во время сортировки и передает указатели двум элементам массива на каждом вызове.

```C
compare( (void *) & elem1, (void *) & elem2 );
```

Подпрограмма сравнивает элементы и возвращает одно из следующих значений.

|Сравнение возвращаемого значения функции|Описание|
|-----------------------------------|-----------------|
|< 0|**elem1** меньше, чем **elem2**|
|0|**elem1** эквивалент **elem2**|
|> 0|**elem1** больше, чем **elem2**|

Массив сортируется по возрастанию, как определено функцией сравнения. Для сортировки массива по убыванию измените смысл значений "больше" и "меньше" на противоположный в функции сравнения.

Эта функция проверяет свои параметры. Если *сравнение* или *число* **NULL,** или если *база* **NULL** и *число* ненулевое, или если *ширина* меньше нуля, вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращается и **errno** устанавливается в **EINVAL**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**qsort**|\<stdlib.h> и \<search.h>|

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

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
