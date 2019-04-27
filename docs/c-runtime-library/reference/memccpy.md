---
title: _memccpy
ms.date: 11/04/2016
apiname:
- _memccpy
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _memccpy
helpviewer_keywords:
- _memccpy function
- memccpy function
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
ms.openlocfilehash: 5cd037974d8580b6ee90b1af736e8f2c6897fe8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156607"
---
# <a name="memccpy"></a>_memccpy

Копирует символы из буфера.

## <a name="syntax"></a>Синтаксис

```C
void *_memccpy(
   void *dest,
   const void *src,
   int c,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Указатель на назначение.

*src*<br/>
Указатель на источник.

*c*<br/>
Последний символ для копирования.

*count*<br/>
Число символов.

## <a name="return-value"></a>Возвращаемое значение

Если символ *c* копируется, **_memccpy** возвращает указатель на тип char в *dest* , сразу после символа. Если *c* не копируется, он возвращает **NULL**.

## <a name="remarks"></a>Примечания

**_Memccpy** функция копирует 0 или более символов *src* для *dest*, останавливаясь после символа *c* был скопирован или когда *число* символы были скопированы, какое событие произойдет первым.

**Примечание о безопасности.** Убедитесь в том, что буфер назначения равен по размеру исходному буферу или превосходит его. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_memccpy**|\<memory.h> или \<string.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_memccpy.c

#include <memory.h>
#include <stdio.h>
#include <string.h>

char string1[60] = "The quick brown dog jumps over the lazy fox";

int main( void )
{
   char buffer[61];
   char *pdest;

   printf( "Function: _memccpy 60 characters or to character 's'\n" );
   printf( "Source: %s\n", string1 );
   pdest = _memccpy( buffer, string1, 's', 60 );
   *pdest = '\0';
   printf( "Result: %s\n", buffer );
   printf( "Length: %d characters\n", strlen( buffer ) );
}
```

### <a name="output"></a>Вывод

```Output
Function: _memccpy 60 characters or to character 's'
Source: The quick brown dog jumps over the lazy fox
Result: The quick brown dog jumps
Length: 25 characters
```

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
