---
title: Глобальные функции точек подключения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b85da5991357f1b67c6d2249d854e6084ee48c23
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884065"
---
# <a name="connection-point-global-functions"></a>Глобальные функции точек подключения
Эти функции обеспечивают поддержку для точки подключения и к приемнику maps.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|  
|[AtlUnadvise](#atlunadvise)|Завершает подключение, установленное через `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Будет указано, или не рекомендуйте записей в картой приемника событий.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="atladvise"></a>  AtlAdvise  
 Создает связь между точкой подключения объекта и приемником клиента.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkCP*  
 [in] Указатель на `IUnknown` объекта клиент хочет подключиться с помощью.  
  
 *pUnk*  
 [in] Указатель на клиент `IUnknown`.  
  
 *IID*  
 [in] Идентификатор GUID точки подключения. Как правило это так же, как выходящего интерфейса, управляемого с использованием точки подключения.  
  
 *PDW*  
 [out] Указатель на файл cookie, который однозначно идентифицирует соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Приемник реализует исходящего интерфейса, поддерживаемого точкой подключения. Клиент использует *pdw* куки-файл, чтобы удалить соединение, передав его в [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>  AtlUnadvise  
 Завершает подключение, установленное через [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkCP*  
 [in] Указатель на `IUnknown` объекта, который клиент подключен с.  
  
 *IID*  
 [in] Идентификатор GUID точки подключения. Как правило это так же, как выходящего интерфейса, управляемого с использованием точки подключения.  
  
 *dw*  
 [in] Файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap  
 Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, содержащий карту в качестве приемника.  
  
 *bAdvise*  
 [in] Значение TRUE, если все записи в качестве приемника, которому необходимо предоставить рекомендацию; Значение FALSE, если все записи в качестве приемника должны быть негативной рекомендации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для работы с точками подключения](../../atl/reference/connection-point-macros.md)
