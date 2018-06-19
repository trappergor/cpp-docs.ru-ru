---
title: Класс CNoWorkerThread | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85e1962d10f274f4f8c35ba27cb05c41e8bf19cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363088"
---
# <a name="cnoworkerthread-class"></a>Класс CNoWorkerThread
Этот класс используется в качестве аргумента для `MonitorClass` параметр шаблона классы кэша, если вы хотите отключить обслуживания динамического кэша.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Участники  
  
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
  
##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle  
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
  
##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer  
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
  
##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle  
 Эквивалент нефункциональные [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId  
 Эквивалент нефункциональные [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="initialize"></a>  CNoWorkerThread::Initialize  
 Эквивалент нефункциональные [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle  
 Эквивалент нефункциональные [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.  
  
##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown  
 Эквивалент нефункциональные [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Реализацию, предоставляемую этим классом не выполняет никаких действий.
