---
title: Интерфейс IWorkerThreadClient | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 545f38058871d81196150e127c1814b304b6ab56
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767859"
---
# <a name="iworkerthreadclient-interface"></a>Интерфейс IWorkerThreadClient

`IWorkerThreadClient` — Это интерфейс, реализуемый клиентами [CWorkerThread](../../atl/reference/cworkerthread-class.md) класса.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CloseHandle](#closehandle)|Реализуйте этот метод, чтобы закрыть дескриптор, связанный с данным объектом.|
|[Execute](#execute)|Реализуйте этот метод для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.|

## <a name="remarks"></a>Примечания

Реализуйте этот интерфейс, когда у вас есть код, который необходимо выполнить в рабочем потоке в ответ на сигнал дескриптор.

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

Реализуйте этот метод, чтобы закрыть дескриптор, связанный с данным объектом.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Параметры

*hHandle*  
Дескриптор будет закрыт.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха или ошибку HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Дескриптор, переданный этому методу был ранее связан с данным объектом, с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

В следующем коде показано простая реализация `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

Реализуйте этот метод для выполнения кода при оповещенным, дескриптор, связанный с данным объектом.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Параметры

*dwParam*  
Параметр user.

*hObject*  
Дескриптор, который оповещения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха или ошибку HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Дескриптор и DWORD/указатель, переданный этому методу ранее был связан с данным объектом с помощью вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

В следующем коде показано простая реализация `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>См. также

[Классы](../../atl/reference/atl-classes.md)   
[Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)
