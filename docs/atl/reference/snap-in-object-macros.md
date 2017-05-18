---
title: "Объект макросы оснастки | Документы Microsoft"
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
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 13823feb06e7fecb2e81a01f3c88e3664de01d30
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="snap-in-object-macros"></a>Макросы объекта snap-In
Эти макросы обеспечивают поддержку расширения оснастки.  
  
|||  
|-|-|  
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|Отмечает начало сопоставление класса данных расширение оснастки для объекта Snap-In.|  
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|Отмечает начало карты инструментов для объекта Snap-In.|  
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|Отмечает конец сопоставление класса данных расширение оснастки для объекта Snap-In.|  
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|Отмечает конец карты инструментов для объекта Snap-In.|  
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|Создает элемент данных для класса данных расширения оснастки.|  
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|Вводит класс данных расширение сопоставление класса данных расширение объекта Snap-In.|  
|[SNAPINMENUID](#snapinmenuid)|Объявляет идентификатор контекстного меню, используемые объектом Snap-In.|  
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|Вводит панели инструментов панели инструментов карты объекта Snap-In.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h 
   
##  <a name="begin_extension_snapin_nodeinfo_map"></a>BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP  
 Отмечает начало расширение сопоставление класса данных.  
  
```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```  
  
### <a name="parameters"></a>Параметры  
 *className*  
 [in] Имя класса данных расширение оснастки.  
  
### <a name="remarks"></a>Примечания  
 Запустить расширение карты с `BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP` макрос, добавьте записи для каждого из типов данных расширение оснастки с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="begin_snapintoolbarid_map"></a>BEGIN_SNAPINTOOLBARID_MAP  
 Объявляет начало инструментов идентификатор схемы для объекта Snap-In.  
  
```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Задает класс объекта Snap-In.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#106;](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]  
  
##  <a name="end_extension_snapin_nodeinfo_map"></a>END_EXTENSION_SNAPIN_NODEINFO_MAP  
 Отмечает конец расширение сопоставление класса данных.  
  
```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 Запустить расширение карты с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных оснастки расширения с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос и выполнить сопоставление с `END_EXTENSION_SNAPIN_NODEINFO_MAP` макрос.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="end_snapintoolbarid_map"></a>END_SNAPINTOOLBARID_MAP  
 Объявляет конце панели инструментов карты идентификатор для объекта Snap-In.  
  
```
END_SNAPINTOOLBARID_MAP( _class )
```  
  
### <a name="parameters"></a>Параметры  
 `_class`  
 [in] Задает класс объекта Snap-In.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
##  <a name="extension_snapin_dataclass"></a>EXTENSION_SNAPIN_DATACLASS  
 Добавляет класс оснастки расширения данных члена данных **ISnapInItemImpl**-производного класса.  
  
```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```  
  
### <a name="parameters"></a>Параметры  
 `dataClass`  
 [in] Класс данных расширения оснастки.  
  
### <a name="remarks"></a>Примечания  
 Этот класс также должны вводиться в сопоставление класса данных расширение оснастки. Запуск карту класс расширение данных с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение оснастки с [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#105;](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]  
  
##  <a name="extension_snapin_nodeinfo_entry"></a>EXTENSION_SNAPIN_NODEINFO_ENTRY  
 Добавляет сопоставление класса данных расширение расширение класса данных.  
  
```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```  
  
### <a name="parameters"></a>Параметры  
 `dataClass`  
 [in] Класс данных расширения оснастки.  
  
### <a name="remarks"></a>Примечания  
 Запуск карту класс расширение данных с [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) макрос, добавьте записи для каждого из типов данных расширение оснастки с `EXTENSION_SNAPIN_NODEINFO_ENTRY` макрос и выполнить сопоставление с [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) макрос.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map).  
  
##  <a name="snapinmenuid"></a>SNAPINMENUID  
 Используйте этот макрос для объявления ресурсов меню контекста объекта Snap-In.  
  
```
SNAPINMENUID( id )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентифицирует контекстное меню объекта Snap-In.  
  
##  <a name="snapintoolbarid_entry"></a>SNAPINTOOLBARID_ENTRY  
 Введите идентификатор панели инструментов в схеме идентификатор объекта оснастку панели инструментов с помощью этого макроса.  
  
```
SNAPINTOOLBARID_ENTRY( id )
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Определяет элемент управления панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map) макрос отмечает начало карты идентификатор инструментов; [END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

