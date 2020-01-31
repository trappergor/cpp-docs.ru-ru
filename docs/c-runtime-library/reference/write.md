---
title: _write
ms.date: 11/04/2016
api_name:
- _write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: 5eaee64c1bf6ad4b4d59c3a7b1a1434741e74454
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821796"
---
# <a name="_write"></a>_write

Записывает данные в файл.

## <a name="syntax"></a>Синтаксис

```C
int _write(
   int fd,
   const void *buffer,
   unsigned int count
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, в который записываются данные.

*buffer*<br/>
Записываемые данные.

*count*<br/>
Число байт.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **_write** возвращает число записанных байтов. Если фактическое пространство на диске меньше, чем размер буфера, который функция пытается записать на диск, **_write** завершается сбоем и не сбрасывает содержимое буфера на диск. Возвращаемое значение, равное-1, указывает на ошибку. Если передается недопустимый параметр, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает значение-1 **, а** параметру возврата — одно из трех значений: **значение EBADF**, что означает, что дескриптор файла недействителен или файл не открыт для записи. **Еноспк**. Это означает, что на устройстве недостаточно свободного места для операции; или **еинвал**, что означает, что *буфер* был пустым указателем или что в файл в режиме Юникода было передано нечетное *число* байтов.

Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Если файл открыт в текстовом режиме, каждый символ перевода строки заменяется парой символов возврата каретки и перевода строки в выходных данных. Замена не влияет на возвращаемое значение.

Если файл открыт в режиме преобразования Юникода, например если экземпляр *демо* -приложения открыт с помощью **_open** или **_sopen** и параметра mode, который включает **_O_WTEXT**, **_O_U16TEXT**или **_O_U8TEXT**, или если он открыт с помощью **FOPEN** и параметр mode, включающий **CCS = Unicode**, **CCS = UTF-16LE**или **CCS = UTF-8**, или, если режим преобразуется в режим преобразования Юникод с помощью **_setmode**, то*буфер* интерпретируется как указатель на Массив **wchar_t** , содержащий данные **UTF-16** . Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.

## <a name="remarks"></a>Заметки

Функция **_write** записывает байты *счетчика* из *буфера* в файл, связанный с *демоном*к памяти. Операция записи начинается с текущего положения указателя файла (при наличии), связанного с данным файлом. Если файл открыт для добавления, операция начинается с текущего конца файла. После операции записи указатель файла увеличивается на число записанных байтов.

При записи в файлы, открытые в текстовом режиме, **_write** ОБРАБАТЫВАЕТ символ CTRL + Z в качестве логического конца файла. При записи на устройство **_write** ОБРАБАТЫВАЕТ символ CTRL + Z в буфере как признак конца выходных данных.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_write**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt__write.c
//
// This program opens a file for output and uses _write to write
// some bytes to the file.

#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <errno.h>
#include <share.h>

char buffer[] = "This is a test of '_write' function";

int main( void )
{
   int         fileHandle = 0;
   unsigned    bytesWritten = 0;

   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )
      return -1;

   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )
   {
      switch(errno)
      {
         case EBADF:
            perror("Bad file descriptor!");
            break;
         case ENOSPC:
            perror("No space left on device!");
            break;
         case EINVAL:
            perror("Invalid parameter: buffer was NULL!");
            break;
         default:
            // An unrelated error occurred
            perror("Unexpected error!");
      }
   }
   else
   {
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );
   }
   _close( fileHandle );
}
```

```Output
Wrote 36 bytes to file.
```

## <a name="see-also"></a>См. также:

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
