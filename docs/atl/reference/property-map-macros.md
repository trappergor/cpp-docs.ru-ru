---
title: Макросы сопоставления свойств | Документация Майкрософт
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
ms.openlocfilehash: caa298ebbb96b04145bf2beb52f93838708ae50b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50088906"
---
# <a name="property-map-macros"></a>Макросы сопоставления свойств

Эти макросы определяют сопоставления свойств и операций.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|Помечает начало ATL сопоставление свойств.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Указывает, экстента или измерений, элементов управления ActiveX.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Описание, идентификатор DISPID свойства и свойства страницы свойств CLSID вводит в схеме сопоставления свойств.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Вводит описание свойства, свойство DISPID, страницу свойств CLSID, и `IDispatch` IID в схеме сопоставления свойств.|
|[PROP_PAGE](#prop_page)|Вводит CLSID страницы свойств в схеме сопоставления свойств.|
|[END_PROP_MAP](#end_prop_map)|Помечает конец ATL сопоставление свойств.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP

Отмечает начало карты свойство объекта.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
[in] Указывает класс, содержащий сопоставление свойств.

### <a name="remarks"></a>Примечания

Сопоставление свойств хранит описания свойств, DISPID свойства, страницу свойств CLSID, и `IDispatch` идентификаторы IID. Классы [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), и [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)использовать сопоставление свойств, чтобы получить и задать эти сведения.

При создании объекта с помощью мастера проектов ATL, мастер создаст картой пустым свойством, указав BEGIN_PROP_MAP, за которым следует [END_PROP_MAP](#end_prop_map).

BEGIN_PROP_MAP не сохраняет out (измерения) степень сопоставление свойств, так как объект, используя сопоставление свойств могут не иметь пользовательский интерфейс, поэтому бы не экстента. Если объект является элементом управления ActiveX с пользовательским интерфейсом, то у экстента. В этом случае необходимо указать [PROP_DATA_ENTRY](#prop_data_entry) в сопоставление свойств для предоставления области памяти.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY

Указывает, экстента или измерений, элементов управления ActiveX.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
[in] Описание свойства.

*member*<br/>
[in] Элемент данных, содержащий экстент; например `m_sizeExtent`.

*vt*<br/>
[in] Указывает тип VARIANT свойства.

### <a name="remarks"></a>Примечания

Этот макрос вызывает заданный элемент данных для сохранения.

При создании элемента управления ActiveX, мастер вставляет этот макрос после макроса карты свойство [BEGIN_PROP_MAP](#begin_prop_map) и перед макросу свойства карты [END_PROP_MAP](#end_prop_map).

### <a name="example"></a>Пример

В следующем примере, экстент объекта (`m_sizeExtent`) сохраняется.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE

Используйте этот макрос, чтобы ввести описание, идентификатор DISPID свойства и свойства страницы свойств CLSID в схеме сопоставления свойств объекта.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
[in] Описание свойства.

*Идентификатор DISPID*<br/>
[in] DISPID свойства.

*CLSID*<br/>
[in] CLSID страницы связанного свойства. Используйте значение CLSID_NULL специальное значение для свойства, которое не имеет связанного свойства страницы.

*vt*<br/>
[in] Тип свойства.

### <a name="remarks"></a>Примечания

Макрос PROP_ENTRY был небезопасно и не рекомендуется. Он был заменен PROP_ENTRY_TYPE.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало в схеме сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.

### <a name="example"></a>Пример

См. в примере [BEGIN_PROP_MAP](#begin_prop_map).

##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX

Аналогичную [PROP_ENTRY_TYPE](#prop_entry_type), но позволяет вам указать определенного IID, если объект поддерживает несколько сдвоенных интерфейсов.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
[in] Описание свойства.

*Идентификатор DISPID*<br/>
[in] DISPID свойства.

*CLSID*<br/>
[in] CLSID страницы связанного свойства. Используйте значение CLSID_NULL специальное значение для свойства, которое не имеет связанного свойства страницы.

*iidDispatch*<br/>
[in] Идентификатор IID сдвоенный интерфейс, определяющий свойство.

*vt*<br/>
[in] Тип свойства.

### <a name="remarks"></a>Примечания

Макрос PROP_ENTRY_EX был небезопасно и не рекомендуется. Он был заменен на PROP_ENTRY_TYPE_EX.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало в схеме сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.

### <a name="example"></a>Пример

В следующем примере группируются записи для `IMyDual1` следуют запись для `IMyDual2`. Группирование по сдвоенный интерфейс позволит повысить производительность.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>  PROP_PAGE

Используйте этот макрос для ввода CLSID страницы свойств в схеме сопоставления свойств объекта.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
[in] CLSID страницы свойств.

### <a name="remarks"></a>Примечания

Аналогичен PROP_PAGE [PROP_ENTRY_TYPE](#prop_entry_type), но не требует описания свойства или идентификатор DISPID.

> [!NOTE]
>  Если вы уже ввели CLSID с PROP_ENTRY_TYPE или [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), вам не нужно вносить дополнительную операцию с PROP_PAGE.

[BEGIN_PROP_MAP](#begin_prop_map) макрос отмечает начало в схеме сопоставления свойств; [END_PROP_MAP](#end_prop_map) макрос отмечает конец.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>  END_PROP_MAP

Помечает конец сопоставление свойств объекта.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Примечания

При создании объекта с помощью мастера проектов ATL, мастер создаст картой пустым свойством, указав [BEGIN_PROP_MAP](#begin_prop_map) следуют END_PROP_MAP.

### <a name="example"></a>Пример

См. в примере [BEGIN_PROP_MAP](#begin_prop_map).

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
