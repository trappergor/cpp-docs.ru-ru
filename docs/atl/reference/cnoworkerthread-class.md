---
title: "Класс CNoWorkerThread | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CNoWorkerThread
- ATL.CNoWorkerThread
- CNoWorkerThread
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
caps.latest.revision: 21
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
ms.openlocfilehash: 4c38d778849a31d55a657fc1022c2e9f4a370eec
ms.lasthandoff: 02/24/2017

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
|[CNoWorkerThread::AddHandle](#addhandle)|Нефункциональные эквивалент [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Нефункциональные эквивалент [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Нефункциональные эквивалент [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Нефункциональные эквивалент [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Нефункциональные эквивалент [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Нефункциональные эквивалент [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Нефункциональные эквивалент [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет тот же открытый интерфейс как [CWorkerThread](../../atl/reference/cworkerthread-class.md). Этот интерфейс должен предоставляться `MonitorClass` параметр шаблона классов кэша.  
  
 Чтобы ничего не реализуются методы в этом классе. Методы, которые возвращают значение HRESULT, всегда возвращают S_OK, и методы, которые возвращают идентификатор ДЕСКРИПТОРА или поток всегда возвращают значение 0.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="a-nameaddhandlea--cnoworkerthreadaddhandle"></a><a name="addhandle"></a>CNoWorkerThread::AddHandle  
 Нефункциональные эквивалент [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
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
  
##  <a name="a-nameaddtimera--cnoworkerthreadaddtimer"></a><a name="addtimer"></a>CNoWorkerThread::AddTimer  
 Нефункциональные эквивалент [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
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
  
##  <a name="a-namegetthreadhandlea--cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 Нефункциональные эквивалент [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="a-namegetthreadida--cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 Нефункциональные эквивалент [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="a-nameinitializea--cnoworkerthreadinitialize"></a><a name="initialize"></a>CNoWorkerThread::Initialize  
 Нефункциональные эквивалент [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="a-nameremovehandlea--cnoworkerthreadremovehandle"></a><a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 Нефункциональные эквивалент [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="a-nameshutdowna--cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoWorkerThread::Shutdown  
 Нефункциональные эквивалент [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.

