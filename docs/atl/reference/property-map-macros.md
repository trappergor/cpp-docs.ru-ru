---
title: "Макросы схемы свойства | Документы Microsoft"
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
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
caps.latest.revision: 17
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
ms.openlocfilehash: fbbed22766f9029456f15c4a554ae91322e6a275
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="property-map-macros"></a>Макрос свойств карты
Эти макросы определить сопоставления свойств и операций.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|Отмечает начало ATL сопоставление свойств.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|Указывает область, то размеры элемента управления ActiveX.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|Описание, идентификатор DISPID свойств и страницы свойств CLSID вводит в схеме сопоставления свойств.|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Описание свойства, свойство DISPID, страница свойств CLSID, вводит и `IDispatch` IID в схеме сопоставления свойств.|  
|[PROP_PAGE](#prop_page)|Вводит CLSID страницы свойств в схеме сопоставления свойств.|  
|[END_PROP_MAP](#end_prop_map)|Отмечает конец ATL сопоставление свойств.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
   
##  <a name="begin_prop_map"></a>BEGIN_PROP_MAP  
 Отмечает начало сопоставление свойств объекта.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Указывает класс, содержащий сопоставление свойств.  
  
### <a name="remarks"></a>Примечания  
 Сопоставление свойств содержит описания свойств, свойство DispId, страница свойств CLSID, и `IDispatch` идентификаторы IID. Классы [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), и [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) использовать сопоставление свойств получить и установить эту информацию.  
  
 При создании объекта с помощью мастера проектов ATL, мастер создаст пустой свойства карты, указав `BEGIN_PROP_MAP` следуют [END_PROP_MAP](#end_prop_map).  
  
 `BEGIN_PROP_MAP`не сохраняет out (измерения) объем сопоставление свойств, поскольку сопоставление свойств с помощью объекта могут не иметь пользовательский интерфейс, поэтому не было бы не экстента. Если объект является элементом управления ActiveX с интерфейсом пользователя, она имеет экстент. В этом случае необходимо указать [PROP_DATA_ENTRY](#prop_data_entry) в сопоставление свойств для предоставления экстента.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#103;](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>PROP_DATA_ENTRY  
 Указывает область, то размеры элемента управления ActiveX.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>Параметры  
 `szDesc`  
 [in] Описание свойства.  
  
 `member`  
 [in] Элемент данных, содержащий область; например `m_sizeExtent`.  
  
 *VT*  
 [in] Указывает тип VARIANT свойства.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос вызывает заданный элемент данных должна быть сохранена.  
  
 При создании элемента управления ActiveX, мастер вставляет этот макрос после макроса сопоставления свойства [BEGIN_PROP_MAP](#begin_prop_map) и перед макрос сопоставления свойства [END_PROP_MAP](#end_prop_map).  
  
### <a name="example"></a>Пример  
 В следующем примере область объекта ( `m_sizeExtent`) сохраняется.  
  
 [!code-cpp[NVC_ATL_Windowing&#131;](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#132;](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>PROP_ENTRY_TYPE  
 Введите описание, идентификатор DISPID свойств и страницы свойств CLSID в схеме сопоставления свойств объекта с помощью этого макроса.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>Параметры  
 `szDesc`  
 [in] Описание свойства.  
  
 `dispid`  
 [in] DISPID свойства.  
  
 `clsid`  
 [in] CLSID страницы связанного свойства. Использовать специальное значение `CLSID_NULL` для свойства, которое не имеет связанного свойства страницы.  
  
 `vt`  
 [in] Тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `PROP_ENTRY` Макрос был небезопасно и не рекомендуется. Он был заменен с `PROP_ENTRY_TYPE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставление свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_PROP_MAP](#begin_prop_map).  
  
##  <a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX  
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
 [in] CLSID страницы связанного свойства. Использовать специальное значение `CLSID_NULL` для свойства, которое не имеет связанного свойства страницы.  
  
 `iidDispatch`  
 [in] Идентификатор IID сдвоенный интерфейс, определяющего свойство.  
  
 `vt`  
 [in] Тип свойства.  
  
### <a name="remarks"></a>Примечания  
 `PROP_ENTRY_EX` Макрос был небезопасно и не рекомендуется. Он был заменен с `PROP_ENTRY_TYPE_EX`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставление свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 Следующий пример группирует записи для `IMyDual1` следуют запись для `IMyDual2`. Группирование по сдвоенный интерфейс повысит производительность.  
  
 [!code-cpp[NVC_ATL_Windowing&#133;](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>PROP_PAGE  
 Введите идентификатор CLSID страницы свойств в схеме сопоставления свойств объекта с помощью этого макроса.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] CLSID страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 `PROP_PAGE`Аналогично [PROP_ENTRY_TYPE](#prop_entry_type), но не требуется описание свойства или DISPID.  
  
> [!NOTE]
>  Если введен CLSID с `PROP_ENTRY_TYPE` или [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), необходимо создать дополнительную операцию с `PROP_PAGE`.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало сопоставление свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#134;](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>END_PROP_MAP  
 Отмечает конец сопоставление свойств объекта.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>Примечания  
 При создании объекта с помощью мастера проектов ATL, мастер создаст пустой свойства карты, указав [BEGIN_PROP_MAP](#begin_prop_map) следуют `END_PROP_MAP`.  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_PROP_MAP](#begin_prop_map).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

