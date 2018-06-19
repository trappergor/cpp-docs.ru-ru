---
title: Макросы схемы свойство | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 718028385b3910b955c49ab9e0abddf23b443967
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365019"
---
# <a name="property-map-macros"></a>Макросы схемы свойство
Эти макросы определяют сопоставления свойств и записи.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|Отмечает начало ATL сопоставление свойств.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|Указывает область, то размеры элемента управления ActiveX.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|Вводит описание, идентификатор DISPID свойств и страницы свойств CLSID в схеме сопоставления свойств.|  
|[НА PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Вводит описания свойства, свойство DISPID, страницу свойств CLSID, и `IDispatch` IID в схеме сопоставления свойств.|  
|[PROP_PAGE](#prop_page)|Вводит CLSID страницы свойств в схеме сопоставления свойств.|  
|[END_PROP_MAP](#end_prop_map)|Отмечает конец ATL сопоставление свойств.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
   
##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP  
 Отмечает начало сопоставления свойств объекта.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Указывает класс, содержащий сопоставление свойств.  
  
### <a name="remarks"></a>Примечания  
 Описания свойств, свойства DispId, страницу свойств CLSID, хранятся в схеме сопоставления свойств и `IDispatch` IID. Классы [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), и [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)использовать в схеме сопоставления свойств для извлечения и установки этих сведений.  
  
 При создании объекта с помощью мастера проектов ATL, мастер создаст пустой свойства карты, указав `BEGIN_PROP_MAP` следуют [END_PROP_MAP](#end_prop_map).  
  
 `BEGIN_PROP_MAP` не сохраняет out экстент (измерения) в сопоставлении свойств, так как объект, с помощью сопоставления свойств могут не иметь пользовательский интерфейс, поэтому бы не экстента. Если объект является элементом управления ActiveX с пользовательским интерфейсом, она имеет экстент. В этом случае необходимо указать [PROP_DATA_ENTRY](#prop_data_entry) в сопоставление свойств для предоставления экстента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY  
 Указывает область, то размеры элемента управления ActiveX.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>Параметры  
 `szDesc`  
 [in] Описание свойства.  
  
 `member`  
 [in] Элемент данных, содержащий степени; например `m_sizeExtent`.  
  
 *vt*  
 [in] Указывает тип VARIANT свойства.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос вызывает заданный элемент данных должна быть сохранена.  
  
 При создании элемента управления ActiveX, как мастер вставит этот макрос после макроса сопоставления свойства [BEGIN_PROP_MAP](#begin_prop_map) и перед макрос сопоставления свойства [END_PROP_MAP](#end_prop_map).  
  
### <a name="example"></a>Пример  
 В следующем примере область объекта ( `m_sizeExtent`) сохраняется.  
  
 [!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE  
 Используйте этот макрос, чтобы ввести описание, идентификатор DISPID свойств и страницы свойств CLSID в схеме сопоставления свойств объекта.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>Параметры  
 `szDesc`  
 [in] Описание свойства.  
  
 `dispid`  
 [in] DISPID свойства.  
  
 `clsid`  
 [in] Код CLSID страницы связанного свойства. Использовать специальное значение `CLSID_NULL` для свойства, которое не имеет связанного свойства страницы.  
  
 `vt`  
 [in] Тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `PROP_ENTRY` Макрос был небезопасной и не рекомендуется. Он был заменен `PROP_ENTRY_TYPE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_PROP_MAP](#begin_prop_map).  
  
##  <a name="prop_entry_type_ex"></a>  НА PROP_ENTRY_TYPE_EX  
 Аналогично [PROP_ENTRY_TYPE](#prop_entry_type), но позволяет вам указать определенного IID, если объект поддерживает несколько сдвоенных интерфейсов.  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>Параметры  
 `szDesc`  
 [in] Описание свойства.  
  
 `dispid`  
 [in] DISPID свойства.  
  
 `clsid`  
 [in] Код CLSID страницы связанного свойства. Использовать специальное значение `CLSID_NULL` для свойства, которое не имеет связанного свойства страницы.  
  
 `iidDispatch`  
 [in] Идентификатор IID сдвоенный интерфейс, определяющего свойство.  
  
 `vt`  
 [in] Тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `PROP_ENTRY_EX` Макрос был небезопасной и не рекомендуется. Он был заменен `PROP_ENTRY_TYPE_EX`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 Следующий пример группирует записи для `IMyDual1` следуют запись для `IMyDual2`. Группирование по сдвоенный интерфейс улучшит производительность.  
  
 [!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>  PROP_PAGE  
 Используйте этот макрос для ввода CLSID страницы свойств в схеме сопоставления свойств объекта.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] Код CLSID страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 `PROP_PAGE` Аналогично [PROP_ENTRY_TYPE](#prop_entry_type), но не требуется описание свойства или DISPID.  
  
> [!NOTE]
>  При вводе идентификатора класса CLSID со `PROP_ENTRY_TYPE` или [на PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), необходимо внести дополнительные запись с `PROP_PAGE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>  END_PROP_MAP  
 Отмечает конец сопоставления свойств объекта.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 При создании объекта с помощью мастера проектов ATL, мастер создаст пустой свойства карты, указав [BEGIN_PROP_MAP](#begin_prop_map) следуют `END_PROP_MAP`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_PROP_MAP](#begin_prop_map).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
