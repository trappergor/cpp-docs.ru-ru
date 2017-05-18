---
title: "Макросы точки подключения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: c16b6f2f889745270a51a32a1449add86dec6ecb
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="connection-point-macros"></a>Макросы точки подключения
Эти макросы определение схемы точки подключения и записи.  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Отмечает начало записей карты точки подключения.|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Вводит карты точки подключения.|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017 г.) Но, похоже на CONNECTION_POINT_ENTRY принимает указатель на идентификатор iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Отмечает конец записей карты точки подключения.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h 
   
##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP  
 Отмечает начало записей карты точки подключения.  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса, содержащего точки подключения.  
  
### <a name="remarks"></a>Примечания  
 Запустите на сопоставление точки подключения с `BEGIN_CONNECTION_POINT_MAP` макрос, добавьте записи для каждой из точек соединения с [CONNECTION_POINT_ENTRY](#connection_point_entry) макрос и выполнить сопоставление с [END_CONNECTION_POINT_MAP](#end_connection_point_map) макрос.  
  
 Дополнительные сведения о точках подключения библиотеки ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#101;](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY и CONNECTION_POINT_ENTRY_P  
 Вводит точку подключения в сопоставление точки подключения, чтобы он был доступен для указанного интерфейса.  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, добавляемого к сопоставление точки подключения. 
 
 `piid`  
 [in] Указатель на интерфейс, который добавляет идентификатор GUID.   
  
### <a name="remarks"></a>Примечания  
 Записи точки соединения в схеме используются [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Класс, содержащий сопоставление точки подключения должен наследовать из `IConnectionPointContainerImpl`.  
  
 Запустите на сопоставление точки подключения с [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) макрос, добавьте записи для каждой из точек соединения с `CONNECTION_POINT_ENTRY` макрос и выполнить сопоставление с [END_CONNECTION_POINT_MAP](#end_connection_point_map) макрос.  
  
 Дополнительные сведения о точках подключения библиотеки ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#120;](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP  
 Отмечает конец записей карты точки подключения.  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Запустите на сопоставление точки подключения с [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) макрос, добавьте записи для каждой из точек соединения с [CONNECTION_POINT_ENTRY](#connection_point_entry) макрос и выполнить сопоставление с `END_CONNECTION_POINT_MAP` макрос.  
  
 Дополнительные сведения о точках подключения библиотеки ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#128;](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Точка подключения глобальные функции](../../atl/reference/connection-point-global-functions.md)

