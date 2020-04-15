---
title: _lfind
ms.date: 4/2/2020
api_name:
- _lfind
- _o__lfind
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
- _lfind
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
ms.openlocfilehash: 287cbd8bc9cc567a4a0d5b9505d57098197bc545
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342174"
---
# <a name="_lfind"></a>_lfind

Выполняет линейный поиск указанного ключа. Существует более безопасная версия этой функции; см. раздел [_lfind_s](lfind-s.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lfind(
   const void *key,
   const void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомый объект.

*base*<br/>
Указатель на начало данных, где будет производиться поиск.

*число*<br/>
Число элементов массива.

*width*<br/>
Ширина элементов массива.

*Сравнить*<br/>
Указатель на подпрограмму сравнения. Первый параметр — это указатель на ключ для поиска. Второй параметр — это указатель на элемент массива, который будет сравниваться с ключом.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lfind** возвращает указатель элементу массива на *базе,* которая соответствует *ключу.* Если ключ не найден, **_lfind** возвращает **NULL**.

## <a name="remarks"></a>Remarks

Функция **_lfind** выполняет линейный поиск *ключа* значения в массиве *элементов числа,* каждый из байтов *ширины.* В отличие от **bsearch,** **_lfind** не требует отсортировки массива. *Базовым* аргументом является указатель на основание массива для поиска. Аргумент *сравнения* является указателем на рутину, поставляемую пользователем, которая сравнивает два элемента массива, а затем возвращает значение, определяющее их отношение. **_lfind** вызывает *рутину сравнения* один или несколько раз во время поиска, передавая указатели на два элемента массива на каждом вызове. *Режим сравнения* должен сравнить элементы, а затем вернуть ненулевой (имеется в виду элементы разные) или 0 (имеется в виду элементы идентичны).

Эта функция проверяет свои параметры. Если *сравнивать,* *ключ* или *номер* **NULL,** или если *база* **NULL** и *число* ненулевое, или если *ширина* меньше нуля, вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lfind**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_lfind.c
// This program uses _lfind to search a string array
// for an occurrence of "hello".

#include <search.h>
#include <string.h>
#include <stdio.h>

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}

int main( )
{
   char *arr[] = {"Hi", "Hello", "Bye"};
   int n = sizeof(arr) / sizeof(char*);
   char **result;
   char *key = "hello";

   result = (char **)_lfind( &key, arr,
                      &n, sizeof(char *), compare );

   if( result )
      printf( "%s found\n", *result );
   else
      printf( "hello not found!\n" );
}
```

```Output
Hello found
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[bsearch](bsearch.md)<br/>
[_lsearch](lsearch.md)<br/>
[qsort](qsort.md)<br/>
