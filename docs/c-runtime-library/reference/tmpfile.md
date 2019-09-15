---
title: tmpfile
ms.date: 11/04/2016
api_name:
- tmpfile
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tmpfile
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
ms.openlocfilehash: f58c23050fe89f84f283c3784a7c0cee72637bf2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957542"
---
# <a name="tmpfile"></a>tmpfile

Создает временный файл. Эта функция устарела, так как появилась более безопасная версия; см. раздел [tmpfile_s](tmpfile-s.md).

## <a name="syntax"></a>Синтаксис

```C
FILE *tmpfile( void );
```

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **tmpfile** возвращает указатель потока. В противном случае возвращается **пустой** указатель.

## <a name="remarks"></a>Примечания

Функция **tmpfile** создает временный файл и возвращает указатель на этот поток. Временный файл создается в корневом каталоге. Чтобы создать временный файл в каталоге, отличном от корневого, используйте [tmpnam_s](tempnam-wtempnam-tmpnam-wtmpnam.md) или [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](fopen-wfopen.md).

Если не удается открыть файл, **tmpfile** возвращает **пустой** указатель. Этот временный файл автоматически удаляется при закрытии файла, при завершении программы в обычном режиме или при вызове **_rmtmp** , предполагая, что текущий рабочий каталог не изменяется. Временный файл открывается в режиме **w + b** (двоичный для чтения и записи).

Сбой может произойти при попытке более TMP_MAX (см. STDIO). H) вызывает метод с **tmpfile**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**tmpfile**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

> [!NOTE]
> В этом примере требуются права администратора для работы в Windows Vista.

```C
// crt_tmpfile.c
// compile with: /W3
// This program uses tmpfile to create a
// temporary file, then deletes this file with _rmtmp.
#include <stdio.h>

int main( void )
{
   FILE *stream;
   int  i;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      if( (stream = tmpfile()) == NULL ) // C4996
      // Note: tmpfile is deprecated; consider using tmpfile_s instead
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
