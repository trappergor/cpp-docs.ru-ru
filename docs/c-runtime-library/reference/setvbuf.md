---
title: setvbuf
ms.date: 11/04/2016
apiname:
- setvbuf
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: d4336c6cc478a035fcc0b9b059a7161d58bc4442
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328101"
---
# <a name="setvbuf"></a>setvbuf

Управляет потоковой буферизацией и размером буфера.

## <a name="syntax"></a>Синтаксис

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Указатель на структуру **FILE**.

*buffer*<br/>
Выделенный пользователем буфер.

*mode*<br/>
Режим буферизации.

*size*<br/>
Размер буфера в байтах. Допустимый диапазон: 2 < = *размер* < = INT_MAX (2147483647). На внутреннем уровне значение, указанное для *размер* округляется вниз до ближайшего числа, кратного 2.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха.

Если *поток* — **NULL**, или если *режим* или *размер* является не в допустимый диапазон, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает -1 и задает **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Setvbuf** функция позволяет программе управлять и буферизацией и размером буфера для *поток*. *поток* должен ссылаться на открытый файл, которого не выполнялись операции ввода-вывода, так как он был открыт. Массив, на которые указывают *буфера* используется в качестве буфера, если только это не **NULL**в этом случае **setvbuf** использует автоматически выделенный буфер длиной  *размер*/2 \* 2 байта.

Должен быть установлен режим **_IOFBF**, **_IOLBF**, или **_IONBF**. Если *режим* — **_IOFBF** или **_IOLBF**, затем *размер* используется в качестве размера буфера. Если *режим* — **_IONBF**, поток без буферизации и *размер* и *буфера* игнорируются. Значения для *режим* и их значений:

|*режим* значение|Значение|
|-|-|
| **_IOFBF** | Полная буферизация; то есть *буфера* используется в качестве буфера и *размер* используется в качестве размера буфера. Если *буфера* — **NULL**, используется автоматически выделенный буфер *размер* используется байт. |
| **_IOLBF** | В некоторых системах таким образом осуществляется линейная буферизация. Однако для Win32, поведение совпадает со значением **_IOFBF** -полная буферизация. |
| **_IONBF** | Буфер не используется, независимо от того, *буфера* или *размер*. |

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
