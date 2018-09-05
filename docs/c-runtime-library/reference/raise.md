---
title: raise | Документы Майкрософт
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- raise
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
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1bc3f52b97159a9caba6f80b4798d9588ec341d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685912"
---
# <a name="raise"></a>raise

Отправляет сигнал выполняемой программе.

> [!NOTE]
> Не используйте этот метод, чтобы завершить работу в приложение Microsoft Store, за исключением сценариев тестирования или отладки. Закрытие приложения Store способов программным способом или пользовательского интерфейса не разрешены согласно [политики Microsoft Store](/legal/windows/agreements/store-policies). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle).

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

## <a name="remarks"></a>Примечания

Функция **raise** отправляет сигнал *sig* выполняемой программе. Если предыдущий вызов **signal** установил функцию обработки сигнала для *sig*, **raise** выполняет эту функцию. Если функция обработчика не была установлена, то выполняется действие по умолчанию, связанное со значением сигнала *sig*, как показано ниже.

|Signal|Значение|Значение по умолчанию|
|------------|-------------|-------------|
|**SIGABRT**|Аварийное завершение|Завершает вызывающую программу с кодом выхода 3|
|**SIGFPE**|Ошибка с плавающей запятой|Завершает вызывающую программу|
|**SIGILL**|Недопустимая инструкция|Завершает вызывающую программу|
|**SIGINT**|Прерывание CTRL+C|Завершает вызывающую программу|
|**SIGSEGV**|Недопустимый доступ к хранилищу|Завершает вызывающую программу|
|**SIGTERM**|Запрос на прекращение, отправленный в программу|Игнорирует сигнал|

Если аргумент не является допустимым сигналом, как указано выше, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если не обрабатывается, функция задает **errno** для **EINVAL** и возвращает ненулевое значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**raise**|\<signal.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
