---
title: bsearch
ms.date: 10/22/2019
api_name:
- bsearch
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
- bsearch
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
ms.openlocfilehash: 6b476cbdd5e9c072cae03ad1091a96e2d0b7422b
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811098"
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

*ключевые* \
Указатель на ключ для поиска.

*base*\
Указатель на базу данных поиска.

*число*\
Число элементов.

*ширина*\
Ширина элементов.

*сравнить*\
Функция обратного вызова, которая сравнивает два элемента. Первый — указатель на ключ для поиска, а второй — это указатель на элемент массива, который будет сравниваться с ключом.

## <a name="return-value"></a>Возвращаемое значение

**bsearch** возвращает указатель на вхождение *ключа* в массиве, на который указывает *base*. Если *ключ* не найден, функция возвращает **значение NULL**. Если массив не отсортирован по возрастанию или содержит повторяющиеся записи с одинаковыми ключами, результат будет непредсказуемым.

## <a name="remarks"></a>Заметки

Функция **bsearch** выполняет двоичный поиск отсортированного массива *числовых* элементов, каждый из которых имеет размер *в байтах* . *Базовое* значение — это указатель на базовую часть массива для поиска, а *ключ* — искомое значение. Параметр *Compare* — это указатель на предоставляемую пользователем подпрограммы, которая сравнивает запрошенный ключ с элементом массива. Он возвращает одно из следующих значений, определяющих их связь:

|Значение, возвращаемое подпрограммы *сравнения*|Описание|
|-----------------------------------------|-----------------|
|\< 0|Ключ меньше, чем элемент массива.|
|0|Ключ равен элементу массива.|
|> 0|Ключ больше, чем элемент массива.|

Эта функция проверяет свои параметры. Если параметр *Compare*, *ключ* или *число* имеют **значение NULL**или если *base* имеет **значение NULL** , а *Number* имеет ненулевое значение или если *Width* равно нулю, функция вызывает обработчик недопустимых параметров, как описано в разделе [Parameter. Проверка](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметру "переводится" значение **`EINVAL`, а** функция возвращает **значение NULL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**bsearch**|\<stdlib.h> и \<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)\
[_lfind](lfind.md)\
[_lsearch](lsearch.md)\
[qsort](qsort.md)
