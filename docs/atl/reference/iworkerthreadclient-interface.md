---
title: "Интерфейс IWorkerThreadClient | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs: C++
helpviewer_keywords: IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cc456cd9b210a4dba9046937a8099b2db6b97470
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iworkerthreadclient-interface"></a>Интерфейс IWorkerThreadClient
`IWorkerThreadClient`Представляет интерфейс, реализуемый клиентами [CWorkerThread](../../atl/reference/cworkerthread-class.md) класса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|Реализуйте этот метод, чтобы закрыть дескриптор, связанный с данным объектом.|  
|[Выполнение](#execute)|Реализуйте этот метод для выполнения кода при сигнала дескриптор, связанный с данным объектом.|  
  
## <a name="remarks"></a>Примечания  
 Реализуйте этот интерфейс, если у вас есть код, который необходимо выполнить в рабочем потоке в ответ на сигнал дескриптор.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 Реализуйте этот метод, чтобы закрыть дескриптор, связанный с данным объектом.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Параметры  
 *hHandle*  
 Дескриптор должен быть закрыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор, переданный в этот метод был ранее связан с этим объектом, с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 Реализуйте этот метод для выполнения кода при сигнала дескриптор, связанный с данным объектом.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Параметры  
 `dwParam`  
 Параметр user.  
  
 `hObject`  
 Дескриптор, который отправлен сигнал.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор и DWORD-указатель, переданный этому методу ранее были связаны с этим объектом с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Пример  
 В следующем коде показано простая реализация `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)
