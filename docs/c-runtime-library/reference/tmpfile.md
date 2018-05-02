---
title: tmpfile | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- tmpfile
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
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d808b26341ea862965dc33c4c3b3b00ff06f2c6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="tmpfile"></a>tmpfile

Создает временный файл. Эта функция устарела, так как появилась более безопасная версия; см. раздел [tmpfile_s](tmpfile-s.md).

## <a name="syntax"></a>Синтаксис

```C
FILE *tmpfile( void );
```

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **tmpfile** возвращает указатель на поток. В противном случае он возвращает **NULL** указателя.

## <a name="remarks"></a>Примечания

**Tmpfile** функция создает временный файл и возвращает указатель в поток. Временный файл создается в корневом каталоге. Чтобы создать временный файл в каталоге, отличном от корневого, используйте [tmpnam_s](tempnam-wtempnam-tmpnam-wtmpnam.md) или [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](fopen-wfopen.md).

Если не удается открыть файл, **tmpfile** возвращает **NULL** указателя. Этот временный файл удаляется автоматически при закрытии файла при завершении программы в обычном режиме, или когда **_rmtmp** вызывается, при условии, что текущий рабочий каталог не изменяется. Временный файл открыт в **w + b** режиме (двоичные чтение запись).

Сбой может возникать при попытке более чем TMP_MAX (STDIO см. H) вызовов с **tmpfile**.

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
