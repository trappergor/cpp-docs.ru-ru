---
title: setvbuf | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c516932eb8d50fb8c9fdbe6f8c48a3f590b1ffb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408488"
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

*Поток*<br/>
Указатель на структуру **FILE**.

*buffer*<br/>
Выделенный пользователем буфер.

*mode*<br/>
Режим буферизации.

*size*<br/>
Размер буфера в байтах. Допустимый диапазон: 2 < = *размер* < = INT_MAX (2147483647). На внутреннем уровне значение, указанное для *размер* округляется вниз до ближайшего числа, кратного 2.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха.

Если *поток* — **NULL**, или, если *режим* или *размер* находится вне пределов допустимого изменения, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает -1 и задает **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Setvbuf** функция позволяет программе управления обоих буферизации и размер для буфера *поток*. *поток* должен ссылаться на открытый файл, который не был отредактирован операцию ввода-вывода с момента его открытия. Массив, на который указывает *буфера* используется в качестве буфера, если он не является **NULL**в этом случае **setvbuf** используется автоматически выделенный буфер длины  *размер*/2 * 2 байта.

Должен быть установлен режим **_IOFBF**, **_IOLBF**, или **_IONBF**. Если *режим* — **_IOFBF** или **_IOLBF**, затем *размер* используется в качестве размера буфера. Если *режим* — **_IONBF**, небуферизованный поток и *размер* и *буфера* игнорируются. Значения для *режим* и их значений:

|*режим* значение|Значение|
|-|-|
**_IOFBF**|Полная буферизация; то есть *буфера* используется в качестве буфера и *размер* используется в качестве размера буфера. Если *буфера* — **NULL**, автоматически выделенный буфер *размер* используется байт.
**_IOLBF**|В некоторых системах таким образом осуществляется линейная буферизация. Однако для Win32, поведение будет таким же, как **_IOFBF** -полная буферизация.
**_IONBF**|Буфер не используется, независимо от того, *буфера* или *размер*.

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
