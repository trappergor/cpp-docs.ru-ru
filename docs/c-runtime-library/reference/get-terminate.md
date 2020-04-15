---
title: _get_terminate
ms.date: 4/2/2020
api_name:
- _get_terminate
- _o__get_terminate
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
- get_terminate
- _get_terminate
- __get_terminate
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
ms.openlocfilehash: fff90037851b23f3525f514aba0f6f913f9dd776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344925"
---
# <a name="_get_terminate"></a>_get_terminate

Возвращает процедуру прекращения, которая будет вызвана **завершением.**

## <a name="syntax"></a>Синтаксис

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на функцию, зарегистрированную функцией [set_terminate](set-terminate-crt.md). Если функция не установлена, значение возврата может быть использовано для восстановления поведения по умолчанию; это значение может быть **NULL**.

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[Прервать](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Прекратить](terminate-crt.md)<br/>
[Неожиданные](unexpected-crt.md)<br/>
