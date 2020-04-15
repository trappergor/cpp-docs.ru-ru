---
title: fgetpos
ms.date: 4/2/2020
api_name:
- fgetpos
- _o_fgetpos
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fgetpos
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: 0c16150a6240068e1453ec90b396c87ab9ece5a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346912"
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

*pos*<br/>
Хранилище индикатора позиции.

## <a name="return-value"></a>Возвращаемое значение

В случае **успеха, fgetpos** возвращает 0. При сбое он возвращает ненулевое значение и устанавливает **errno** к одной из следующих констант манифеста (определяется в STDIO. H): **EBADF**, что означает, что указанный поток не является действительным указателем файла или не доступен, или **EINVAL**, что означает значение *потока* или значение *pos* является недействительным, например, если либо является нулевым указателем. Если *поток* или *pos* является указателем **NULL,** функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md)

## <a name="remarks"></a>Remarks

Функция **fgetpos** получает текущее значение индикатора файловой позиции *аргумента потока* и хранит его в объекте, на который указывает *pos.* Функция **fsetpos** может позже использовать информацию, хранящуюся в *pos,* чтобы сбросить указатель аргумента *потока* в свое положение во время **вызова fgetpos.** Значение *pos* хранится во внутреннем формате и предназначено для использования только **fgetpos** и **fsetpos.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="input-crt_fgetpostxt"></a>Входные данные: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crt_fgetpostxt"></a>Выходные данные: crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
