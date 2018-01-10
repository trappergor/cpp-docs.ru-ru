---
title: "Макросы схемы (классов ATL) сообщений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
dev_langs: C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 200d82c9d9b2ca0456ae5de4d6c937be69e212bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="message-map-macros-atl"></a>Макросы схемы сообщений (ATL)
Эти макросы определяют схемы сообщений и операции.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Отмечает начало альтернативную схему сообщений.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Отмечает начало карты сообщений по умолчанию.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочки для альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки для альтернативную схему сообщений в данных члена класса.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочек в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки для схемы сообщений в другом классе во время выполнения.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочек в схеме сообщений по умолчанию в данных члена класса.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[COMMAND_HANDLER](#command_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, основанные на идентификаторе элемента меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Реализует схему пустое сообщение.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Предоставляет обработчик по умолчанию для отраженные сообщения, которые не были обработаны в противном случае.|  
|[END_MSG_MAP](#end_msg_map)|Отмечает конец схемы сообщений.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Перенаправляет сообщения уведомления в родительское окно.|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет функцию обработчика сообщений Windows.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет сообщения непрерывный диапазон Windows функцию обработчика событий.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[NOTIFY_HANDLER](#notify_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе идентификатора элемента управления.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Отражает уведомляющих сообщений в окно, отправившего их.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, основанные на идентификаторе элемента меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="alt_msg_map"></a>ALT_MSG_MAP  
 Отмечает начало альтернативную схему сообщений.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 ATL определяет каждую карту сообщение с номером. Сопоставление сообщений по умолчанию (объявлено с `BEGIN_MSG_MAP` макрос) определяется 0. Альтернативную схему сообщений определяется `msgMapID`.  
  
 Схемы сообщений используются для обработки сообщений, отправленных в окно. Например [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) позволяет указать идентификатор схемы сообщений в вмещающего объекта. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) затем использует эту схему сообщений для направления сообщений содержащееся окно, соответствующий обработчик функции или в другой схеме сообщений. Список макросов, которые объявления функции обработчика см. в разделе [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений.  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Обратите внимание, что всегда ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 Ниже приведен пример сообщения по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика.  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   

##  <a name="begin_msg_map"></a>BEGIN_MSG_MAP  
 Отмечает начало карты сообщений по умолчанию.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Имя класса, содержащего схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) использует схему сообщений по умолчанию для обработки сообщений, отправляемых в окно. Сопоставление сообщений направляет сообщений соответствующим функциям обработки или другую схему сообщений.  

  
 Следующие макросы сопоставить сообщение функцию обработчика событий. Эта функция должен быть определен в `theClass`.  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет функцию обработчика сообщений Windows.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет сообщения непрерывный диапазон Windows функцию обработчика событий.|  
|[COMMAND_HANDLER](#command_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, основанные на идентификаторе элемента меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Maps **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет непрерывный диапазон **WM_COMMAND** сообщений в функцию обработчика событий на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[NOTIFY_HANDLER](#notify_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе идентификатора элемента управления.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Maps **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет непрерывный диапазон **WM_NOTIFY** сообщений в функцию обработчика событий, основанные на идентификаторе элемента управления.|  
  
 Следующие макросы направлять сообщения в другую схему сообщений. Этот процесс называется «привязка».  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочек в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочек в схеме сообщений по умолчанию в данных члена класса.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочки для альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки для альтернативную схему сообщений в данных члена класса.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочек в схеме сообщений по умолчанию в другом классе во время выполнения.|  
  
 Следующие макросы направлять сообщения «отражены» от родительского окна. Например элемент управления обычно отправляет сообщения уведомления своему родительскому окну для обработки, но родительского окна можно переслать сообщение обратно в элемент управления.  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, основанные на идентификаторе элемента меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженный **WM_COMMAND** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженный **WM_NOTIFY** сообщения функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Когда `CMyExtWindow` объект получает `WM_PAINT` , сообщение направлено сообщение `CMyExtWindow::OnPaint` фактической обработки. Если `OnPaint` указывает сообщения требуется дальнейшей обработки сообщения будут, а затем направлять на схеме сообщений по умолчанию в `CMyBaseWindow`.  
  
 В дополнение к схеме сообщений по умолчанию, можно определить альтернативную схему сообщений с [ALT_MSG_MAP](#alt_msg_map). Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений. Ниже приведен пример сообщения по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика.  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Обратите внимание, что всегда ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainClass`  
 [in] Имя базового класса, содержащего схему сообщений.  
  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_ALT`направляет сообщения к альтернативную схему сообщений в базовом классе. Был объявлен этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщений в схеме сообщений по умолчанию базового класса (объявлено с [BEGIN_MSG_MAP](#begin_msg_map)), используйте `CHAIN_MSG_MAP`. Пример см. в разделе [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainMember`  
 [in] Имя элемента данных, содержащий схему сообщений.  
  
 `msgMapID`  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_ALT_MEMBER`в члене данных направляет сообщения к альтернативную схему сообщений. Был объявлен этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщений в схеме сообщений по умолчанию элемент данных (объявлено с [BEGIN_MSG_MAP](#begin_msg_map)), используйте `CHAIN_MSG_MAP_MEMBER`. Пример см. в разделе [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainClass`  
 [in] Имя базового класса, содержащего схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP`направляет сообщения к схеме сообщений по умолчанию базового класса (объявлено с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений для базового класса альтернативную схему сообщений (объявлено с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Этот пример иллюстрирует следующее:  
  
-   При использовании процедуру окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер, сообщение направляется `CMyBaseClass`в схеме сообщений по умолчанию для обработки.  
  
-   Если процедуру окна с помощью первого альтернативную схему сообщений в `CMyClass`, все сообщения направляются `CMyBaseClass`в схеме сообщений по умолчанию.  
  
-   При использовании процедуру окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер, сообщение направляется в указанный альтернативной схеме сообщений в `CMyBaseClass`. `CMyBaseClass`необходимо было объявлено на этой карте сообщение с `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Параметры  
 *dynaChainID*  
 [in] Уникальный идентификатор для объекта схемы сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_DYNAMIC`направляет сообщения, во время выполнения, в схеме сообщений по умолчанию в другом объекте. Объект и схему сообщений, связанных с *dynaChainID*, которые определяют через [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Необходимо создать производный класс от `CDynamicChain` для использования `CHAIN_MSG_MAP_DYNAMIC`. Пример см. в разделе [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Обзор.  

  
> [!NOTE]
>  Всегда начинаются схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Параметры  
 `theChainMember`  
 [in] Имя элемента данных, содержащий схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 `CHAIN_MSG_MAP_MEMBER`направляет сообщения к схеме сообщений по умолчанию элемент данных (объявлено с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений для элемента данных альтернативную схему сообщений (объявлено с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с `BEGIN_MSG_MAP`. Затем можно объявить схемы последующих альтернативный сообщений с `ALT_MSG_MAP`. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Этот пример иллюстрирует следующее:  
  
-   При использовании процедуру окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер, сообщение направляется `m_obj`в схеме сообщений по умолчанию для обработки.  
  
-   Если процедуру окна с помощью первого альтернативную схему сообщений в `CMyClass`, все сообщения направляются `m_obj`в схеме сообщений по умолчанию.  
  
-   При использовании процедуру окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер, сообщение направляется карта указанного альтернативного сообщения `m_obj`. Класс `CMyContainedClass` необходимо было объявлено на этой карте сообщение с `ALT_MSG_MAP(1)`.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
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
  
##  <a name="command_handler"></a>COMMAND_HANDLER  
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
 `COMMAND_HANDLER`Сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений в функцию указанного обработчика в коде уведомления и идентификатор элемента управления. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Функции, указанной в `COMMAND_HANDLER` макрос должны быть определены следующим образом:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `CommandHandler` вызывается. Если `CommandHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `COMMAND_HANDLER`, можно использовать [MESSAGE_HANDLER](#message_handler) для сопоставления **WM_COMMAND** сообщения без учета идентификатор или кода. В этом случае `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` будет направлять все **WM_COMMAND** сообщений `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений только на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.  
  
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
  
##  <a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 Аналогично [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщений с кодом уведомлений из диапазона элементов управления на функцию один обработчик.  
  
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
  
##  <a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
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
  
##  <a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 Объявляет сопоставление пустое сообщение.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 `DECLARE_EMPTY_MSG_MAP`представляет удобный макрос, который вызывает макросы [BEGIN_MSG_MAP](#begin_msg_map) и [END_MSG_MAP](#end_msg_map) Создание карты пустое сообщение:  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 Предоставляет обработчик по умолчанию для дочернего окна (управления), который получит отраженных сообщений; Обработчик необработанных сообщений, чтобы правильно передает `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="end_msg_map"></a>END_MSG_MAP  
 Отмечает конец схемы сообщений.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Всегда используйте [BEGIN_MSG_MAP](#begin_msg_map) макрос для обозначения начала схемы сообщений. Используйте [ALT_MSG_MAP](#alt_msg_map) для объявления схемы последующих альтернативный сообщений.  
  
 Обратите внимание, что всегда ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 Ниже приведен пример сообщения по умолчанию и один альтернативную схему сообщений, каждый из которых содержит одну функцию обработчика.  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставлений. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 Перенаправляет сообщения уведомления в родительское окно.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос в рамках схему сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="message_handler"></a>MESSAGE_HANDLER  
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
 `MESSAGE_HANDLER`сопоставляется с функцией указанный обработчик сообщений Windows.  
  
 Функции, указанной в `MESSAGE_HANDLER` макрос должны быть определены следующим образом:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `MESSAGE_HANDLER`, можно использовать [COMMAND_HANDLER](#command_handler) и [NOTIFY_HANDLER](#notify_handler) для сопоставления [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) и [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений, соответственно.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 Аналогично [MESSAGE_HANDLER](#message_handler), но сопоставлен диапазона Windows сообщений в функцию один обработчик.  
  
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
  
##  <a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
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
  
##  <a name="notify_handler"></a>NOTIFY_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента управления, отправляющего сообщения.  
  
 `cd`  
 [in] Код уведомления.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 `NOTIFY_HANDLER`Сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений в функцию указанного обработчика в коде уведомления и идентификатор элемента управления.  
  
 Функции, указанной в `NOTIFY_HANDLER` макрос должны быть определены следующим образом:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Сопоставление наборов сообщений `bHandled` для **TRUE** перед `NotifyHandler` вызывается. Если `NotifyHandler` не полностью обрабатывает сообщение, он должен устанавливать `bHandled` для **FALSE** для указания сообщения требуется дополнительная обработка.  
  
> [!NOTE]
>  Всегда начинаются схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схему сообщений. Каждой карте сообщения должны иметь ровно один экземпляр `BEGIN_MSG_MAP` и `END_MSG_MAP`.  
  
 В дополнение к `NOTIFY_HANDLER`, можно использовать [MESSAGE_HANDLER](#message_handler) для сопоставления **WM_NOTIFY** сообщения без учета идентификатор или кода. В этом случае `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` будет направлять все **WM_NOTIFY** сообщений `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщения на основе только идентификатор элемента управления.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента управления, отправляющего сообщения.  
  
 `func`  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 Аналогично [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с кодом уведомлений из диапазона элементов управления на функцию один обработчик.  
  
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
 Этот диапазон определяется на идентификатор элемента управления, отправляющего сообщения.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
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
 Этот диапазон определяется на идентификатор элемента управления, отправляющего сообщения.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 Отражает сообщения уведомления обратно дочернее окно (управления), отправившего их.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос в составе схемы сообщений родительского окна.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 Аналогично [COMMAND_CODE_HANDLER](#command_code_handler), но сопоставляет команды, отраженной в родительское окно.  
  
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
   
##  <a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 Аналогично [COMMAND_HANDLER](#command_handler), но сопоставляет команды, отраженной в родительское окно.  
  
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

##  <a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 Аналогично [COMMAND_ID_HANDLER](#command_id_handler), но сопоставляет команды, отраженной в родительское окно.  
  
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

##  <a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Аналогично [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), но сопоставляет команды, отраженной в родительское окно.  
  
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

##  <a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 Аналогично [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет команды, отраженной в родительское окно.  
  
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

##  <a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 Аналогично [NOTIFY_CODE_HANDLER](#notify_code_handler), но сопоставляет уведомления, отраженной в родительское окно.  
  
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

##  <a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 Аналогично [NOTIFY_HANDLER](#notify_handler), но сопоставляет уведомления, отраженной в родительское окно.  
  
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

##  <a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 Аналогично [NOTIFY_ID_HANDLER](#notify_id_handler), но сопоставляет уведомления, отраженной в родительское окно.  
  
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

##  <a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Аналогично [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), но сопоставляет уведомления, отраженной в родительское окно.  
  
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
  
##  <a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 Аналогично [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет уведомления, отраженной в родительское окно.  
  
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
