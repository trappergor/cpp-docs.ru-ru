---
title: tmpfile_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tmpfile_s
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
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd7866a7135f04aa580910d5ac121311312c542
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="tmpfiles"></a>tmpfile_s

Создает временный файл. Это версия функции [tmpfile](tmpfile.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>Параметры

*pFilePtr*<br/>
Адрес указателя для хранения адреса созданного указателя на поток.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Условия ошибок

|*pFilePtr*|**Возвращаемое значение**|**Содержимое***pFilePtr* |
|----------------|----------------------|---------------------------------|
|**NULL**|**EINVAL**|не изменено|

Если возникает ошибка проверки приведенного выше параметра, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и возвращаемым значением является **EINVAL**.

## <a name="remarks"></a>Примечания

**Tmpfile_s** функция создает временный файл и помещает указатель в поток в *pFilePtr* аргумент. Временный файл создается в корневом каталоге. Чтобы создать временный файл в каталоге, отличном от корневого, используйте [tmpnam_s](tmpnam-s-wtmpnam-s.md) или [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](fopen-wfopen.md).

Если не удается открыть файл, **tmpfile_s** записывает **NULL** для *pFilePtr* параметра. Этот временный файл удаляется автоматически при закрытии файла при завершении программы в обычном режиме, или когда **_rmtmp** вызывается, при условии, что текущий рабочий каталог не изменяется. Временный файл открыт в **w + b** режиме (двоичные чтение запись).

Сбой может возникать при попытке более **TMP_MAX_S** (STDIO см. H) вызовов с **tmpfile_s**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

> [!NOTE]
> В этом примере могут потребоваться административные полномочия для запуска в Windows.

```C
// crt_tmpfile_s.c
// This program uses tmpfile_s to create a
// temporary file, then deletes this file with _rmtmp.
//

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char tempstring[] = "String to be written";
   int  i;
   errno_t err;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      err = tmpfile_s(&stream);
      if( err )
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
