---
title: _putch_nolock, _putwch_nolock
ms.date: 4/2/2020
api_name:
- _putwch_nolock
- _putch_nolock
- _o__putch_nolock
- _o__putwch_nolock
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
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putch_nolock
- _puttch_nolock
- putch_nolock
- putwch_nolock
- _putwch_nolock
helpviewer_keywords:
- putwch_nolock function
- puttch_nolock function
- characters, writing
- putch_nolock function
- _putch_nolock function
- _puttch_nolock function
- console, writing characters to
- _putwch_nolock function
ms.assetid: edbc811d-bac6-47fa-a872-fe4f3a1590b0
ms.openlocfilehash: 16f01e626f72269286cda045615665152361a887
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338442"
---
# <a name="_putch_nolock-_putwch_nolock"></a>_putch_nolock, _putwch_nolock

Записывает символ в консоль без блокировки потока.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _putch_nolock(
int c
);
wint_t _putwch_nolock(
wchar_t c
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Символ, который требуется вывести.

## <a name="return-value"></a>Возвращаемое значение

Возвращает значение *c* в случае успешного выполнения. Если функция **_putch_nolock** завершается с ошибкой, она возвращает значение **EOF**; если функция **_putwch_nolock** завершается с ошибкой, она возвращает значение **WEOF**.

## <a name="remarks"></a>Remarks

Версии **_putch_nolock** и **_putwch_nolock** идентичны версиям **_putch** и **_putwch** соответственно, за исключением того, что они не защищены от помех со стороны других потоков. Они могут выполняться быстрее, поскольку не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttch_nolock**|**_putch_nolock**|**_putch_nolock**|**_putwch_nolock**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_putch_nolock**|\<conio.h>|
|**_putwch_nolock**|\<conio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Консоль и порт I/O](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
