---
title: "Интерфейс IWorkerThreadClient | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: 24
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
ms.openlocfilehash: 2127d13dc11edb353ef27396f3457dd9abdc4a99
ms.lasthandoff: 02/24/2017

---
# <a name="iworkerthreadclient-interface"></a>Интерфейс IWorkerThreadClient
`IWorkerThreadClient`Представляет интерфейс, реализуемый клиентами [CWorkerThread](../../atl/reference/cworkerthread-class.md) класса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|Реализация этого метода, чтобы закрыть дескриптор, связанный с данным объектом.|  
|[Выполнение](#execute)|Реализация этого метода для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.|  
  
## <a name="remarks"></a>Примечания  
 Реализуйте этот интерфейс, если у вас есть код, необходимый для выполнения рабочего потока в ответ на сигнал дескриптор.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Реализация этого метода, чтобы закрыть дескриптор, связанный с данным объектом.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Параметры  
 *hHandle*  
 Дескриптор будет закрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Маркер, переданный этому методу был ранее связан с этим объектом, с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities&#135;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 Реализация этого метода для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `dwParam`  
 Параметр user.  
  
 `hObject`  
 Дескриптор, который будет отправлен сигнал.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор и DWORD-указатель, передаваемый этому методу ранее были связаны с этим объектом с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities&#136;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)

