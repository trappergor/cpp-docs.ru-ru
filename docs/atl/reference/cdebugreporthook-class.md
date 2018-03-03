---
title: "Класс CDebugReportHook | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df098ee80bcd8fa81b5503cc21b08ded86945a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdebugreporthook-class"></a>Класс CDebugReportHook
Этот класс можно используйте для отправки отчетов отладки именованного канала.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Вызовы [CDebugReportHook::RemoveHook](#removehook).|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Статический) Настраиваемая функция, сообщающая, подключенное в C времени выполнения отладки процессу создания отчетов.|  
|[CDebugReportHook::RemoveHook](#removehook)|Этот метод вызывается для прекращения отправки отчетов отладки именованного канала и восстановления предыдущего обработчика отчетов.|  
|[CDebugReportHook::SetHook](#sethook)|Этот метод используется для отправки отчетов отладки в именованный канал.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Этот метод используется для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.|  
  
## <a name="remarks"></a>Примечания  
 Создайте экземпляр этого класса в отладочных построениях служб или приложений для отправки отчетов отладки именованного канала. Отладка отчеты создаются путем вызова [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) или с помощью программы-оболочки для этой функции, например [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace) и [ATLASSERT](debugging-and-error-reporting-macros.md#atlassert) макросы.  
  
 Используйте этот класс позволяет интерактивную отладку компонентов, работающих пакетном [рабочих станциях](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Обратите внимание, что отчеты отладки отправляются с помощью базового контекста безопасности потока. Олицетворение временно отключено, чтобы выполнять отладку отчетов можно просмотреть в ситуациях, олицетворение с низким уровнем прав пользователей где происходит, например, в веб-приложениях.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szMachineName`  
 Имя компьютера, на который должны отправляться выходных данных отладки. По умолчанию на локальном компьютере.  
  
 `szPipeName`  
 Имя именованного канала, к которому должны отправляться данные отладки.  
  
 `dwTimeout`  
 Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 Вызовы [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 Настраиваемая функция, сообщающая, подключенное в C времени выполнения отладки процессу создания отчетов.  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `reportType`  
 Тип отчета (_CRT_WARN, _CRT_ERROR или _CRT_ASSERT).  
  
 `message`  
 Строка сообщения.  
  
 *returnValue*  
 Значение, которое должно возвращаться [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение FALSE, если ловушка обрабатывает сообщение полностью дальнейшая выдача отчета не требуется. Возвращает значение TRUE, если `_CrtDbgReport` следует сообщать сообщение обычным способом.  
  
### <a name="remarks"></a>Примечания  
 Функция отчетов предпринимает попытку открытия именованного канала и взаимодействия с процессом на другом конце. Если канал занят, функция отчетов будет ждать свободен канала или истечения времени ожидания. Время ожидания можно задать, конструктор или вызов [CDebugReportHook::SetTimeout](#settimeout).  
  
 При выполнении примера в этой функции в базовый контекст безопасности вызывающего потока, то есть, олицетворение отключено на время выполнения этой функции.  
  
##  <a name="removehook"></a>CDebugReportHook::RemoveHook  
 Этот метод вызывается для прекращения отправки отчетов отладки именованного канала и восстановления предыдущего обработчика отчетов.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) для восстановления предыдущего обработчика отчетов.  
  
##  <a name="sethook"></a>CDebugReportHook::SetHook  
 Этот метод используется для отправки отчетов отладки в именованный канал.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) иметь отчеты отладки, маршрутизируются через [CDebugReportHookProc](#cdebugreporthookproc) к именованному каналу. Этот класс отслеживает отслеживания объекта предыдущего обработчика отчетов, чтобы он мог быть восстановлены при [RemoveHook](#removehook) вызывается.  
  
##  <a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Этот метод используется для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szMachineName`  
 Имя компьютера, на который должны отправляться выходных данных отладки.  
  
 `szPipeName`  
 Имя именованного канала, к которому должны отправляться данные отладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTimeout`  
 Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)
