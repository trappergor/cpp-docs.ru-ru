---
title: Макросы объекта оснастки
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
ms.openlocfilehash: e3eec62e2bea92f1f308b149046b83be1b9085b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656941"
---
# <a name="snap-in-object-macros"></a>Макросы объекта оснастки

Эти макросы обеспечивают поддержку расширения оснастки.

|||
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Отмечает начало карты класс расширение данных для объекта Snap-In.|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Отмечает начало карты инструментов для объекта Snap-In.|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Помечает конец сопоставление класса данных расширение для объекта Snap-In.|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Помечает конец панели инструментов карты для объекта Snap-In.|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Создает элемент данных для класса данных расширения оснастки.|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Вводит класс данных расширение сопоставление класса данных расширение объекта Snap-In.|
|[SNAPINMENUID](#snapinmenuid)|Объявляет идентификатор контекстного меню, используемые объектом Snap-In.|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Вводит панель инструментов панели инструментов карты объекта Snap-In.|

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

Отмечает начало карты расширение данных класса.

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>Параметры

*classname*<br/>
[in] Имя класса данных расширение.

### <a name="remarks"></a>Примечания

Запустите расширение карты с помощью макроса BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP, добавьте записи для каждого из типов данных расширение с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос и выполнить сопоставление с [ END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP

Объявляет начало карты идентификатор панели инструментов для объекта Snap-In.

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>Параметры

*_класса*<br/>
[in] Задает класс объекта Snap-In.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP

Помечает конец сопоставление класса данных расширение.

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>Примечания

Запустите оснастку расширения карты с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных оснастку расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос, и завершить карты с помощью макроса END_EXTENSION_SNAPIN_NODEINFO_MAP.

### <a name="example"></a>Пример

См. в примере [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP

Объявляет конце сопоставления идентификатор панели инструментов для объекта Snap-In.

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>Параметры

*_класса*<br/>
[in] Задает класс объекта Snap-In.

### <a name="example"></a>Пример

См. в примере [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS

Добавляет данные-член в класс данных расширение для **ISnapInItemImpl**-производного класса.

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>Параметры

*классу данных*<br/>
[in] Класс данных расширения оснастки.

### <a name="remarks"></a>Примечания

Этот класс также должны вводиться в сопоставление класса данных расширение. Запуск карту класс расширение данных с помощью [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY

Добавляет сопоставление класса данных расширение расширение класса данных.

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>Параметры

*классу данных*<br/>
[in] Класс данных расширения оснастки.

### <a name="remarks"></a>Примечания

Запуск карту класс расширение данных с помощью [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение с помощью макроса EXTENSION_SNAPIN_NODEINFO_ENTRY и завершить карты с помощью [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.

### <a name="example"></a>Пример

См. в примере [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).

##  <a name="snapinmenuid"></a>  SNAPINMENUID

Используйте этот макрос для объявления ресурс меню контекста объекта Snap-In.

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>Параметры

*id*<br/>
[in] Идентифицирует контекстное меню объекта Snap-In.

##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY

Используйте этот макрос ввести идентификатор панели инструментов карты идентификатор панели инструментов объект Snap-In.

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>Параметры

*id*<br/>
[in] Определяет элемент управления панели инструментов.

### <a name="remarks"></a>Примечания

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) макрос отмечает начало карты идентификатор панели инструментов; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) макрос отмечает конец.

### <a name="example"></a>Пример

См. в примере [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
