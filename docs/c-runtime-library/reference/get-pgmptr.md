---
title: _get_pgmptr
ms.date: 4/2/2020
api_name:
- _get_pgmptr
- _o__get_pgmptr
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: efcac6a64c01bee38a3753bdec378dae625db35e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345024"
---
# <a name="_get_pgmptr"></a>_get_pgmptr

Получает текущее значение **_pgmptr** глобальной переменной.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на строку, которая должна быть заполнена текущим значением **переменной _pgmptr.**

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если *pValue* является **NULL,** то недействительный обработчик параметров вызывается, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Remarks

Позвоните **_get_pgmptr** только если ваша программа имеет узкую точку входа, как **основной ()** или **WinMain ()**. **Глобальная** переменная _pgmptr содержит полный путь к исполняемому процессу. Дополнительные сведения см. в разделе [_pgmptr _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_get_wpgmptr](get-wpgmptr.md)<br/>
