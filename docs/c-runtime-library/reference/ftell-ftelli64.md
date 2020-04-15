---
title: ftell, _ftelli64
ms.date: 4/2/2020
api_name:
- _ftelli64
- ftell
- _o__ftelli64
- _o_ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: bfe79610161a7f4032517d9f7eaa0de50be18e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345614"
---
# <a name="ftell-_ftelli64"></a>ftell, _ftelli64

Получает текущее положение указателя файла.

## <a name="syntax"></a>Синтаксис

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Целевая структура **FILE.**

## <a name="return-value"></a>Возвращаемое значение

**ftell** и **_ftelli64** вернуть текущее положение файла. Значение, возвращенное **ftell** и **_ftelli64** может не отражать физическое смещение байт для потоков, открытых в текстовом режиме, потому что текстовый режим вызывает перевод канала возврата. Используйте **ftell** с [fseek](fseek-fseeki64.md) или **_ftelli64** с [_fseeki64,](fseek-fseeki64.md) чтобы вернуться к файлу местах правильно. По ошибке **ftell** и **_ftelli64** ссылаются на недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции возвращают -1L и устанавливают **errno** в одну из двух констант, определяемую в ERRNO. H. **Постоянная eBADF** означает, что аргумент *потока* не является действительным значением указателя файла или не относится к открытому файлу. **EINVAL** означает, что недействительный аргумент *потока* был передан функции. На устройствах, неспособных к поиску (например, терминалы и принтеры) или когда *поток* не относится к открытому файлу, значение возврата не определено.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

**Функции ftell** и **_ftelli64** извлекают текущее положение указателя файла (если таковые имеется), связанные с *потоком.* Позиция представляется как смещение относительно начала потока.

Обратите внимание, что когда файл открыт для добавления данных, текущее положение в файле определяется последней операцией ввода-вывода, а не тем, где должна быть произведена следующая запись. Например, если файл открыт для добавления и последней операцией было чтение, положением в файле является место, где должна начинаться следующая операция чтения, а не следующая операция записи. (Когда файл открыт для приложения, позиция файла перемещается в конец файла до операции записи.) Если в файле, открытом для приложения, еще не произошло операции ввоза/ввоза, позиция файла — это начало файла.

В текстовом режиме при вводе CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения/письма, **fopen** и всех связанных с ними подпрограмм проверяют CTRL в конце файла и удаляют его, если это возможно. Это делается потому, что с помощью комбинации **ftell** и [fseek](fseek-fseeki64.md) или **_ftelli64** и [_fseeki64,](fseek-fseeki64.md)чтобы переместиться в файл, который заканчивается с CTRL, может привести к **ftell** или **_ftelli64** вести себя ненадлежащим образом ближе к концу файла.

Во время выполнения функция блокирует вызывающий поток, поэтому она потокобезопасна. Для неблокирующей версии см. **_ftell_nolock**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательные заголовки|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
