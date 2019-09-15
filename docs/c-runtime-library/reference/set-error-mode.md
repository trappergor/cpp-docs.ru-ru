---
title: _set_error_mode
ms.date: 11/04/2016
api_name:
- _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 15a6d72a79f0498fb7d81094ed3595dea1cf444f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948567"
---
# <a name="_set_error_mode"></a>_set_error_mode

Изменяет **__error_mode** , чтобы определить расположение, отличное от используемого по умолчанию, когда среда выполнения C записывает сообщение об ошибке для ошибки, которая может завершить программу.

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

Управляет приемником вывода ошибок, устанавливая значение **__error_mode**. Например, можно направить вывод в стандартную ошибку или использовать API **MessageBox** .

Параметру *mode_val* может быть присвоено одно из следующих значений.

|Параметр|Описание|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Приемник ошибки определяется **__app_type**.|
|**_OUT_TO_STDERR**|Приемником ошибок является стандартная ошибка.|
|**_OUT_TO_MSGBOX**|Приемником ошибок является окно сообщения.|
|**_REPORT_ERRMODE**|Сообщает текущее значение **__error_mode** .|

При передаче функции значения, отличного от перечисленных, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено , _Set_error_mode **устанавливает** **еинвал** и возвращает-1.

При использовании с [Assert](assert-macro-assert-wassert.md) **_set_error_mode** отображает оператор Failed в диалоговом окне и дает возможность нажать кнопку **пропустить** , чтобы можно было продолжить выполнение программы.

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
