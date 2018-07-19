---
title: fgetpos | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b111a911083354c8d9478b2c914a0a5f7dfe7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397389"
---
# <a name="fgetpos"></a>fgetpos

Получает индикатор позиции файла потока.

## <a name="syntax"></a>Синтаксис

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Целевой поток.

*POS*<br/>
Хранилище индикатора позиции.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **fgetpos** возвращает 0. В случае сбоя он возвращает ненулевое значение и задает **errno** к одному из следующих манифеста констант (определенных в STDIO. H): **EBADF**, то есть указанного потока не является допустимым файлом указателем или недоступен, или **EINVAL**, означающее, что *поток* значение или значение *pos* является недопустимым, например, если либо является пустым указателем. Если *поток* или *pos* — **NULL** указателем, функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Примечания

**Fgetpos** функция возвращает текущее значение *поток* указателя позиции файла и сохраняет его в объект, на который указывает аргумент *pos*. **Fsetpos** функция позже может использовать данные, хранящиеся в *pos* Сброс *поток* аргумента указатель на ее положение во время **fgetpos** был вызван. *Pos* значение хранится во внутреннем формате и предназначен для использования только в выпуске **fgetpos** и **fsetpos**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>Входные данные: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>Выходные данные: crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
