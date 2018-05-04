---
title: Макросы точки подключения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e50a868dd87628873b2a43f0ace55690b0583fd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="connection-point-macros"></a>Макросы точки подключения
Эти макросы определяют схемы точки подключения и записи.  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Отмечает начало карты записей точки подключения.|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Вводит карты точки подключения.|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017 г.) Аналогично CONNECTION_POINT_ENTRY, но принимает указатель на iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Отмечает конец записей карты точки подключения.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h 
   
##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP  
 Отмечает начало карты записей точки подключения.  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса, содержащего точки подключения.  
  
### <a name="remarks"></a>Примечания  
 Запуск на сопоставление точки подключения с `BEGIN_CONNECTION_POINT_MAP` макрос, добавьте записи для каждой из точек соединения с [CONNECTION_POINT_ENTRY](#connection_point_entry) макрос и выполнить сопоставление с [END_CONNECTION_POINT_MAP](#end_connection_point_map) макрос.  
  
 Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY и CONNECTION_POINT_ENTRY_P  
 Вводит точку подключения в сопоставление точки подключения, чтобы он был доступен для указанного интерфейса.  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, добавляется сопоставление точки подключения. 
 
 `piid`  
 [in] Указатель на идентификатор GUID интерфейса, который добавляет.   
  
### <a name="remarks"></a>Примечания  
 Записи точки соединения в схеме используются [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Класс, содержащий сопоставление точки подключения должен наследовать от `IConnectionPointContainerImpl`.  
  
 Запуск на сопоставление точки подключения с [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) макрос, добавьте записи для каждой из точек соединения с `CONNECTION_POINT_ENTRY` макрос и выполнить сопоставление с [END_CONNECTION_POINT_MAP ](#end_connection_point_map) макрос.  
  
 Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP  
 Отмечает конец записей карты точки подключения.  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Запуск на сопоставление точки подключения с [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) макрос, добавьте записи для каждой из точек соединения с [CONNECTION_POINT_ENTRY](#connection_point_entry) макрос и выполнить сопоставление с `END_CONNECTION_POINT_MAP` макрос.  
  
 Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции точек подключения](../../atl/reference/connection-point-global-functions.md)
