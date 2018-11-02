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
ms.openlocfilehash: beab4e4308bc7bcde287366b78671f61a89f8827
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504537"
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

Возвращает дескриптор файла операционной системы, если *fd* является допустимым. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **INVALID_HANDLE_VALUE** (-1) и задает **errno** для **значение EBADF**, указывающее, дескриптор файла является недопустимым. Чтобы предотвратить появление предупреждения компилятора, когда результат используется в подпрограммы, которые ожидают дескриптор файла Win32, приведите его к **ОБРАБАТЫВАТЬ** типа.

## <a name="remarks"></a>Примечания

Чтобы закрыть файл, дескриптор файла операционной системы (ОС) которого получается путем **_get_osfhandle**, вызовите [_close](close.md) на дескриптор файла *fd*. Не вызывайте **CloseHandle** для возвращаемого значения функции. Принадлежит базовый дескриптор файла операционной системы *fd* дескриптор файла и закрывается, когда [_close](close.md) вызывается для *fd*. Если владельцем дескриптора файла `FILE *` потока, затем вызвать [fclose](fclose-fcloseall.md) об этом `FILE *` поток закрывает дескриптор файла и базовый дескриптор файла операционной системы. В этом случае не следует вызывать [_close](close.md) на дескриптор файла.

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
