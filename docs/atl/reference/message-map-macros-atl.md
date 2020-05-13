---
title: Карта сообщений Макрос (ATL)
ms.date: 11/04/2016
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
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: 157812fa6625869c86dd8a27156a2970a3dc8d4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326227"
---
# <a name="message-map-macros-atl"></a>Карта сообщений Макрос (ATL)

Эти макросы определяют карты сообщений и записи.

|||
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|Отмечает начало альтернативной карты сообщений.|
|[BEGIN_MSG_MAP](#begin_msg_map)|Отметка начала карты сообщения по умолчанию.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепи к альтернативной карте сообщений в базовом классе.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки к альтернативной карте сообщений в элементе данных класса.|
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки на карте сообщений по умолчанию в базовом классе.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки к карте сообщений в другом классе во время выполнения.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки к карте сообщения по умолчанию в члене группы данных класса.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|Карты WM_COMMAND сообщения с функцией обработчика, на основе кода уведомления.|
|[COMMAND_HANDLER](#command_handler)|Отображает WM_COMMAND сообщение функции обработчика на основе кода уведомлений и идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Отображает сообщение WM_COMMAND с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Отображает WM_COMMAND сообщение функции обработчика, основанное на коде уведомлений и смежном диапазоне идентификаторов управления.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Отображает WM_COMMAND сообщение с функцией обработчика, основанной на смежном диапазоне идентификаторов управления.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Реализует пустую карту сообщений.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Предоставляет обработчик по умолчанию для отраженных сообщений, которые не обрабатываются в противном случае.|
|[END_MSG_MAP](#end_msg_map)|Отметки конца карты сообщений.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Перенаправляет сообщения уведомлений в родительское окно.|
|[MESSAGE_HANDLER](#message_handler)|Отослает сообщение Windows к функции обработчика.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Отображает смежный диапазон сообщений Windows с функцией обработчика.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Карты WM_NOTIFY сообщения с функцией обработчика, на основе кода уведомления.|
|[NOTIFY_HANDLER](#notify_handler)|Отображает WM_NOTIFY сообщение с функцией обработчика на основе кода уведомлений и идентификатора управления.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Карты WM_NOTIFY сообщения с функцией обработчика, основанной на идентификаторе управления.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Отображает WM_NOTIFY сообщение функции обработчика, основанное на коде уведомлений и смежном диапазоне идентификаторов управления.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Отображает WM_NOTIFY сообщение с функцией обработчика, основанной на смежном диапазоне идентификаторов управления.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Отражает сообщения уведомлений обратно в окно, которое их отправило.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанной на коде уведомлений.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанного на коде уведомлений и идентификаторе элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанного на идентификаторе элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Карты отраженного WM_COMMAND сообщения для функции обработчика, основанной на коде уведомлений и смежном диапазоне идентификаторов управления.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Карты отраженного WM_COMMAND сообщения для функции обработчика, основанной на смежном диапазоне идентификаторов управления.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на коде уведомлений.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на коде уведомлений и идентификаторе управления.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на идентификаторе управления.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Карты отраженного WM_NOTIFY сообщения для функции обработчика, основанной на коде уведомлений и смежном диапазоне идентификаторов управления.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Карты отраженного WM_NOTIFY сообщения к функции обработчика, основанной на смежном диапазоне идентификаторов управления.|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="alt_msg_map"></a><a name="alt_msg_map"></a>ALT_MSG_MAP

Отмечает начало альтернативной карты сообщений.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>Параметры

*msgMapID*<br/>
(в) Идентификатор карты сообщений.

### <a name="remarks"></a>Remarks

ATL определяет каждую карту сообщений по номеру. Карта сообщений по умолчанию (объявленная с макросом BEGIN_MSG_MAP) идентифицируется по 0. Альтернативная карта сообщений идентифицируется *msgMapID.*

Карты сообщений используются для обработки сообщений, отправляемых в окно. Например, [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) позволяет указать идентификатор карты сообщений в содержащем объекте. [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc) затем использует эту карту сообщений, чтобы направить содержащиеся сообщения окна либо к соответствующей функции обработчика или на другую карту сообщений. Список макросов, декларизуемых функциями обработчика, см. [BEGIN_MSG_MAP](#begin_msg_map).

Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений.

Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Обратите внимание, что всегда есть точно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

В следующем примере показана карта сообщений по умолчанию и одна альтернативная карта сообщения, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные карты сообщений. Карта сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="begin_msg_map"></a><a name="begin_msg_map"></a>BEGIN_MSG_MAP

Отметка начала карты сообщения по умолчанию.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
(в) Название класса, содержащего карту сообщений.

### <a name="remarks"></a>Remarks

[CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc) использует карту сообщений по умолчанию для обработки сообщений, отправляемых в окно. Карта сообщений направляет сообщения либо в соответствующую функцию обработчика, либо на другую карту сообщений.

Следующие макросы нанесли сообщение функции обработчика. Эта функция должна быть *определена*в классе .

|Макрос|Описание|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Отослает сообщение Windows к функции обработчика.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Отображает смежный диапазон сообщений Windows с функцией обработчика.|
|[COMMAND_HANDLER](#command_handler)|Отображает WM_COMMAND сообщение функции обработчика на основе кода уведомлений и идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Отображает сообщение WM_COMMAND с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_CODE_HANDLER](#command_handler)|Карты WM_COMMAND сообщения с функцией обработчика, на основе кода уведомления.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Отображает смежный диапазон WM_COMMAND сообщений к функции обработчика, на основе идентификатора элемента меню, управления или ускорителя.|
|[NOTIFY_HANDLER](#notify_handler)|Отображает WM_NOTIFY сообщение с функцией обработчика на основе кода уведомлений и идентификатора управления.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Карты WM_NOTIFY сообщения с функцией обработчика, основанной на идентификаторе управления.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Карты WM_NOTIFY сообщения с функцией обработчика, на основе кода уведомления.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Отображает смежный диапазон WM_NOTIFY сообщений к функции обработчика, основанной на идентификаторе управления.|

Следующие макросы направляют сообщения на другую карту сообщений. Этот процесс называется "цепь".

|Макрос|Описание|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочки на карте сообщений по умолчанию в базовом классе.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочки к карте сообщения по умолчанию в члене группы данных класса.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепи к альтернативной карте сообщений в базовом классе.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочки к альтернативной карте сообщений в элементе данных класса.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочки к карте сообщений по умолчанию в другом классе во время выполнения.|

Следующие макросы направляют "отраженные" сообщения из родительского окна. Например, элемент управления обычно отправляет сообщения уведомлений в родительское окно для обработки, но родительское окно может отражать сообщение обратно в элемент управления.

|Макрос|Описание|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанного на коде уведомлений и идентификаторе элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанного на идентификаторе элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Карты отраженного WM_COMMAND сообщения функции обработчика, основанной на коде уведомлений.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Карты отраженного WM_COMMAND сообщения для функции обработчика, основанной на смежном диапазоне идентификаторов управления.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Карты отраженного WM_COMMAND сообщения для функции обработчика, основанной на коде уведомлений и смежном диапазоне идентификаторов управления.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на коде уведомлений и идентификаторе управления.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на идентификаторе управления.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Карты отраженного WM_NOTIFY сообщения функции обработчика, основанной на коде уведомлений.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Карты отраженного WM_NOTIFY сообщения к функции обработчика, основанной на смежном диапазоне идентификаторов управления.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Карты отраженного WM_NOTIFY сообщения для функции обработчика, основанной на коде уведомлений и смежном диапазоне идентификаторов управления.|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

Когда `CMyExtWindow` объект получает WM_PAINT сообщение, сообщение `CMyExtWindow::OnPaint` направляется для фактической обработки. Если `OnPaint` сообщение требует дальнейшей обработки, сообщение будет направлено на `CMyBaseWindow`карту сообщения по умолчанию в .

В дополнение к карте сообщений по умолчанию можно определить альтернативную карту сообщений с [ALT_MSG_MAP](#alt_msg_map). Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений. В следующем примере показана карта сообщений по умолчанию и одна альтернативная карта сообщения, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные карты сообщений. Карта сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Обратите внимание, что всегда есть точно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_alt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT

Определяет запись на карте сообщений.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>Параметры

*TheChainClass*<br/>
(в) Название базового класса, содержащего карту сообщений.

*msgMapID*<br/>
(в) Идентификатор карты сообщений.

### <a name="remarks"></a>Remarks

CHAIN_MSG_MAP_ALT направляет сообщения на альтернативную карту сообщений в базовом классе. Вы должны были задекларировал эту альтернативную карту сообщений с [ALT_MSG_MAP (msgMapID).](#alt_msg_map) Чтобы направить сообщения на карту сообщений базового класса по умолчанию (объявленную [с BEGIN_MSG_MAP),](#begin_msg_map)используйте CHAIN_MSG_MAP. Например, [см. CHAIN_MSG_MAP](#chain_msg_map).

> [!NOTE]
> Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений с ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_alt_member"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER

Определяет запись на карте сообщений.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>Параметры

*TheChainMember*<br/>
(в) Имя участника данных, содержащего карту сообщений.

*msgMapID*<br/>
(в) Идентификатор карты сообщений.

### <a name="remarks"></a>Remarks

CHAIN_MSG_MAP_ALT_MEMBER направляет сообщения на альтернативную карту сообщений в элементе данных. Вы должны были задекларировал эту альтернативную карту сообщений с [ALT_MSG_MAP (msgMapID).](#alt_msg_map) Чтобы направить сообщения на карту сообщения по умолчанию участника данных (объявленную с [BEGIN_MSG_MAP),](#begin_msg_map)используйте CHAIN_MSG_MAP_MEMBER. Например, см. [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).

> [!NOTE]
> Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений с ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP

Определяет запись на карте сообщений.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>Параметры

*TheChainClass*<br/>
(в) Название базового класса, содержащего карту сообщений.

### <a name="remarks"></a>Remarks

CHAIN_MSG_MAP направляет сообщения на карту сообщений базового класса по умолчанию (объявленную [с BEGIN_MSG_MAP).](#begin_msg_map) Чтобы направить сообщения на альтернативную карту сообщений базового класса (объявленную [с ALT_MSG_MAP),](#alt_msg_map)используйте [CHAIN_MSG_MAP_ALT.](#chain_msg_map_alt)

> [!NOTE]
> Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений с ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

Этот пример иллюстрирует следующее:

- Если процедура окна `CMyClass`использует карту сообщения `OnPaint` по умолчанию и не обрабатывает `CMyBaseClass`сообщение, сообщение направляется на карту сообщения по умолчанию для обработки.

- Если процедура окна использует первую альтернативную карту `CMyClass`сообщения, `CMyBaseClass`все сообщения направляются на карту сообщений по умолчанию.

- Если процедура окна `CMyClass`использует вторую альтернативную `OnChar` карту сообщения и не обрабатывает сообщение, сообщение направляется на указанную альтернативную карту сообщения в `CMyBaseClass`. `CMyBaseClass`должны были обобъявлении эту карту сообщений с ALT_MSG_MAP(1).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_dynamic"></a><a name="chain_msg_map_dynamic"></a>CHAIN_MSG_MAP_DYNAMIC

Определяет запись на карте сообщений.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>Параметры

*dynaChainID*<br/>
(в) Уникальный идентификатор для карты сообщений объекта.

### <a name="remarks"></a>Remarks

CHAIN_MSG_MAP_DYNAMIC направляет сообщения во время выполнения на карту сообщений по умолчанию на другом объекте. Объект и его карта сообщений связаны с *dynaChainID*, который вы определяете через [CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry). Вы должны получить `CDynamicChain` свой класс из того, чтобы использовать CHAIN_MSG_MAP_DYNAMIC. Например, [см.](../../atl/reference/cdynamicchain-class.md)

> [!NOTE]
> Всегда начинайте карту сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные карты сообщений с ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_member"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER

Определяет запись на карте сообщений.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>Параметры

*TheChainMember*<br/>
(в) Имя участника данных, содержащего карту сообщений.

### <a name="remarks"></a>Remarks

CHAIN_MSG_MAP_MEMBER направляет сообщения на карту сообщения по умолчанию участника данных (объявленную [с BEGIN_MSG_MAP).](#begin_msg_map) Чтобы направить сообщения на альтернативную карту сообщения участника данных (объявленную [с ALT_MSG_MAP),](#alt_msg_map)используйте [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).

> [!NOTE]
> Всегда начинайте карту сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные карты сообщений с ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

Этот пример иллюстрирует следующее:

- Если процедура окна `CMyClass`использует карту сообщения `OnPaint` по умолчанию и не обрабатывает `m_obj`сообщение, сообщение направляется на карту сообщения по умолчанию для обработки.

- Если процедура окна использует первую альтернативную карту `CMyClass`сообщения, `m_obj`все сообщения направляются на карту сообщений по умолчанию.

- Если процедура окна `CMyClass`использует вторую альтернативную `OnChar` карту сообщения и не обрабатывает сообщение, сообщение направляется на указанную альтернативную карту сообщения `m_obj`. Класс `CMyContainedClass` должен был задекларировал эту карту сообщений с ALT_MSG_MAP(1).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_code_handler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER

Как и [COMMAND_HANDLER,](#command_handler)но карты [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение основано только на коде уведомления.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>Параметры

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_handler"></a><a name="command_handler"></a>COMMAND_HANDLER

Определяет запись на карте сообщений.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя.

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

COMMAND_HANDLER отображает [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение для указанной функции обработчика, основанной на коде уведомлений и идентификаторе управления. Пример:

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

Любая функция, указанная в COMMAND_HANDLER макросе, должна быть определена следующим образом:

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

Карта сообщений `bHandled` устанавливается `CommandHandler` на TRUE, прежде чем называется. Если `CommandHandler` сообщение не полностью обработано, оно должно быть установлено `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинайте карту сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные карты сообщений с [ALT_MSG_MAP.](#alt_msg_map) Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к COMMAND_HANDLER можно использовать [MESSAGE_HANDLER](#message_handler) для картирования WM_COMMAND сообщения без учета идентификатора или кода. В этом `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` случае, направит все WM_COMMAND сообщения `OnHandlerFunction`.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_id_handler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER

Как и [COMMAND_HANDLER,](#command_handler)но отображает [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение, основанное только на идентификаторе элемента меню, элемента управления или ускорителя.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя отправки сообщения.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_range_code_handler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER

Как и [COMMAND_RANGE_HANDLER,](#command_range_handler)но карты [WM_COMMAND](/windows/win32/menurc/wm-command) сообщения с определенным кодом уведомлений от ряда элементов управления до функции одного обработчика.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

Этот диапазон основан на идентификаторе элемента меню, элемента управления или ускорителя отправки сообщения.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_range_handler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER

Как и [COMMAND_HANDLER,](#command_handler)но карты [WM_COMMAND](/windows/win32/menurc/wm-command) сообщения от различных элементов управления до функции одного обработчика.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

Этот диапазон основан на идентификаторе элемента меню, элемента управления или ускорителя отправки сообщения.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="declare_empty_msg_map"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP

Объявляет пустую карту сообщений.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>Remarks

DECLARE_EMPTY_MSG_MAP является удобным макросом, который вызывает [BEGIN_MSG_MAP](#begin_msg_map) и [END_MSG_MAP](#end_msg_map) для создания пустой карты сообщений:

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

## <a name="default_reflection_handler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER

Обеспечивает обработчик по умолчанию для окна ребенка (управления), которое будет получать отраженные сообщения; обработчик будет правильно передавать `DefWindowProc`необработанные сообщения.

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="end_msg_map"></a><a name="end_msg_map"></a>END_MSG_MAP

Отметки конца карты сообщений.

```
END_MSG_MAP()
```

### <a name="remarks"></a>Remarks

Всегда используйте [BEGIN_MSG_MAP](#begin_msg_map) макрос, чтобы отметить начало карты сообщений. Используйте [ALT_MSG_MAP](#alt_msg_map) для объявления последующих альтернативных карт сообщений.

Обратите внимание, что всегда есть точно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

В следующем примере показана карта сообщений по умолчанию и одна альтернативная карта сообщения, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные карты сообщений. Карта сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="forward_notifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS

Перенаправляет сообщения уведомлений в родительское окно.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>Remarks

Укажите этот макрос как часть карты сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="message_handler"></a><a name="message_handler"></a>MESSAGE_HANDLER

Определяет запись на карте сообщений.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>Параметры

*Msg*<br/>
(в) Сообщение Windows.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

MESSAGE_HANDLER отображает сообщение Windows с указанной функцией обработчика.

Любая функция, указанная в MESSAGE_HANDLER макросе, должна быть определена следующим образом:

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

Карта сообщений `bHandled` устанавливается `MessageHandler` на TRUE, прежде чем называется. Если `MessageHandler` сообщение не полностью обработано, оно должно быть установлено `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинайте карту сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные карты сообщений с [ALT_MSG_MAP.](#alt_msg_map) Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к MESSAGE_HANDLER, вы можете использовать [COMMAND_HANDLER](#command_handler) и [NOTIFY_HANDLER](#notify_handler) для отображения [WM_COMMAND](/windows/win32/menurc/wm-command) и [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщений, соответственно.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="message_range_handler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER

Как и [MESSAGE_HANDLER,](#message_handler)но отображает ряд сообщений Windows на одну функцию обработчика.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>Параметры

*msgПервый*<br/>
(в) Отмечает начало смежного диапазона сообщений.

*msgLast*<br/>
(в) Отмечает конец смежного диапазона сообщений.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_code_handler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER

Как и [NOTIFY_HANDLER,](#notify_handler)но карты [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение основано только на коде уведомления.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>Параметры

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_handler"></a><a name="notify_handler"></a>NOTIFY_HANDLER

Определяет запись на карте сообщений.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента управления, отправляющий сообщение.

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

NOTIFY_HANDLER отображает [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с указанной функцией обработчика на основе кода уведомлений и идентификатора управления.

Любая функция, указанная в NOTIFY_HANDLER макросе, должна быть определена следующим образом:

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

Карта сообщений `bHandled` устанавливается `NotifyHandler` на TRUE, прежде чем называется. Если `NotifyHandler` сообщение не полностью обработано, оно должно быть установлено `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинайте карту сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные карты сообщений с [ALT_MSG_MAP.](#alt_msg_map) Макрос [END_MSG_MAP](#end_msg_map) обозначает конец карты сообщений. Каждая карта сообщений должна иметь ровно один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к NOTIFY_HANDLER можно использовать [MESSAGE_HANDLER](#message_handler) для картирования WM_NOTIFY сообщения без учета идентификатора или кода. В этом `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` случае, направит все WM_NOTIFY сообщения `OnHandlerFunction`.

Для получения дополнительной информации об использовании карт сообщений в ATL, [см.](../../atl/message-maps-atl.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_id_handler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER

Как и [NOTIFY_HANDLER,](#notify_handler)но карты [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение основано только на идентификаторе управления.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента управления, отправляющий сообщение.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_range_code_handler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER

Как и [NOTIFY_RANGE_HANDLER,](#notify_range_handler)но карты [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщения с определенным кодом уведомлений от ряда элементов управления до функции одного обработчика.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

Этот диапазон основан на идентификаторе элемента управления, отправляемого сообщением.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_range_handler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER

Как и [NOTIFY_HANDLER,](#notify_handler)но карты [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщения от различных элементов управления до функции одного обработчика.

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="remarks"></a>Remarks

Этот диапазон основан на идентификаторе элемента управления, отправляемого сообщением.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflect_notifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS

Отражает сообщения уведомлений обратно в окно ребенка (управление), которое их отправило.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>Remarks

Укажите этот макрос как часть карты сообщений родительского окна.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_code_handler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER

Как и [COMMAND_CODE_HANDLER,](#command_code_handler)но команды карт отражаются из родительского окна.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>Параметры

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_handler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER

Как и [COMMAND_HANDLER,](#command_handler)но команды карт отражаются из родительского окна.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя.

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_id_handler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER

Как и [COMMAND_ID_HANDLER,](#command_id_handler)но команды карт отражаются из родительского окна.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_range_code_handler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER

Как и [COMMAND_RANGE_CODE_HANDLER,](#command_range_code_handler)но команды карт отражаются из родительского окна.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*Код*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_range_handler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER

Как и [COMMAND_RANGE_HANDLER,](#command_range_handler)но команды карт отражаются из родительского окна.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_code_handler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER

Как и [NOTIFY_CODE_HANDLER,](#notify_code_handler)но карты уведомлений, отраженных из родительского окна.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>Параметры

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_handler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER

Как и [NOTIFY_HANDLER,](#notify_handler)но карты уведомлений, отраженных из родительского окна.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя.

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_id_handler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER

Как и [NOTIFY_ID_HANDLER,](#notify_id_handler)но карты уведомлений, отраженных из родительского окна.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Идентификатор элемента меню, элемент управления или ускорителя.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_range_code_handler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER

Как и [NOTIFY_RANGE_CODE_HANDLER,](#notify_range_code_handler)но карты уведомлений, отраженных из родительского окна.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*cd*<br/>
(в) Код уведомления.

*func*<br/>
(в) Название функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_range_handler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER

Как и [NOTIFY_RANGE_HANDLER,](#notify_range_handler)но карты уведомлений, отраженных из родительского окна.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*idПервый*<br/>
(в) Отмечает начало смежного диапазона идентификаторов управления.

*idLast*<br/>
(в) Отметки конца смежного диапазона идентификаторов управления.

*func*<br/>
(в) Название функции обработчика сообщений.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
