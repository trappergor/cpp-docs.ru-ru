---
title: "Класс CDebugReportHook | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDebugReportHook
- CDebugReportHook
- ATL::CDebugReportHook
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 632167d4f78ef930673450d6d087f32e91b6541f
ms.lasthandoff: 02/24/2017

---
# <a name="cdebugreporthook-class"></a>Класс CDebugReportHook
Этот класс используется для отправки отчетов отладки именованного канала.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|Вызовы [CDebugReportHook::RemoveHook](#removehook).|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Статический) Пользовательскую функцию отчетов, подключенное к отладочному во время выполнения процедуры составления отчетности.|  
|[CDebugReportHook::RemoveHook](#removehook)|Этот метод вызывается для прекращения отправки отчетов отладки именованного канала и восстановление предыдущего обработчика отчетов.|  
|[CDebugReportHook::SetHook](#sethook)|Вызовите этот метод, чтобы запустить отправку отчетов отладки именованного канала.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Этот метод используется для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.|  
  
## <a name="remarks"></a>Примечания  
 Создайте экземпляр этого класса в отладочных построениях, служб или приложений для отправки отчетов отладки именованного канала. Отладка отчеты создаются путем вызова [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) или с помощью оболочки для этой функции, например [ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e) и [ATLASSERT](http://msdn.microsoft.com/library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) макросы.  
  
 Использование этого класса можно в интерактивном режиме отлаживать компоненты, работающие в неинтерактивном [рабочих станциях](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Обратите внимание, что отладки отчеты отправляются с помощью базового контекст безопасности потока. Олицетворение временно отключена, отчетов отладки можно просматривать в ситуациях, где олицетворения пользователей с низким уровнем привилегий имеют место, например, в веб-приложениях.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="a-namecdebugreporthooka--cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 Вызовы [SetPipeName](#setpipename), [SetTimeout](#settimeout), и [SetHook](#sethook).  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szMachineName`  
 Имя компьютера, на который должны отправляться выходные данные отладки. По умолчанию используется локальный компьютер.  
  
 `szPipeName`  
 Имя именованного канала, на который должны отправляться выходные данные отладки.  
  
 `dwTimeout`  
 Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
##  <a name="a-namedtora--cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 Вызовы [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="a-namecdebugreporthookproca--cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 Пользовательскую функцию отчетов, подключенное к отладочному во время выполнения процедуры составления отчетности.  
  
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
  
 *Возвращаемое значение*  
 Значение, которое должно возвращаться функцией [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение FALSE, если ловушка обрабатывает сообщение полностью дальнейшая выдача отчета не требуется. Возвращает значение TRUE, если `_CrtDbgReport` следует отправлять сообщение обычным образом.  
  
### <a name="remarks"></a>Примечания  
 Функция отчетов предпринимает попытку открытия именованного канала и взаимодействия с процессом на другом конце. Если канал занят, функция отчетов будет ждать канала является бесплатным или истечения времени ожидания. Время ожидания можно задать, конструктор или вызов [CDebugReportHook::SetTimeout](#settimeout).  
  
 При выполнении примера в этой функции в базовый контекст безопасности вызывающего потока, то есть, олицетворение отключено в течение этой функции.  
  
##  <a name="a-nameremovehooka--cdebugreporthookremovehook"></a><a name="removehook"></a>CDebugReportHook::RemoveHook  
 Этот метод вызывается для прекращения отправки отчетов отладки именованного канала и восстановление предыдущего обработчика отчетов.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) для восстановления предыдущего обработчика отчетов.  
  
##  <a name="a-namesethooka--cdebugreporthooksethook"></a><a name="sethook"></a>CDebugReportHook::SetHook  
 Вызовите этот метод, чтобы запустить отправку отчетов отладки именованного канала.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) иметь отчетов отладки, проходят через [CDebugReportHookProc](#cdebugreporthookproc) к именованному каналу. Этот класс данные о предыдущем обработчика отчетов, чтобы его можно было восстановить при [RemoveHook](#removehook) вызывается.  
  
##  <a name="a-namesetpipenamea--cdebugreporthooksetpipename"></a><a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Этот метод используется для установки на компьютер и имя канала, к которому будут отправляться отчеты отладки.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szMachineName`  
 Имя компьютера, на который должны отправляться выходные данные отладки.  
  
 `szPipeName`  
 Имя именованного канала, на который должны отправляться выходные данные отладки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesettimeouta--cdebugreporthooksettimeout"></a><a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Вызовите этот метод, чтобы задать время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTimeout`  
 Время в миллисекундах, что этот класс будет ожидать именованного канала станет доступным.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)

