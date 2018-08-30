---
title: Макросы схемы (классов ATL) сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d87a3b0e4ed9c5c558c90a2935c538b4fb826be
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201684"
---
# <a name="message-map-macros-atl"></a>Макросы схемы сообщений (ATL)
Эти макросы определяют схемы сообщений и записей.  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|Помечает начало альтернативную схему сообщений.|  
|[BEGIN_MSG_MAP](#begin_msg_map)|Отмечает начало карты сообщения по умолчанию.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочки для альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки для альтернативную схему сообщений в элемент данных класса.|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки для схемы сообщений в другом классе во время выполнения.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки в схеме сообщений по умолчанию в элементе данных класса.|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе кода уведомления.|  
|[COMMAND_HANDLER](#command_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Реализует сопоставление пустое сообщение.|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Предоставляет обработчик по умолчанию для отраженного сообщения, которые не обрабатываются иначе.|  
|[END_MSG_MAP](#end_msg_map)|Помечает конец виртуальной схемы сообщений.|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Перенаправляет сообщения уведомления в родительское окно.|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет сообщение Windows функцию обработчика событий.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет сообщения непрерывный диапазон Windows функцию обработчика событий.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления.|  
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе идентификатора элемента управления.|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Отражает уведомляющих сообщений в окно отправки их.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="alt_msg_map"></a>  ALT_MSG_MAP  
 Помечает начало альтернативную схему сообщений.  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 *msgMapID*  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 ATL определяет каждой карты сообщение с номером. Сопоставление сообщений по умолчанию (объявлено с помощью макроса BEGIN_MSG_MAP) определяется по 0. Альтернативную схему сообщений определяется *msgMapID*.  
  
 Схемы сообщений используются для обработки сообщений, отправленных в окно. Например [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) позволяет указать идентификатор виртуальной схемы сообщений в содержащем объекте. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) затем использует эту схему сообщения, чтобы направить содержащееся окно сообщения, или на другую схему сообщений соответствующим функциям обработки. Список макросов, которые объявляют функции обработчика, см. в разделе [BEGIN_MSG_MAP](#begin_msg_map).  
  
 Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений.  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Обратите внимание на то, что всегда есть только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано сообщение по умолчанию и одного альтернативную схему сообщений, каждая из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставления. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   

##  <a name="begin_msg_map"></a>  BEGIN_MSG_MAP  
 Отмечает начало карты сообщения по умолчанию.  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 *theClass*  
 [in] Имя класса, содержащего схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) использует схему сообщений по умолчанию для обработки сообщений, отправляемых в окно. Сопоставление сообщений направляет сообщения или на другую схему сообщений соответствующим функциям обработки.  

  
 Следующие макросы сопоставить сообщение функцию обработчика событий. Эта функция должен быть определен в *theClass*.  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет сообщение Windows функцию обработчика событий.|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет сообщения непрерывный диапазон Windows функцию обработчика событий.|  
|[COMMAND_HANDLER](#command_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[COMMAND_CODE_HANDLER](#command_handler)|Сопоставляет сообщение WM_COMMAND функцию обработчика событий, на основе кода уведомления.|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет сообщения непрерывный диапазон WM_COMMAND функцию обработчика событий, на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе идентификатора элемента управления.|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления.|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет сообщения непрерывный диапазон WM_NOTIFY функцию обработчика событий, на основе идентификатора элемента управления.|  
  
 Следующие макросы направлять сообщения в другую схему сообщений. Этот процесс называется «цепочки».  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки в схеме сообщений по умолчанию в базовом классе.|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки в схеме сообщений по умолчанию в элементе данных класса.|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочки для альтернативную схему сообщений в базовом классе.|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки для альтернативную схему сообщений в элемент данных класса.|  
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки в схеме сообщений по умолчанию в другом классе во время выполнения.|  
  
 Следующие макросы направлять сообщения «отражены» от родительского окна. Например элемент управления обычно отправляет сообщения уведомления своему родительскому окну для обработки, но родительского окна можно переслать сообщение обратно в элемент управления.  
  
|Макрос|Описание:|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления и идентификатор пункта меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженного сообщения WM_COMMAND функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и идентификатор элемента управления.|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе идентификатора элемента управления.|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления.|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, в зависимости от непрерывный диапазон идентификаторов элементов управления.|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженного сообщения WM_NOTIFY функцию обработчика событий, на основе кода уведомления и непрерывный диапазон идентификаторов элементов управления.|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 Когда `CMyExtWindow` объект получает сообщение WM_PAINT, сообщение направляется `CMyExtWindow::OnPaint` фактической обработки. Если `OnPaint` указывает сообщение требует дальнейшей обработки, то сообщение, а затем направляться в схеме сообщений по умолчанию в `CMyBaseWindow`.  
  
 В дополнение к схеме сообщений по умолчанию, вы можете определить альтернативную схему сообщений с [ALT_MSG_MAP](#alt_msg_map). Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений. В следующем примере показано сообщение по умолчанию и одного альтернативную схему сообщений, каждая из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставления. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Обратите внимание на то, что всегда есть только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_alt"></a>  CHAIN_MSG_MAP_ALT  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 *theChainClass*  
 [in] Имя базового класса, содержащего схему сообщений.  
  
 *msgMapID*  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 CHAIN_MSG_MAP_ALT направляет сообщения к альтернативную схему сообщений в базовом классе. Был объявлен этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщения в схеме сообщений по умолчанию базового класса (объявлен с [BEGIN_MSG_MAP](#begin_msg_map)), используйте CHAIN_MSG_MAP. Например, см. в разделе [CHAIN_MSG_MAP](#chain_msg_map).  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений с ALT_MSG_MAP. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_alt_member"></a>  CHAIN_MSG_MAP_ALT_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>Параметры  
 *theChainMember*  
 [in] Имя элемента данных, содержащий схему сообщений.  
  
 *msgMapID*  
 [in] Идентификатор сопоставления сообщения.  
  
### <a name="remarks"></a>Примечания  
 CHAIN_MSG_MAP_ALT_MEMBER направляет сообщения к альтернативную схему сообщений в элементе данных. Был объявлен этот альтернативную схему сообщений с [ALT_MSG_MAP(msgMapID)](#alt_msg_map). Для направления сообщения в схеме сообщений по умолчанию элемент данных (объявлен с [BEGIN_MSG_MAP](#begin_msg_map)), используйте CHAIN_MSG_MAP_MEMBER. Например, см. в разделе [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений с ALT_MSG_MAP. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map"></a>  CHAIN_MSG_MAP  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>Параметры  
 *theChainClass*  
 [in] Имя базового класса, содержащего схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 CHAIN_MSG_MAP направляет сообщения к схеме сообщений по умолчанию базового класса (объявлен с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений базовый класс альтернативную схему сообщений (объявлен с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений с ALT_MSG_MAP. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 Этот пример иллюстрирует следующее:  
  
-   При использовании процедуры окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер, сообщение, сообщение направляется `CMyBaseClass`элемента по умолчанию сопоставление сообщений для обработки.  
  
-   Если в процедуру окна используется первый альтернативную схему сообщений в `CMyClass`, все сообщения будут направляться `CMyBaseClass`в схеме сообщений по умолчанию.  
  
-   При использовании процедуры окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер, сообщение, сообщение направляется в указанное сообщение альтернативное сопоставление в `CMyBaseClass`. `CMyBaseClass` должен объявлен этого сопоставления сообщения с ALT_MSG_MAP(1).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_dynamic"></a>  CHAIN_MSG_MAP_DYNAMIC  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>Параметры  
 *dynaChainID*  
 [in] Уникальный идентификатор для объекта схемы сообщений.  
  
### <a name="remarks"></a>Примечания  
 CHAIN_MSG_MAP_DYNAMIC направляет сообщения, во время выполнения, в схеме сообщений по умолчанию в другом объекте. Объект и схему сообщений, связанных с *dynaChainID*, которое определяется через [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Должен быть производным от класса `CDynamicChain` для использования CHAIN_MSG_MAP_DYNAMIC. Например, см. в разделе [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Обзор.  

  
> [!NOTE]
>  Всегда начинаются схему сообщения со [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с ALT_MSG_MAP. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="chain_msg_map_member"></a>  CHAIN_MSG_MAP_MEMBER  
 Определяет запись в схеме сообщений.  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>Параметры  
 *theChainMember*  
 [in] Имя элемента данных, содержащий схему сообщений.  
  
### <a name="remarks"></a>Примечания  
 CHAIN_MSG_MAP_MEMBER направляет сообщения к схеме сообщений по умолчанию элемент данных (объявлен с [BEGIN_MSG_MAP](#begin_msg_map)). Для направления сообщений элемент данных альтернативную схему сообщений (объявлен с [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со BEGIN_MSG_MAP. Затем можно объявить схемы последующих альтернативный сообщений с ALT_MSG_MAP. [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 Этот пример иллюстрирует следующее:  
  
-   При использовании процедуры окна `CMyClass`в схеме сообщений по умолчанию и `OnPaint` не маркер, сообщение, сообщение направляется `m_obj`элемента по умолчанию сопоставление сообщений для обработки.  
  
-   Если в процедуру окна используется первый альтернативную схему сообщений в `CMyClass`, все сообщения будут направляться `m_obj`в схеме сообщений по умолчанию.  
  
-   При использовании процедуры окна `CMyClass`второе сообщение альтернативного сопоставления и `OnChar` не маркер, сообщение, сообщение направляется сопоставление указанного альтернативного сообщения `m_obj`. Класс `CMyContainedClass` должен объявлен этого сопоставления сообщения с ALT_MSG_MAP(1).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_code_handler"></a>  COMMAND_CODE_HANDLER  
 Аналогичную [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщения на основе только код уведомления.  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>Параметры  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_handler"></a>  COMMAND_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш.  
  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Сопоставляет COMMAND_HANDLER [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщение для указанного обработчика функции, в зависимости от кода уведомления и идентификатор элемента управления. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 Любая функция, указанных в макросе COMMAND_HANDLER должны быть определены следующим образом:  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 Карта наборов сообщений `bHandled` значение TRUE перед `CommandHandler` вызывается. Если `CommandHandler` не полностью обрабатывает сообщение, она должна задать `bHandled` значение false, чтобы указать, должна дальнейшей обработки сообщения.  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Помимо COMMAND_HANDLER, можно использовать [MESSAGE_HANDLER](#message_handler) сопоставить сообщение WM_COMMAND, вне зависимости от идентификатора или кода. В этом случае `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` будет направлять все сообщения WM_COMMAND `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_id_handler"></a>  COMMAND_ID_HANDLER  
 Аналогичную [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщение только на основе идентификатора элемента меню, элемент управления или сочетаний клавиш.  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_range_code_handler"></a>  COMMAND_RANGE_CODE_HANDLER  
 Аналогичную [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщений с кодом уведомления из диапазона элементов управления к одному обработчику функции.  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется идентификатор пункта меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="command_range_handler"></a>  COMMAND_RANGE_HANDLER  
 Аналогичную [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщений из диапазона элементов управления к одному обработчику функции.  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон определяется идентификатор пункта меню, элемент управления или сочетаний клавиш, отправляющий сообщение.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="declare_empty_msg_map"></a>  DECLARE_EMPTY_MSG_MAP  
 Объявляет сопоставление пустое сообщение.  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 DECLARE_EMPTY_MSG_MAP представляет собой макрос удобства, который вызывает макросы [BEGIN_MSG_MAP](#begin_msg_map) и [END_MSG_MAP](#end_msg_map) создать сопоставление пустое сообщение:  
  
 [!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="default_reflection_handler"></a>  DEFAULT_REFLECTION_HANDLER  
 Предоставляет обработчик по умолчанию для дочернего окна (управления), который будет получать отраженных сообщений; обработчик будет правильно передавать необработанные сообщения для `DefWindowProc`.  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="end_msg_map"></a>  END_MSG_MAP  
 Помечает конец виртуальной схемы сообщений.  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Всегда используйте [BEGIN_MSG_MAP](#begin_msg_map) макрос для обозначения начала виртуальной схемы сообщений. Используйте [ALT_MSG_MAP](#alt_msg_map) для объявления схемы последующих альтернативный сообщений.  
  
 Обратите внимание на то, что всегда есть только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано сообщение по умолчанию и одного альтернативную схему сообщений, каждая из которых содержит одну функцию обработчика:  
  
 [!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 В следующем примере показано два альтернативных сопоставления. Сопоставление сообщений по умолчанию является пустым.  
  
 [!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="forward_notifications"></a>  FORWARD_NOTIFICATIONS  
 Перенаправляет сообщения уведомления в родительское окно.  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос как часть вашей схемы сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="message_handler"></a>  MESSAGE_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>Параметры  
 *msg*  
 [in] Сообщение Windows.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 MESSAGE_HANDLER сообщение Windows сопоставляется с функцией указанным обработчиком.  
  
 Любая функция, указанных в макросе MESSAGE_HANDLER должны быть определены следующим образом:  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 Карта наборов сообщений `bHandled` значение TRUE перед `MessageHandler` вызывается. Если `MessageHandler` не полностью обрабатывает сообщение, она должна задать `bHandled` значение false, чтобы указать, должна дальнейшей обработки сообщения.  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Помимо MESSAGE_HANDLER, можно использовать [COMMAND_HANDLER](#command_handler) и [NOTIFY_HANDLER](#notify_handler) для сопоставления [WM_COMMAND](/windows/desktop/menurc/wm-command) и [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений , соответственно.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="message_range_handler"></a>  MESSAGE_RANGE_HANDLER  
 Аналогичную [MESSAGE_HANDLER](#message_handler), но сопоставлен диапазона Windows сообщений к одному обработчику функции.  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 *msgFirst*  
 [in] Помечает начало смежных сообщений.  
  
 *msgLast*  
 [in] Помечает конец смежных сообщений.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_code_handler"></a>  NOTIFY_CODE_HANDLER  
 Аналогичную [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщения на основе только код уведомления.  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>Параметры  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_handler"></a>  NOTIFY_HANDLER  
 Определяет запись в схеме сообщений.  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор элемента управления, отправляющего сообщения.  
  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Сопоставляет NOTIFY_HANDLER [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщение для указанного обработчика функции, в зависимости от кода уведомления и идентификатор элемента управления.  
  
 Любая функция, указанных в макросе NOTIFY_HANDLER должны быть определены следующим образом:  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 Карта наборов сообщений `bHandled` значение TRUE перед `NotifyHandler` вызывается. Если `NotifyHandler` не полностью обрабатывает сообщение, она должна задать `bHandled` значение false, чтобы указать, должна дальнейшей обработки сообщения.  
  
> [!NOTE]
>  Всегда начинаются схему сообщения со [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить схемы последующих альтернативный сообщений с [ALT_MSG_MAP](#alt_msg_map). [END_MSG_MAP](#end_msg_map) макрос отмечает конец схемы сообщений. Каждая схема сообщения должен иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.  
  
 Помимо NOTIFY_HANDLER, можно использовать [MESSAGE_HANDLER](#message_handler) для сопоставления сообщения WM_NOTIFY вне зависимости от идентификатора или кода. В этом случае `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` будет направлять все сообщения WM_NOTIFY `OnHandlerFunction`.  
  
 Дополнительные сведения об использовании схемы сообщений библиотеки ATL, см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_id_handler"></a>  NOTIFY_ID_HANDLER  
 Аналогичную [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщения на основе только идентификатор элемента управления.  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор элемента управления, отправляющего сообщения.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_range_code_handler"></a>  NOTIFY_RANGE_CODE_HANDLER  
 Аналогичную [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений с кодом уведомления из диапазона элементов управления к одному обработчику функции.  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон является на основе идентификатора элемента управления, отправляющего сообщения.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="notify_range_handler"></a>  NOTIFY_RANGE_HANDLER  
 Аналогичную [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583) сообщений из диапазона элементов управления к одному обработчику функции.  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="remarks"></a>Примечания  
 Этот диапазон является на основе идентификатора элемента управления, отправляющего сообщения.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="reflect_notifications"></a>  REFLECT_NOTIFICATIONS  
 Отражает уведомляющих сообщений к дочернему окну (управления), которое их отправки.  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>Примечания  
 Укажите этот макрос как часть схемы сообщений родительского окна.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="reflected_command_code_handler"></a>  REFLECTED_COMMAND_CODE_HANDLER  
 Аналогичную [COMMAND_CODE_HANDLER](#command_code_handler), но сопоставляет команды, отраженным из родительского окна.  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>Параметры  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
##  <a name="reflected_command_handler"></a>  REFLECTED_COMMAND_HANDLER  
 Аналогичную [COMMAND_HANDLER](#command_handler), но сопоставляет команды, отраженным из родительского окна.  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш.  
  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_command_id_handler"></a>  REFLECTED_COMMAND_ID_HANDLER  
 Аналогичную [COMMAND_ID_HANDLER](#command_id_handler), но сопоставляет команды, отраженным из родительского окна.  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_command_range_code_handler"></a>  REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 Аналогичную [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), но сопоставляет команды, отраженным из родительского окна.  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Код*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_command_range_handler"></a>  REFLECTED_COMMAND_RANGE_HANDLER  
 Аналогичную [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляет команды, отраженным из родительского окна.  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_notify_code_handler"></a>  REFLECTED_NOTIFY_CODE_HANDLER  
 Аналогичную [NOTIFY_CODE_HANDLER](#notify_code_handler), но сопоставляет уведомления, отраженным из родительского окна.  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_notify_handler"></a>  REFLECTED_NOTIFY_HANDLER  
 Аналогичную [NOTIFY_HANDLER](#notify_handler), но сопоставляет уведомления, отраженным из родительского окна.  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш.  
  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_notify_id_handler"></a>  REFLECTED_NOTIFY_ID_HANDLER  
 Аналогичную [NOTIFY_ID_HANDLER](#notify_id_handler), но сопоставляет уведомления, отраженным из родительского окна.  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>Параметры  
 *id*  
 [in] Идентификатор пункта меню, элемент управления или сочетаний клавиш.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

##  <a name="reflected_notify_range_code_handler"></a>  REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 Аналогичную [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), но сопоставляет уведомления, отраженным из родительского окна.  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *компакт-диска*  
 [in] Код уведомления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h   
  
##  <a name="reflected_notify_range_handler"></a>  REFLECTED_NOTIFY_RANGE_HANDLER  
 Аналогичную [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет уведомления, отраженным из родительского окна.  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>Параметры  
 *idFirst*  
 [in] Помечает начало непрерывный диапазон идентификаторов элементов управления.  
  
 *idLast*  
 [in] Помечает конец непрерывный диапазон идентификаторов элементов управления.  
  
 *Func*  
 [in] Имя функции обработчика сообщений.  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
