---
title: Макросы категорий | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
dev_langs:
- C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc13285549543eeab07bed6372f8f7d529f90a32
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078703"
---
# <a name="category-macros"></a>Макросы категорий

Эти макросы определяют категории карт.

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Отмечает начало карты категории.|
|[END_CATEGORY_MAP](#end_category_map)|Помечает конец карты категории.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|Указывает категории, которые реализуются посредством COM-объекта.|
|[REQUIRED_CATEGORY](#required_category)|Указывает категории, которые требуются контейнера с COM-объекта.|  

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h  

##  <a name="begin_category_map"></a>  BEGIN_CATEGORY_MAP

Отмечает начало карты категории.

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
[in] Имя класса, содержащего карту категории.

### <a name="remarks"></a>Примечания

Карта категория используется для указания категорий компонентов COM-класс будет реализовывать и категорий, к которым он требует от его контейнера.

Добавить [IMPLEMENTED_CATEGORY](#implemented_category) запись на карту для каждой категории, реализованного в классе COM. Добавить [REQUIRED_CATEGORY](#required_category) запись на карту для каждой категории, классу для реализации своих клиентов. Отметить конец карты с [END_CATEGORY_MAP](#end_category_map) макрос.

Категории компонента в схеме будут автоматически регистрироваться при модуль регистрируется в том случае, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .

> [!NOTE]
>  ATL использует диспетчер категорий стандартных компонентов для регистрации категорий компонентов. Если диспетчер отсутствует в системе, при регистрации модуля, регистрация выполняется успешно, но категорий компонентов не будут регистрироваться для этого класса.

Дополнительные сведения о категории компонентов, см. в разделе [Каковы категорий компонентов и как они работают](/windows/desktop/com/component-categories-and-how-they-work) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

##  <a name="end_category_map"></a>  END_CATEGORY_MAP

Помечает конец карты категории.

```
END_CATEGORY_MAP()
```

### <a name="example"></a>Пример

См. в примере [BEGIN_CATEGORY_MAP](#begin_category_map).

##  <a name="implemented_category"></a>  IMPLEMENTED_CATEGORY

Добавление макроса IMPLEMENTED_CATEGORY к компоненту [карты категории](#begin_category_map) для указания, что он должен быть зарегистрирован как реализация категории, идентифицируемый *catID* параметра.

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Параметры

*catID*<br/>
[in] CATID константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для реализованного категории. Адрес *catID* будут выполнены и добавлены на карту. В приведенной ниже таблице для выделения из стандартных категорий.

### <a name="remarks"></a>Примечания

Категории компонента в схеме будут автоматически регистрироваться при модуль регистрируется в том случае, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать сведения о категории, зарегистрированные для класса, чтобы определить его возможности и требования без необходимости создавать его экземпляр.

Дополнительные сведения о категории компонентов, см. в разделе [Каковы категорий компонентов и как они работают](/windows/desktop/com/component-categories-and-how-they-work) в пакете Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий

|Описание|Символ|Реестр GUID|
|-----------------|------------|-------------------|
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Сложные методы связывания данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Объекты с поддержкой Интернета|См. в разделе [виду объектов Internet](/windows/desktop/com/internet-aware-objects) в пакете Windows SDK для простого списка.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

##  <a name="required_category"></a>  REQUIRED_CATEGORY

Добавление макроса REQUIRED_CATEGORY компонента [карты категории](#begin_category_map) для указания, что он должен быть зарегистрирован как требующий категории, идентифицируемый *catID* параметра.

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Параметры

*catID*<br/>
[in] CATID константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для необходимые категории. Адрес *catID* будут выполнены и добавлены на карту. В приведенной ниже таблице для выделения из стандартных категорий.

### <a name="remarks"></a>Примечания

Категории компонента в схеме будут автоматически регистрироваться при модуль регистрируется в том случае, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать сведения о категории, зарегистрированные для класса, чтобы определить его возможности и требования без необходимости создавать его экземпляр. Например элемент управления может потребоваться, что контейнер поддерживают привязку данных. Контейнер можно выяснить наличие возможности, необходимые для размещения элемента управления, запрашивая диспетчер категорий для категорий, необходимые для этого элемента управления. Если контейнер не поддерживает функцию, необходимую, она может отклонить для размещения COM-объекта.

Дополнительные сведения о категории компонентов, включая список примеров, см. в разделе [Каковы категорий компонентов и как они работают](/windows/desktop/com/component-categories-and-how-they-work) в пакете Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий

|Описание|Символ|Реестр GUID|
|-----------------|------------|-------------------|
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Сложные методы связывания данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Объекты с поддержкой Интернета|См. в разделе [виду объектов Internet](/windows/desktop/com/internet-aware-objects) в пакете Windows SDK для простого списка.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
