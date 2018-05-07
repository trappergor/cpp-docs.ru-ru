---
title: _get_osfhandle | Документы Майкрософт
ms.custom: ''
ms.date: 12/12/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b58bbeb7c0b52950509dc8005551ad706577fcf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

Возвращает дескриптор файла операционной системы, если *fd* является допустимым. В противном случае вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **INVALID_HANDLE_VALUE** (-1) и задает **errno** для **EBADF**, указывающее, неправильный дескриптор файла.

## <a name="remarks"></a>Примечания

Чтобы закрыть файл, получаемой в результате которого дескриптор файла операционной системы (ОС) **_get_osfhandle**, вызовите [_close](close.md) на дескриптор файла *fd*. Не вызывайте **CloseHandle** для возвращаемого значения функции. Принадлежит базовый дескриптор файла операционной системы *fd* дескриптор файла, а затем закрывается, когда [_close](close.md) будет вызван на *fd*. Если владельцем дескриптора файла **ФАЙЛ \***  поток, затем вызвать [fclose](fclose-fcloseall.md) , **ФАЙЛ \***  поток закрывает дескриптор файла и базовый дескриптор файла операционной системы. В этом случае не следует вызывать [_Закрыть](close.md) на дескриптор файла.

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
