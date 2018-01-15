---
title: "raise | Документы Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: raise
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
f1_keywords: Raise
dev_langs: C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b7ec6c886c96bae93f511e54119500d58d6fea5
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="raise"></a>raise

Отправляет сигнал выполняемой программе.

> [!NOTE]
> Не используйте этот метод, чтобы завершить работу приложения магазина Microsoft, за исключением сценариев тестирования или отладки. Программный или пользовательского интерфейса способов закрыть приложение магазина, не разрешено согласно [банка политики](http://go.microsoft.com/fwlink/?LinkId=865936). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Синтаксис

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Параметры

*sig*  
Сигнал, который требуется инициализировать.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **raise** возвращает 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

Функция **raise** отправляет сигнал *sig* выполняемой программе. Если предыдущий вызов **signal** установил функцию обработки сигнала для *sig*, **raise** выполняет эту функцию. Если функция обработчика не была установлена, то выполняется действие по умолчанию, связанное со значением сигнала *sig*, как показано ниже.

|Signal|Значение|По умолчанию|
|------------|-------------|-------------|
|`SIGABRT`|Аварийное завершение|Завершает вызывающую программу с кодом выхода 3|
|`SIGFPE`|Ошибка с плавающей запятой|Завершает вызывающую программу|
|`SIGILL`|Недопустимая инструкция|Завершает вызывающую программу|
|`SIGINT`|Прерывание CTRL+C|Завершает вызывающую программу|
|`SIGSEGV`|Недопустимый класс хранения|Завершает вызывающую программу|
|`SIGTERM`|Запрос на прекращение, отправленный в программу|Игнорирует сигнал|

Если аргумент не является допустимым сигналом, как указано выше, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка не обработана, функция задает для параметра `errno` значение `EINVAL` и возвращает ненулевое значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**raise**|\<signal.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[signal](../../c-runtime-library/reference/signal.md)  
