---
title: _pclose
ms.date: 11/04/2016
apiname:
- _pclose
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
- _pclose
- pclose
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
ms.openlocfilehash: eb0f54ec27992cd0e62b11d8fec5bd54c3daea4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507722"
---
# <a name="pclose"></a>_pclose

Ожидает новый обработчик команд и закрывает поток по связанному каналу.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Значение, возвращаемое из предыдущего вызова **_popen**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает состояние завершения завершающего обработчика команд или значение -1, если произошла ошибка. Формат возвращаемого значения совпадает со значением, для **_cwait**, за исключением, что байты низкого и высокого порядка меняются местами. Если поток имеет **NULL**, **_pclose** задает **errno** для **EINVAL** и возвращает – 1.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Pclose** функция ищет идентификатор процесса интерпретатор командной строки (Cmd.exe), запущенного связанным **_popen** вызова, выполняет [_cwait](cwait.md) вызвать для новой команды Процессор и закрывает поток по связанному каналу.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_pclose**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
