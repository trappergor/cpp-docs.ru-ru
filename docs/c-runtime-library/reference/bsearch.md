---
title: bsearch
ms.date: 11/04/2016
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
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: a5f4542623dfa503d7ec43dff0cf0de9e69ccec4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464848"
---
# <a name="bsearch"></a>bsearch

Выполняет двоичный поиск по отсортированному массиву. Существует более безопасная версия этой функции, см. раздел [bsearch_s](bsearch-s.md).

## <a name="syntax"></a>Синтаксис

```C
void *bsearch(
   const void *key,
   const void *base,
   size_t num,
   size_t width,
   int ( __cdecl *compare ) (const void *key, const void *datum)
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*номер*<br/>
Число элементов.

*width*<br/>
Ширина элементов.

*compare*<br/>
Функция обратного вызова, которая сравнивает два элемента. Первый — это указатель на ключ для поиска, а второй — указатель на элемент массива, который будет сравниваться с ключом.

## <a name="return-value"></a>Возвращаемое значение

**bsearch** возвращает указатель на вхождение *ключ* в массиве, на которые указывают *базового*. Если *ключ* не найден, функция возвращает **NULL**. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.

## <a name="remarks"></a>Примечания

**Bsearch** функция выполняет двоичный поиск по отсортированному массиву из *номер* элементов, каждый из которых *ширины* байт размером. *Базового* значение — это указатель на базовый массив, в который будет выполняться поиск, и *ключ* является искомое значение. *Сравнения* параметр — указатель на предоставляемую пользователем подпрограмму, которая сравнивает запрошенный раздел на элемент массива и возвращает одно из следующих значений, определяющее их связь:

|Значение, возвращенное *сравнения* подпрограмму|Описание|
|-----------------------------------------|-----------------|
|\< 0|Ключ меньше, чем элемент массива.|
|0|Ключ равен элементу массива.|
|> 0|Ключ больше, чем элемент массива.|

Эта функция проверяет свои параметры. Если *сравнения*, *ключ* или *номер* — **NULL**, или если *базового* является **NULL**и *номер* не равно нулю, или если *ширины* равен нулю, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается `EINVAL` и функция возвращает **NULL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Программа сортирует массив строк с помощью qsort, а затем использует bsearch для поиска слова "cat".

```C
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

[Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
