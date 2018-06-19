---
title: Макросы объекта оснастки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
dev_langs:
- C++
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8a335bbe5424ca04f1db03a3f3ac4bf3cfa9ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363914"
---
# <a name="snap-in-object-macros"></a>Объект оснастки макросы
Эти макросы обеспечивают поддержку расширения оснастки.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Отмечает начало карты класс расширение данных для объекта оснастки.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Отмечает начало карты инструментов для объекта оснастки.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Отмечает конец сопоставления класса расширение данных для объекта оснастки.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Отмечает конец панели инструментов карты для объекта оснастки.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Создает элемент данных для класса данных расширения оснастки.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Вводит класс данных расширение класса сопоставление данных расширение объекта оснастки.|  
|[SNAPINMENUID](#snapinmenuid)|Объявляет идентификатор контекстного меню, используемые объектом оснастки.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Вводит панели инструментов панели инструментов карты объекта оснастки.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>  BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Отмечает начало карты расширение класса данных.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Параметры  
 *classname*  
 [in] Имя класса данных, расширение оснастки.  
  
### <a name="remarks"></a>Примечания  
 Запуск на карте расширение с `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` макрос, добавьте записи для каждого из типов данных расширение с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос и выполнить сопоставление с [END_ EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>  BEGIN_SNAPINTOOLBARID_MAP  
 Объявляет начало инструментов идентификатор схемы для объекта оснастки.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Указывает класс объекта оснастки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>  END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Отмечает конец сопоставления расширение класса данных.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Запуск на карте расширение с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных оснастки расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макроса Завершите карты с `END_EXTENSION_SNAPIN_NODEINFO_MAP` макрос.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>  END_SNAPINTOOLBARID_MAP  
 Объявляет конец карты идентификатор инструментов для объекта оснастки.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Указывает класс объекта оснастки.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>  EXTENSION_SNAPIN_DATACLASS  
 Добавляет данные-член класса данных расширение для **ISnapInItemImpl**-производного класса.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Параметры  
 `dataClass`  
 [in] Класс данных расширения оснастки.  
  
### <a name="remarks"></a>Примечания  
 Этот класс также должен быть введен в сопоставление класса данных расширение. Запуск на карте класс расширение данных с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>  EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Добавляет расширение класса данных карту расширение данных классов.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Параметры  
 `dataClass`  
 [in] Класс данных расширения оснастки.  
  
### <a name="remarks"></a>Примечания  
 Запуск на карте класс расширение данных с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение с `EXTENSION_SNAPIN_NODEINFO_ENTRY` макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>  SNAPINMENUID  
 Используйте этот макрос для объявления ресурс меню контекста объекта оснастки.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентифицирует контекстное меню объекта оснастки.  
  
##  <a name="snapintoolbarid_entry"></a>  SNAPINTOOLBARID_ENTRY  
 Используйте этот макрос ввести идентификатор панели инструментов в схеме ID объекта оснастку панели инструментов.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Определяет элемент управления панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) макрос отмечает начало карты идентификатор панели инструментов; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
