---
title: Класс CDebugReportHook | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb0bf24657a47cbe1cf1129f0202d120fb1d017e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039068"
---
# <a name="cdebugreporthook-class"></a>Класс CDebugReportHook

Этот класс используется для отправки отчетов отладки именованного канала.

## <a name="syntax"></a>Синтаксис

```
class CDebugReportHook
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).|
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Вызовы [CDebugReportHook::RemoveHook](#removehook).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Статический) Настраиваемая функция, сообщающая, подключенное в отладку времени выполнения C, процедуры составления отчетности.|
|[CDebugReportHook::RemoveHook](#removehook)|Вызовите этот метод, чтобы остановить отправку отчетов отладки к именованному каналу и восстановить предыдущие отчетные.|
|[CDebugReportHook::SetHook](#sethook)|Вызовите этот метод, с которого начинается отправка отчетов отладки к именованному каналу.|
|[CDebugReportHook::SetPipeName](#setpipename)|Вызовите этот метод для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.|
|[CDebugReportHook::SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.|

## <a name="remarks"></a>Примечания

Создайте экземпляр этого класса в отладочных сборках, служб и приложений для отправки отчетов отладки именованного канала. Отладка отчеты создаются путем вызова [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) или с помощью оболочки для этой функции, например [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) и [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) макросы.

Используйте данный класс позволяет осуществлять интерактивную отладку компонентов, работающих в пакетном [рабочих станциях](/windows/desktop/winstation/window-stations).

Обратите внимание на то, что выполнять отладку отчетов отправляются с помощью базового контекст безопасности потока. Олицетворение временно отключено, чтобы выполнять отладку отчетов, которые можно просмотреть в ситуациях, где олицетворения пользователей с низким уровнем привилегий выполняется, например, в веб-приложениях.

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook

Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>Параметры

*szMachineName*<br/>
Имя компьютера, на который будут отправляться данные отладки. По умолчанию на локальном компьютере.

*szPipeName*<br/>
Имя именованного канала, к которому следует отправлять выходные данные отладки.

*dwTimeout*<br/>
Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.

##  <a name="dtor"></a>  CDebugReportHook:: ~ CDebugReportHook

Вызовы [CDebugReportHook::RemoveHook](#removehook).

```
~CDebugReportHook() throw();
```

##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc

Настраиваемая функция, сообщающая, подключенное в отладку времени выполнения C, процедуры составления отчетности.

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета (_CRT_WARN, _CRT_ERROR или _CRT_ASSERT).

*message*<br/>
Строка сообщения.

*returnValue*<br/>
Значение, которое должен вернуть [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение FALSE, если ловушка обрабатывает сообщение полностью дальнейшая выдача отчета не требуется. Возвращает значение TRUE, если `_CrtDbgReport` сообщите сообщение обычным способом.

### <a name="remarks"></a>Примечания

Функция отчетов попытки открытия именованного канала и взаимодействия с процессом на другом конце. Если канал занят, функция отчетов будет ждать бесплатна канала или истечения времени ожидания. Время ожидания можно задать, конструктор или вызов [CDebugReportHook::SetTimeout](#settimeout).

При выполнении примера в этой функции в базовый контекст безопасности вызывающего потока, то есть олицетворение отключено в течение этой функции.

##  <a name="removehook"></a>  CDebugReportHook::RemoveHook

Вызовите этот метод, чтобы остановить отправку отчетов отладки к именованному каналу и восстановить предыдущие отчетные.

```
void RemoveHook() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) для восстановления предыдущего обработчика отчетов.

##  <a name="sethook"></a>  CDebugReportHook::SetHook

Вызовите этот метод, с которого начинается отправка отчетов отладки к именованному каналу.

```
void SetHook() throw();
```

### <a name="remarks"></a>Примечания

Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) требуется выполнять отладку отчетов через [CDebugReportHookProc](#cdebugreporthookproc) к именованному каналу. Этот класс отслеживает этой предыдущие отчетные, это могут быть восстановлены при [RemoveHook](#removehook) вызывается.

##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName

Вызовите этот метод для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>Параметры

*szMachineName*<br/>
Имя компьютера, на который будут отправляться данные отладки.

*szPipeName*<br/>
Имя именованного канала, к которому следует отправлять выходные данные отладки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout

Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.

```
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>Параметры

*dwTimeout*<br/>
Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.

## <a name="see-also"></a>См. также

[Классы](../../atl/reference/atl-classes.md)
