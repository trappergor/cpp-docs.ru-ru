---
title: "Глобальные функции для точки подключения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce7f6fc3d2a0b51f88952dd720955367b1dfe9d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="connection-point-global-functions"></a>Глобальные функции для точки подключения
Эти функции обеспечивают поддержку для точки подключения и приемника карты.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|  
|[AtlUnadvise](#atlunadvise)|Завершает подключение, установленное с помощью `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Будет указано, или unadvises записей в схеме событий приемника.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
   
##  <a name="atladvise"></a>AtlAdvise  
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
 `pUnkCP`  
 [in] Указатель на **IUnknown** объекта клиент хочет подключиться с.  
  
 *pUnk*  
 [in] Указатель на клиент **IUnknown**.  
  
 `iid`  
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с помощью точки подключения.  
  
 `pdw`  
 [out] Указатель на файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Приемник реализует исходящего интерфейса, поддерживаемого точкой подключения. Клиент использует `pdw` куки-файл для удаления соединения путем ее передачи [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>AtlUnadvise  
 Завершает подключение, установленное с помощью [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkCP`  
 [in] Указатель на **IUnknown** объекта, связанный с клиентом.  
  
 `iid`  
 [in] Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с помощью точки подключения.  
  
 `dw`  
 [in] Файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, содержащий приемником сопоставления.  
  
 `bAdvise`  
 [in] **true** Если все записи приемника должны быть проигнорирована; **false** Если все операции приемников должны быть unadvised.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)   
 [Макросы для работы с точками подключения](../../atl/reference/connection-point-macros.md)
