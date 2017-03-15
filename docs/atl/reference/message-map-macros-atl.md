---
title: "Сообщение макросы схемы (классов ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8097982d6574af2ce1ba592dbead8abf6f6433df
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-atl"></a>Макросы схемы сообщений (ATL)
Эти макросы определять схемы сообщений и операции.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Отмечает начало альтернативную схему сообщений.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Отмечает начало в схеме сообщений по умолчанию.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Связан альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Связан альтернативную схему сообщений в данных члена класса.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки для сопоставления сообщения в другом классе во время выполнения.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки в схеме сообщений по умолчанию члена данных класса.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления.|  
|[COMMAND_HANDLER](#command_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе идентификатора элемента меню, управления или сочетаний клавиш.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет **WM_COMMAND** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Реализует привязку пустое сообщение.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Предоставляет обработчик по умолчанию для отраженные сообщения, которые не были обработаны в противном случае.|  
|[END_MSG_MAP](#end_msg_map)|Отмечает конец схемы сообщений.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Перенаправляет сообщения уведомления родительского окна.|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляется функции обработчика сообщений Windows.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляется функции обработчика сообщений непрерывный диапазон Windows.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления.|  
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе идентификатора элемента управления.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет **WM_NOTIFY** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Отражает уведомляющих сообщений в окно отправки их.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе идентификатора элемента меню, управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namealtmsgmapa--altmsgmap"></a><a name="alt_msg_map"></a>ALT_MSG_MAP  
 Отмечает начало альтернативную схему сообщений.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщений.  
  
### <a name="remarks"></a>Примечания  
 ATL определяет каждая карта сообщение с номером. В схеме сообщений по умолчанию (объявленные с `BEGIN_MSG_MAP` макрос) определяется 0. Определяется альтернативную схему сообщений `msgMapID`.  
  
 Схемы сообщений используются для обработки сообщений, отправленных в окно. Например [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) позволяет указать идентификатор схемы сообщений в вмещающего объекта. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) затем использует это сопоставление сообщений для направления сообщений содержащееся окно соответствующим функциям обработки или другой схеме сообщений. Список макросов, которые объявляют функции обработчика, в разделе [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативного сообщений.  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Обратите внимание, что всегда существует только один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано сообщение по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. В схеме сообщений по умолчанию является пустой.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   

##  <a name="a-namebeginmsgmapa--beginmsgmap"></a><a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Отмечает начало в схеме сообщений по умолчанию.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Имя класса, содержащего схему сообщения.  
  
### <a name="remarks"></a>Примечания  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) использует схему сообщений по умолчанию для обработки сообщений, отправляемых в окно. Сопоставление сообщений направляет сообщения соответствующим функциям обработки или другой схеме сообщений.  

  
 Следующие макросы сопоставить сообщение функцию обработчика событий. Эта функция должен быть определен в `theClass`.  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляется функции обработчика сообщений Windows.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляется функции обработчика сообщений непрерывный диапазон Windows.|  
|[COMMAND_HANDLER](#command_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе идентификатора элемента меню, управления или сочетаний клавиш.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Сопоставляет **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет диапазон смежных **WM_COMMAND** сообщений в функцию обработчика событий на основе идентификатора элемента меню, управления или сочетаний клавиш.|  
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе идентификатора элемента управления.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет диапазон смежных **WM_NOTIFY** сообщений в функцию обработчика событий, основанные на идентификаторе элемента управления.|  
  
 Следующие макросы направлять сообщения на другой схеме сообщений. Этот процесс называется «объединение».  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки в схеме сообщений по умолчанию члена данных класса.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Связан альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Связан альтернативную схему сообщений в данных члена класса.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки в схеме сообщений по умолчанию в другом классе во время выполнения.|  
  
 Следующие макросы направлять сообщения «отражены» из родительского окна. Например элемент управления обычно отправляет уведомления для родительского окна для обработки, но родительского окна можно переслать сообщение обратно в элемент управления.  
  
|Макрос|Описание|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе идентификатора элемента меню, управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженные **WM_COMMAND** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение для функции обработчика, основанной на непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженные **WM_NOTIFY** сообщение функцию обработчика событий на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#102;](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Когда `CMyExtWindow` объект получает `WM_PAINT` , сообщение направлено сообщение `CMyExtWindow::OnPaint` фактической обработки. Если `OnPaint` показывают сообщение требует дальнейшей обработки сообщения будет затем направляться в схеме сообщений по умолчанию в `CMyBaseWindow`.  
  
 В дополнение к схеме сообщений по умолчанию, можно определить альтернативную схему сообщений с [ALT_MSG_MAP](#alt_msg_map). Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативного сообщений. В следующем примере показано сообщение по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. В схеме сообщений по умолчанию является пустой.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Обратите внимание, что всегда существует только один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namechainmsgmapalta--chainmsgmapalt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainClass`  
 [in] Имя базового класса, содержащего схему сообщения.  
  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_ALT`направляет сообщения к альтернативную схему сообщений в базовом классе. Необходимо объявить этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщений в схеме сообщений по умолчанию базового класса (объявленные с [BEGIN_MSG_MAP](#begin_msg_map)), используйте `CHAIN_MSG_MAP`. Например, в разделе [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить последующие сообщения альтернативного сопоставления с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namechainmsgmapaltmembera--chainmsgmapaltmember"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainMember`  
 [in] Имя элемента данных, содержащий сопоставление сообщений.  
  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_ALT_MEMBER`направляет сообщения к альтернативную схему сообщений в членах данных. Необходимо объявить этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщений в схеме сообщений по умолчанию данные-член (объявленные с [BEGIN_MSG_MAP](#begin_msg_map)), используйте `CHAIN_MSG_MAP_MEMBER`. Например, в разделе [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить последующие сообщения альтернативного сопоставления с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namechainmsgmapa--chainmsgmap"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainClass`  
 [in] Имя базового класса, содержащего схему сообщения.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP`направляет сообщения к схеме сообщений по умолчанию базового класса (объявленные с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений для базового класса альтернативную схему сообщений (объявленные с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить последующие сообщения альтернативного сопоставления с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#107;](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 В этом примере демонстрируются следующие возможности.  
  
-   При использовании процедуре окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер направляется сообщение, то `CMyBaseClass`в схеме сообщений по умолчанию для обработки.  
  
-   Если процедура окна с помощью первого альтернативную схему сообщений в `CMyClass`, все сообщения направляются `CMyBaseClass`в схеме сообщений по умолчанию.  
  
-   Если используется процедура окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер сообщение, то направляется на карту указанного альтернативного сообщения в `CMyBaseClass`. `CMyBaseClass`должен был объявлен на этой карте сообщения с `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namechainmsgmapdynamica--chainmsgmapdynamic"></a><a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Параметры  
 *dynaChainID*  
 [in] Уникальный идентификатор для объекта схемы сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_DYNAMIC`направляет сообщения, во время выполнения, в схеме сообщений по умолчанию в другом объекте. Объект и его сопоставления сообщения связанные с *dynaChainID*, определяющих через [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Необходимо создать производный класс от `CDynamicChain` для использования `CHAIN_MSG_MAP_DYNAMIC`. Например, в разделе [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Обзор.  

  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие сообщения альтернативного сопоставления с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namechainmsgmapmembera--chainmsgmapmember"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainMember`  
 [in] Имя элемента данных, содержащий сопоставление сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_MEMBER`направляет сообщения к схеме сообщений по умолчанию данные-член (объявленные с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений для элемента данных альтернативную схему сообщений (объявленные с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с `BEGIN_MSG_MAP`. Затем можно объявить последующие сообщения альтернативного сопоставления с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#108;](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 В этом примере демонстрируются следующие возможности.  
  
-   При использовании процедуре окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер направляется сообщение, то `m_obj`в схеме сообщений по умолчанию для обработки.  
  
-   Если процедура окна с помощью первого альтернативную схему сообщений в `CMyClass`, все сообщения направляются `m_obj`в схеме сообщений по умолчанию.  
  
-   Если используется процедура окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер сообщение, сообщение направляется в указанное сообщение альтернативное сопоставление `m_obj`. Класс `CMyContainedClass` должен был объявлен на этой карте сообщения с `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namecommandcodehandlera--commandcodehandler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщения на основе только код уведомления.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Параметры  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namecommandhandlera--commandhandler"></a><a name="command_handler"></a>COMMAND_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 `COMMAND_HANDLER`Сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений в функцию обработчика, указанного на основе код уведомления и идентификатор элемента управления. Например:  
  
 [!code-cpp[NVC_ATL_Windowing&#119;](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Функции, указанной в `COMMAND_HANDLER` макрос должен быть определен следующим образом:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `CommandHandler` вызывается. Если `CommandHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие сообщения альтернативного сопоставления с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `COMMAND_HANDLER`, можно использовать [MESSAGE_HANDLER](#message_handler) для сопоставления **WM_COMMAND** сообщения без учета идентификатор или код. В этом случае `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` будет направлять все **WM_COMMAND** сообщений для `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namecommandidhandlera--commandidhandler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений только на основе идентификатора элемента меню, управления или сочетаний клавиш.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namecommandrangecodehandlera--commandrangecodehandler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Аналогично [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений с кодом уведомлений из диапазона элементов в функцию один обработчик.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется идентификатор пункта меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namecommandrangehandlera--commandrangehandler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений из диапазона элементов управления на функцию один обработчик.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется идентификатор пункта меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namedeclareemptymsgmapa--declareemptymsgmap"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Объявляет сопоставление пустое сообщение.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_EMPTY_MSG_MAP`представляет удобный макрос, который вызывает макросы [BEGIN_MSG_MAP](#begin_msg_map) и [END_MSG_MAP](#end_msg_map) для создания карты пустое сообщение:  
  
 [!code-cpp[NVC_ATL_Windowing&#122;](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="a-namedefaultreflectionhandlera--defaultreflectionhandler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Предоставляет обработчик по умолчанию для дочернего окна (элемент управления), который получит отраженных сообщений; обработчик будет правильно передавать необработанных сообщений в `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-nameendmsgmapa--endmsgmap"></a><a name="end_msg_map"></a>END_MSG_MAP  
 Отмечает конец схемы сообщений.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Всегда используйте [BEGIN_MSG_MAP](#begin_msg_map) макрос для обозначения начала схемы сообщений. Используйте [ALT_MSG_MAP](#alt_msg_map) для объявления схемы последующих альтернативного сообщений.  
  
 Обратите внимание, что всегда существует только один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано сообщение по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing&#98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. В схеме сообщений по умолчанию является пустой.  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-nameforwardnotificationsa--forwardnotifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Перенаправляет сообщения уведомления родительского окна.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос как часть вашей схеме сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namemessagehandlera--messagehandler"></a><a name="message_handler"></a>MESSAGE_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Параметры  
 `msg`  
 [in] Сообщение Windows.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 `MESSAGE_HANDLER`сопоставляется функции указанный обработчик сообщений Windows.  
  
 Функции, указанной в `MESSAGE_HANDLER` макрос должен быть определен следующим образом:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие сообщения альтернативного сопоставления с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `MESSAGE_HANDLER`, можно использовать [COMMAND_HANDLER](#command_handler) и [NOTIFY_HANDLER](#notify_handler) для сопоставления [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) и [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений, соответственно.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#129;](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namemessagerangehandlera--messagerangehandler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Аналогично [MESSAGE_HANDLER](#message_handler), но сопоставлен диапазон Windows сообщений в функцию один обработчик.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 *msgFirst*  
 [in] Отмечает начало смежных сообщений.  
  
 *msgLast*  
 [in] Отмечает конец смежных сообщений.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namenotifycodehandlera--notifycodehandler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщения на основе только код уведомления.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Параметры  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namenotifyhandlera--notifyhandler"></a><a name="notify_handler"></a>NOTIFY_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента управления, отправляющий сообщение.  
  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 `NOTIFY_HANDLER`Сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений в функцию обработчика, указанного на основе код уведомления и идентификатор элемента управления.  
  
 Функции, указанной в `NOTIFY_HANDLER` макрос должен быть определен следующим образом:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `NotifyHandler` вызывается. Если `NotifyHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются сопоставление сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие сообщения альтернативного сопоставления с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `NOTIFY_HANDLER`, можно использовать [MESSAGE_HANDLER](#message_handler) для сопоставления **WM_NOTIFY** сообщения без учета идентификатор или код. В этом случае `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` будет направлять все **WM_NOTIFY** сообщений для `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#130;](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namenotifyidhandlera--notifyidhandler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщения на основе только идентификатор элемента управления.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента управления, отправляющий сообщение.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namenotifyrangecodehandlera--notifyrangecodehandler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Аналогично [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с кодом уведомлений из диапазона элементов в функцию один обработчик.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется на идентификатор элемента управления, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namenotifyrangehandlera--notifyrangehandler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений из диапазона элементов управления на функцию один обработчик.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется на идентификатор элемента управления, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namereflectnotificationsa--reflectnotifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Отражает сообщения уведомлений обратно дочернее окно (элемент управления), отправившего их.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос как часть схемы родительского окна сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namereflectedcommandcodehandlera--reflectedcommandcodehandler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Аналогично [COMMAND_CODE_HANDLER](#command_code_handler), но сопоставляет команды отражается от родительского окна.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Параметры  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
##  <a name="a-namereflectedcommandhandlera--reflectedcommandhandler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет команды отражается от родительского окна.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectedcommandidhandlera--reflectedcommandidhandler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Аналогично [COMMAND_ID_HANDLER](#command_id_handler), но сопоставляет команды отражается от родительского окна.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectedcommandrangecodehandlera--reflectedcommandrangecodehandler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Аналогично [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), но сопоставляет команды отражается от родительского окна.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `code`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectedcommandrangehandlera--reflectedcommandrangehandler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Аналогично [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет команды отражается от родительского окна.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectednotifycodehandlera--reflectednotifycodehandler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Аналогично [NOTIFY_CODE_HANDLER](#notify_code_handler), но сопоставляет уведомлений отражается от родительского окна.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectednotifyhandlera--reflectednotifyhandler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет уведомлений отражается от родительского окна.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectednotifyidhandlera--reflectednotifyidhandler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Аналогично [NOTIFY_ID_HANDLER](#notify_id_handler), но сопоставляет уведомлений отражается от родительского окна.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню, элемент управления или сочетаний клавиш.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="a-namereflectednotifyrangecodehandlera--reflectednotifyrangecodehandler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Аналогично [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), но сопоставляет уведомлений отражается от родительского окна.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="a-namereflectednotifyrangehandlera--reflectednotifyrangehandler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Аналогично [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет уведомлений отражается от родительского окна.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 `idFirst`  
 [in] Отмечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 `idLast`  
 [in] Отмечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

