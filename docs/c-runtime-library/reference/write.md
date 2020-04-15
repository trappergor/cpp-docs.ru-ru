---
title: _write
ms.date: 4/2/2020
api_name:
- _write
- _o__write
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
- _write
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
ms.openlocfilehash: a616df570d266c335337d897da59a2a0ec69b40e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367394"
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

*Fd*<br/>
Дескриптор файла, в который записываются данные.

*Буфера*<br/>
Записываемые данные.

*count*<br/>
Число байтов.

## <a name="return-value"></a>Возвращаемое значение

В случае **успеха, _write** возвращает количество байтов, написанных. Если фактическое пространство, оставшееся на диске, меньше размера буфера, который функция пытается написать на диск, **_write** не справляется и не промывает содержимое буфера на диск. Значение возврата -1 указывает на ошибку. Если передается недопустимый параметр, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функция возвращается -1 и **errno** устанавливается на одно из трех значений: **EBADF**, что означает, что дескриптор файла недействителен или файл не открыт для записи; **ENOSPC**, что означает, что на устройстве не осталось достаточно места для операции; или **EINVAL**, что означает, что *буфер* был нулевой указатель или что нечетные *количество* байтов был передан для записи в файл в режиме Unicode.

Для получения дополнительной информации об этих и других кодах возврата [_sys_nerr _sys_errlist _doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)см.

Если файл открыт в текстовом режиме, символ корма каждой строки заменяется парой кормов возврата каретной линии на выходе. Замена не влияет на значение возврата.

Например, при открытии файла в режиме перевода Unicode если *fd* открывается с помощью **_open** или **_sopen** и параметра режима, который включает в себя **_O_WTEXT,** **_O_U16TEXT**или **_O_U8TEXT,** или если он открыт с помощью **fopen** и параметра режима, который включает в себя **ccs'UNICODE**, **ccs'UTF-16LE**, или **ccs'UTF-8**, или если режим изменен на режим перевода Unicode с помощью **_setmode**-*буфер* интерпретируется как точечный к массиву **wchar_t,** который **содержит.** Попытка записи нечетного числа байт в этом режиме приводит к возникновению ошибки проверки параметра.

## <a name="remarks"></a>Remarks

Функция **_write** записывает *подсчет* байтов из *буфера* в файл, связанный с *fd.* Операция записи начинается с текущего положения указателя файла (при наличии), связанного с данным файлом. Если файл открыт для добавления, операция начинается с текущего конца файла. После операции записи указатель файла увеличивается на количество написанных байтов.

При написании файлов, открытых в текстовом режиме, **_write** рассматривает символ CTRL как логический конец файла. При записи на устройство **_write** рассматривает символ CTRL- в буфере как терминатор вывода.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_write**|\<io.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_setmode](setmode.md)<br/>
