---
title: Макрос объекта Snap-In
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: 6a57cdb3c9b6a4448bc954ff754ac9b18fa0b393
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325859"
---
# <a name="snap-in-object-macros"></a>Макрос объекта Snap-In

Эти макросы обеспечивают поддержку расширений для оснастки.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Отмечает начало карты класса данных расширения расширения для объекта Snap-In.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Отметка начала карты панели инструментов для объекта Snap-In.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Отметка конца карты класса данных расширения расширения для объекта Snap-In.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Отметки конца карты панели инструментов для объекта Snap-In.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Создает член данных для класса данных расширения привязки.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Вводит класс данных расширения в отрывок в карту класса данных расширения расширения объекта Snap-In.|
|[СНПИННУИД](#snapinmenuid)|Объявляет идентификатор контекстного меню, используемого объектом Snap-In.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Введите панель инструментов в карту панели инструментов объекта Snap-In.|

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Отмечает начало карты класса данных расширения расширения.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
(в) Название класса данных расширения оснастки.

### <a name="remarks"></a>Remarks

Запустите карту расширения с BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP макроса, добавьте записи для каждого из типов данных расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макросом и завершите карту [макросом END_EXTENSION_SNAPIN_NODEINFO_MAP.](#end_extension_snapin_nodeinfo_map)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP

Объявляет начало идентификаторной карты панели инструментов для объекта Snap-In.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Параметры

*_class*<br/>
(в) Определяет класс объектов Snap-In.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP

Отметка конец карты класса данных расширения расширения.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Remarks

Запустите карту расширения с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макроса, добавьте записи для каждого из типов данных расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макросом и завершите карту с END_EXTENSION_SNAPIN_NODEINFO_MAP макросом.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP

Объявляет конец id-карты панели инструментов для объекта Snap-In.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Параметры

*_class*<br/>
(в) Определяет класс объектов Snap-In.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS

Добавляет участника данных в класс данных расширения для класса **ISnapInItemImpl.**

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Параметры

*данныеКласс*<br/>
(в) Класс данных расширения оснастки.

### <a name="remarks"></a>Remarks

Этот класс также должен быть введен в карту класса данных расширения. Запустите карту класса данных расширения с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макроса, добавьте записи для каждого из типов данных расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макросом и завершите карту [с](#end_extension_snapin_nodeinfo_map) END_EXTENSION_SNAPIN_NODEINFO_MAP макросом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY

Добавляет класс данных расширения расширения к карте класса данных расширения.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Параметры

*данныеКласс*<br/>
(в) Класс данных расширения оснастки.

### <a name="remarks"></a>Remarks

Запустите карту класса данных расширения с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макроса, добавьте записи для каждого из типов данных расширения с EXTENSION_SNAPIN_NODEINFO_ENTRY макросом и завершите карту с помощью [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макроса.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a>СНПИННУИД

Используйте этот макрос для объявления ресурса контекстного меню объекта Snap-In.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Определяет контекстное меню объекта Snap-In.

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY

Используйте этот макрос, чтобы ввести идентификатор панели инструментов в идентификатор панели инструментов Snap-In.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Параметры

*id*<br/>
(в) Определяет элемент управления панели инструментов.

### <a name="remarks"></a>Remarks

Макрос [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) знаменует собой начало id-карты панели инструментов; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) макрос знаменует собой конец.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
