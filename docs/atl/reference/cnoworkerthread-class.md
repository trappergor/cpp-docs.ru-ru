---
title: "Класс CNoWorkerThread | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 9d5722ece0c85c07445f22d93e4840b9188b246c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cnoworkerthread-class"></a>Класс CNoWorkerThread
Этот класс используется в качестве аргумента для `MonitorClass` параметр шаблона классы кэша, если вы хотите отключить обслуживания динамического кэша.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|Эквивалент нефункциональные [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Эквивалент нефункциональные [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Эквивалент нефункциональные [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Эквивалент нефункциональные [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Эквивалент нефункциональные [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Эквивалент нефункциональные [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Эквивалент нефункциональные [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет тот же открытый интерфейс, как [CWorkerThread](../../atl/reference/cworkerthread-class.md). Этот интерфейс должен предоставляться `MonitorClass` параметр шаблона классам кэше.  
  
 Методы в этом классе реализованы для не выполняют никаких действий. Методы, которые возвращают значение HRESULT всегда возвращают S_OK и методы, которые возвращают идентификатор ДЕСКРИПТОРА или поток всегда возвращает значение 0.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="addhandle"></a>CNoWorkerThread::AddHandle  
 Эквивалент нефункциональные [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="addtimer"></a>CNoWorkerThread::AddTimer  
 Эквивалент нефункциональные [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 Эквивалент нефункциональные [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 Эквивалент нефункциональные [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="initialize"></a>CNoWorkerThread::Initialize  
 Эквивалент нефункциональные [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 Эквивалент нефункциональные [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="shutdown"></a>CNoWorkerThread::Shutdown  
 Эквивалент нефункциональные [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.

