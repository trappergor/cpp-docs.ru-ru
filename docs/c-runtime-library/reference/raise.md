---
title: raise
ms.date: 4/2/2020
api_name:
- raise
- _o_raise
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
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: b38a3430274b2324e345be30ce9e38f0c2749fa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338266"
---
# <a name="raise"></a>raise

Отправляет сигнал выполняемой программе.

> [!NOTE]
> Не используйте этот метод для закрытия приложения Microsoft Store, за исключением сценариев тестирования или отладки. Программные или утилиты для использования не допускаются в соответствии с [правилами Microsoft Store.](/legal/windows/agreements/store-policies) Для получения дополнительной [UWP app lifecycle](/windows/uwp/launch-resume/app-lifecycle)информации см.

## <a name="syntax"></a>Синтаксис

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Параметры

*sig*<br/>
Сигнал, который требуется инициализировать.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **raise** возвращает 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Remarks

Функция **raise** отправляет сигнал *sig* выполняемой программе. Если предыдущий вызов **signal** установил функцию обработки сигнала для *sig*, **raise** выполняет эту функцию. Если функция обработчика не была установлена, то выполняется действие по умолчанию, связанное со значением сигнала *sig*, как показано ниже.

|Сигнал|Значение|Значение по умолчанию|
|------------|-------------|-------------|
|**SIGABRT**|Аварийное завершение|Завершает вызывающую программу с кодом выхода 3|
|**SIGFPE**|Ошибка с плавающей запятой|Завершает вызывающую программу|
|**SIGILL**|Недопустимая инструкция|Завершает вызывающую программу|
|**SIGINT**|Прерывание CTRL+C|Завершает вызывающую программу|
|**SIGSEGV**|Недопустимый доступ к хранилищу|Завершает вызывающую программу|
|**SIGTERM**|Запрос на прекращение, отправленный в программу|Игнорирует сигнал|

Если аргумент не является допустимым сигналом, как указано выше, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если функция не обрабатывается, функция устанавливает **errno** **к EINVAL** и возвращает ненулевое значение.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**raise**|\<signal.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Прервать](abort.md)<br/>
[Сигнал](signal.md)<br/>
