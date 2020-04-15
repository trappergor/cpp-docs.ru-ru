---
title: _lsearch
ms.date: 4/2/2020
api_name:
- _lsearch
- _o__lsearch
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
- _lsearch
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
ms.openlocfilehash: a6ef3d86ffe8f03da34d4a374bddda1452815672
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341636"
---
# <a name="_lsearch"></a>_lsearch

Выполняет линейный поиск значения и добавляет значение в конец списка, если оно не найдено. Существует более безопасная версия этой функции; см. раздел [_lsearch_s](lsearch-s.md).

## <a name="syntax"></a>Синтаксис

```C
void *_lsearch(
   const void *key,
   void *base,
   unsigned int *num,
   unsigned int width,
   int (__cdecl *compare)(const void *, const void *)
);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Искомый объект.

*base*<br/>
Указатель на начало массива, где будет производиться поиск.

*число*<br/>
Число элементов.

*width*<br/>
Ширина каждого элемента массива.

*Сравнить*<br/>
Указатель на подпрограмму сравнения. Первый параметр — это указатель на ключ для поиска. Второй параметр — это указатель на элемент массива, который будет сравниваться с ключом.

## <a name="return-value"></a>Возвращаемое значение

Если ключ найден, **_lsearch** возвращает указатель элементу массива на *базе,* которая соответствует *ключу.* Если ключ не найден, **_lsearch** возвращает указатель на недавно добавленный элемент в конце массива.

## <a name="remarks"></a>Remarks

Функция **_lsearch** выполняет линейный поиск *ключа* значения в массиве *элементов числа,* каждый из байтов *ширины.* В отличие от **bsearch,** **_lsearch** не требует отсортировки массива. Если *ключ* не найден, **_lsearch** добавляет его в конец массива и *число*приращений.

Аргумент *сравнения* является указателем на рутину, поставляемую пользователем, которая сравнивает два элемента массива и возвращает значение, определяющее их отношение. **_lsearch** вызывает *рутину сравнения* один или несколько раз во время поиска, передавая указатели на два элемента массива на каждом вызове. *сравнить* должны сравнить элементы и вернуть либо ненулевой (имеется в виду элементы разные) или 0 (имеется в виду элементы идентичны).

Эта функция проверяет свои параметры. Если *сравнивать,* *ключ* или *номер* **NULL,** или если *база* **NULL** и *число* ненулевое, или если *ширина* меньше нуля, вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_lsearch**|\<search.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_lsearch.c
#include <search.h>
#include <string.h>
#include <stdio.h>

int compare( const void *arg1, const void *arg2 );

int main(void)
{
   char * wordlist[4] = { "hello", "thanks", "bye" };
                            // leave room to grow...
   int n = 3;
   char **result;
   char *key = "extra";
   int i;

   printf( "wordlist before _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );

   result = (char **)_lsearch( &key, wordlist,
                      &n, sizeof(char *), compare );

   printf( "wordlist after _lsearch:" );
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );
   printf( "\n" );
}

int compare(const void *arg1, const void *arg2 )
{
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );
}
```

```Output
wordlist before _lsearch: hello thanks bye
wordlist after _lsearch: hello thanks bye extra
```

## <a name="see-also"></a>См. также раздел

[Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch](bsearch.md)<br/>
[_lfind](lfind.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
