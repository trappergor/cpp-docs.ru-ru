---
title: _get_osfhandle
ms.date: 05/29/2018
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: cc3b50e3d3f65bee83b8df83aa0adb5c8694e35a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821656"
---
# <a name="getosfhandle"></a>_get_osfhandle

Получает дескриптор файла операционной системы, связанный с указанным дескриптором файла.

## <a name="syntax"></a>Синтаксис

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор существующего файла.

## <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор файла операционной системы, если *fd* является допустимым. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, он возвращает **INVALID_HANDLE_VALUE** (-1). Он также задает **errno** для **значение EBADF**, указывающее, дескриптор файла является недопустимым. Чтобы избежать предупреждения, когда результат используется как дескриптор файла Win32, приведите его к **ОБРАБАТЫВАТЬ** типа.

> [!NOTE]
> Когда **stdin**, **stdout**, и **stderr** не связанную с потоком (например, в приложении Windows без окна консоли) значения дескриптора файла Эти потоки возвращаются из [_fileno](fileno.md) как специальное значение -2. Аналогично Если вы используете 0, 1 или 2 в качестве параметра дескриптор файла, вместо результата вызова **_fileno**, **_get_osfhandle** также возвращает специальное значение -2, если дескриптор файла не связана с помощью потока и не устанавливает **errno**. Тем не менее это значение не является допустимым файлом дескриптор, и последующие вызовы, которые пытаются использовать его, скорее всего, переход на другой.

Дополнительные сведения о **значение EBADF** и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Чтобы закрыть файл, дескриптор файла операционной системы (ОС) которого получается путем **_get_osfhandle**, вызовите [_close](close.md) на дескриптор файла *fd*. Никогда не вызовет **CloseHandle** для возвращаемого значения функции. Принадлежит базовый дескриптор файла операционной системы *fd* дескриптор файла и закрывается, когда [_close](close.md) вызывается для *fd*. Если владельцем дескриптора файла `FILE *` потока, затем вызвать [fclose](fclose-fcloseall.md) об этом `FILE *` поток закрывает дескриптор файла и базовый дескриптор файла операционной системы. В этом случае не вызывайте [_close](close.md) на дескриптор файла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
