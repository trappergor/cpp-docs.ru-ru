---
title: _read
ms.date: 4/2/2020
api_name:
- _read
- _o__read
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
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: db3726b85bb4ba7c8e9a691bef3fb063ec5709c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338137"
---
# <a name="_read"></a>_read

Считывает данные из файла.

## <a name="syntax"></a>Синтаксис

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

*Буфера*<br/>
Место хранения данных.

*buffer_size*<br/>
Максимальное количество байтов для чтения.

## <a name="return-value"></a>Возвращаемое значение

**_read** возвращает количество прочитанным байтов, которое может быть меньше, чем *buffer_size,* если в файле осталось менее *buffer_size* байтов или если файл был открыт в текстовом режиме. В текстовом режиме каждая `\r\n` паровая корма `\n`возврата каретки заменяется одним символом подачи линии. В значении возврата учитывается только символ канала одной строки. Эта замена не влияет на указатель файла.

Если функция пытается прочитать конечную часть файла, она возвращает 0. Если *fd* не действителен, файл не открыт для чтения, или файл заблокирован, вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращает -1 и устанавливает **errno** в **EBADF.**

Если *буфер* **NULL,** или если *buffer_size* > **INT_MAX,** вызовуется обработчик параметров недействительного. Если выполнение разрешено продолжать, функция возвращается -1 и **errno** устанавливается в **EINVAL.**

Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_read** считывает максимум *buffer_size* байтов в *буфер* из файла, связанного с *fd.* Операция чтения начинается с текущего положения указателя файла, связанного с данным файлом. После операции чтения указатель файла указывает на следующий непрочитанный символ.

Если файл был открыт в текстовом режиме, чтение прекращается, когда **_read** сталкивается с символом CTRL, который рассматривается как индикатор конца файла. Чтобы очистить индикатор конца файла, следует использовать [_lseek](lseek-lseeki64.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_read**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crt_readtxt"></a>Входные данные: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Выходные данные

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
