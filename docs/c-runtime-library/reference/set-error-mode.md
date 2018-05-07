---
title: _set_error_mode | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
dev_langs:
- C++
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 130e9fee13401c8b598a5d6eef7d1fab3ed80ae9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="seterrormode"></a>_set_error_mode

Изменяет **__error_mode** для определения местоположения не по умолчанию, где среда выполнения C записывает сообщение об ошибке для ошибки, которые могут вызвать завершение программы.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>Параметры

*mode_val*<br/>
Назначение сообщений об ошибках.

## <a name="return-value"></a>Возвращаемое значение

Возвращает старое значение или -1, если возникла ошибка.

## <a name="remarks"></a>Примечания

Управляет приемником потока ошибок, задав значение **__error_mode**. Например, можно направить вывод в стандартную ошибку или использовать **MessageBox** API.

*Mode_val* параметра может быть присвоено одно из следующих значений.

|Параметр|Описание|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Приемник ошибок определяется **__app_type**.|
|**_OUT_TO_STDERR**|Приемником ошибок является стандартная ошибка.|
|**_OUT_TO_MSGBOX**|Приемником ошибок является окно сообщения.|
|**_REPORT_ERRMODE**|Сообщает текущее **__error_mode** значение.|

При передаче функции значения, отличного от перечисленных, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_set_error_mode** задает **errno** для **EINVAL** и возвращает значение -1.

При использовании с [assert](assert-macro-assert-wassert.md), **_set_error_mode** выводит инструкцию сбоя в диалоговом окне и предоставляет возможность выбора **Ignore** кнопку, чтобы пользователь мог продолжить выполнение программы.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h>|

## <a name="example"></a>Пример

```C
// crt_set_error_mode.c
// compile with: /c
#include <stdlib.h>
#include <assert.h>

int main()
{
   _set_error_mode(_OUT_TO_STDERR);
   assert(2+2==5);
}
```

```Output
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>См. также

[Макрос assert, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
