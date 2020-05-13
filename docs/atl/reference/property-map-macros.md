---
title: Недвижимость Карта Макрос
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 56fdb02939a99e396b9000705753e2475b80f6dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326091"
---
# <a name="property-map-macros"></a>Недвижимость Карта Макрос

Эти макросы определяют карты свойств и записи.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|Отмечает начало карты свойств ATL.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Указывает степень или размеры элемента управления ActiveX.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Введите описание свойства, свойство DISPID и страницу свойств CLSID в карту свойства.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Введите описание свойства, свойство DISPID, `IDispatch` страницу свойств CLSID и IID в карту свойства.|
|[PROP_PAGE](#prop_page)|Ввод страницы свойств CLSID в карту свойств.|
|[END_PROP_MAP](#end_prop_map)|Отметка конца карты свойств ATL.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a>BEGIN_PROP_MAP

Отмечает начало карты свойства объекта.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
(в) Опображаем класс, содержащий карту свойств.

### <a name="remarks"></a>Remarks

Карта недвижимости хранит описания свойств, свойства DISPIDs, страницы собственности CLSIDs, и `IDispatch` IIDs. Классы [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), и [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) использовать карту свойств для получения и установить эту информацию.

При создании объекта с помощью Мастера проекта ATL мастер создаст пустую карту свойств, указав BEGIN_PROP_MAP следуют [END_PROP_MAP.](#end_prop_map)

BEGIN_PROP_MAP не экономит размер (т.е. размеры) карты свойств, поскольку объект, использующий карту свойств, может не иметь пользовательского интерфейса, поэтому он не будет иметь никакого размера. Если объект является элементом управления ActiveX с пользовательским интерфейсом, он имеет степень. В этом случае необходимо указать [PROP_DATA_ENTRY](#prop_data_entry) на карте недвижимости, чтобы предоставить размер.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a>PROP_DATA_ENTRY

Указывает степень или размеры элемента управления ActiveX.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
(в) Описание свойства.

*Член*<br/>
(в) Член данных, содержащий степень; например, `m_sizeExtent`.

*vt*<br/>
(в) Определяет тип свойства VARIANT.

### <a name="remarks"></a>Remarks

Этот макрос приводит к сохранению указанного элемента данных.

При создании элемента управления ActiveX мастер вставляет этот макрос после [макроBEGIN_PROP_MAP](#begin_prop_map) карты свойств и до [того,](#end_prop_map)как макроEND_PROP_MAP карты свойств.

### <a name="example"></a>Пример

В следующем примере сохраняется степень`m_sizeExtent`объекта () .

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a>PROP_ENTRY_TYPE

Используйте этот макрос для ввода описания свойств, свойства DISPID и страницы свойств CLSID в карту свойств объекта.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
(в) Описание свойства.

*Dispid*<br/>
(в) Отель DISPID.

*clsid*<br/>
(в) CLSID страницы связанного свойства. Используйте специальное значение CLSID_NULL для свойства, не имеющем страницы связанного свойства.

*vt*<br/>
(в) Тип свойства.

### <a name="remarks"></a>Remarks

МакроPROP_ENTRYбыл, был небезопасным и обесценивался. Он был заменен на PROP_ENTRY_TYPE.

Макрос [BEGIN_PROP_MAP](#begin_prop_map) знаменует собой начало карты свойств; [END_PROP_MAP](#end_prop_map) макрос знаменует собой конец.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_PROP_MAP](#begin_prop_map).

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX

Как и [PROP_ENTRY_TYPE,](#prop_entry_type)но позволяет указать определенный IID, если объект поддерживает несколько двойных интерфейсов.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Параметры

*szDesc*<br/>
(в) Описание свойства.

*Dispid*<br/>
(в) Отель DISPID.

*clsid*<br/>
(в) CLSID страницы связанного свойства. Используйте специальное значение CLSID_NULL для свойства, не имеющем страницы связанного свойства.

*iidDispatch*<br/>
(в) IID двойного интерфейса, определяющего свойство.

*vt*<br/>
(в) Тип свойства.

### <a name="remarks"></a>Remarks

МакроPROP_ENTRY_EX был небезопасным и обесценивался. Он был заменен на PROP_ENTRY_TYPE_EX.

Макрос [BEGIN_PROP_MAP](#begin_prop_map) знаменует собой начало карты свойств; [END_PROP_MAP](#end_prop_map) макрос знаменует собой конец.

### <a name="example"></a>Пример

Следующий пример группы `IMyDual1` записей для `IMyDual2`последующего вступления в . Группировка с помощью двойного интерфейса повысит производительность.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a>PROP_PAGE

Используйте этот макрос для ввода страницы свойств CLSID в карту свойств объекта.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
(в) CLSID страницы свойств.

### <a name="remarks"></a>Remarks

PROP_PAGE похож на [PROP_ENTRY_TYPE,](#prop_entry_type)но не требует описания свойства или DISPID.

> [!NOTE]
> Если вы уже вступили в CLSID с PROP_ENTRY_TYPE или [PROP_ENTRY_TYPE_EX,](#prop_entry_type_ex)вам не нужно делать дополнительную запись с PROP_PAGE.

Макрос [BEGIN_PROP_MAP](#begin_prop_map) знаменует собой начало карты свойств; [END_PROP_MAP](#end_prop_map) макрос знаменует собой конец.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a>END_PROP_MAP

Отметка конец карты свойства объекта.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Remarks

При создании объекта с помощью Мастера проекта ATL мастер создаст пустую карту свойств, указав [BEGIN_PROP_MAP](#begin_prop_map) следуют END_PROP_MAP.

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_PROP_MAP](#begin_prop_map).

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
