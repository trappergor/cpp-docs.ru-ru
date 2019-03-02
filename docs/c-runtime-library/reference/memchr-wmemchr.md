---
title: memchr, wmemchr
ms.date: 11/04/2016
apiname:
- wmemchr
- memchr
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- memchr
- wmemchr
helpviewer_keywords:
- memchr function
- wmemchr function
ms.assetid: 5a348581-28f1-4256-8434-687245f7fc9f
ms.openlocfilehash: cbd8b80ed42a6532fb7161fab7217a772a2cb777
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57209903"
---
# <a name="memchr-wmemchr"></a>memchr, wmemchr

Выполняет поиск символов в буфере.

## <a name="syntax"></a>Синтаксис

```C
void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C only
void *memchr(
   void *buffer,
   int c,
   size_t count
); // C++ only
const void *memchr(
   const void *buffer,
   int c,
   size_t count
); // C++ only
wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C only
wchar_t *wmemchr(
   wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
const wchar_t *wmemchr(
   const wchar_t * buffer,
   wchar_t c,
   size_t count
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Указатель на буфер.

*c*<br/>
Символ для поиска.

*count*<br/>
Число проверяемых символов.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает указатель на первое расположение *c* в *буфера*. В противном случае возвращается значение NULL.

## <a name="remarks"></a>Примечания

`memchr` и `wmemchr` поиск первого вхождения *c* в первом *число* байт *буфера*. Он останавливается при обнаружении *c* или после проверки первый *число* байтов.

В языке C, эти функции принимают **const** указатель для первого аргумента. В языке C++ доступны две перегрузки. Перегрузка, принимающая указатель на **const** возвращает указатель на **const**; версия, которая принимает указатель на не -**const** возвращает указатель на не -**const** . _CRT_CONST_CORRECT_OVERLOADS макрос определен в том случае, если оба **const** и не-**const** доступны версии этих функций. Если вам требуется отличного**const** поведение для обоих реализовать C++, определите символ _CONST_RETURN.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`memchr`|\<memory.h> или \<string.h>|
|`wmemchr`|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_memchr.c

#include <memory.h>
#include <stdio.h>

int  ch = 'r';
char str[] =    "lazy";
char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int result;
   printf( "String to be searched:\n             %s\n", string );
   printf( "             %s\n             %s\n\n", fmt1, fmt2 );

   printf( "Search char: %c\n", ch );
   pdest = memchr( string, ch, sizeof( string ) );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf( "Result:      %c found at position %d\n", ch, result );
   else
      printf( "Result:      %c not found\n" );
}
```

### <a name="output"></a>Вывод

```Output
String to be searched:
             The quick brown dog jumps over the lazy fox
                      1         2         3         4         5
             12345678901234567890123456789012345678901234567890

Search char: r
Result:      r found at position 12
```

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
