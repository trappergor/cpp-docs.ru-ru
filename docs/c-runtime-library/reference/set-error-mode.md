---
title: _set_error_mode
ms.date: 11/04/2016
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
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 8c95ed45423b791a688f05ea30f48e188826a797
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502314"
---
# <a name="seterrormode"></a>_set_error_mode

Изменяет **__error_mode** для определения расположения не по умолчанию, где среда выполнения C записывает сообщение об ошибке для ошибки, которые могут вызвать завершение программы.

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

*Mode_val* параметру можно присвоить одно из следующих значений.

|Параметр|Описание|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Приемник ошибок определяется по **__app_type**.|
|**_OUT_TO_STDERR**|Приемником ошибок является стандартная ошибка.|
|**_OUT_TO_MSGBOX**|Приемником ошибок является окно сообщения.|
|**_REPORT_ERRMODE**|Сообщает текущее **__error_mode** значение.|

При передаче функции значения, отличного от перечисленных, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_set_error_mode** задает **errno** для **EINVAL** и возвращает – 1.

При использовании с [assert](assert-macro-assert-wassert.md), **_set_error_mode** отображает сбоя оператор в диалоговом окне и предоставляет возможность выбора **пропустить** кнопку, чтобы пользователь мог продолжить выполнение программы.

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
