---
title: Категория Макрос
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CATEGORY_MAP
- atlcom/ATL::END_CATEGORY_MAP
- atlcom/ATL::IMPLEMENTED_CATEGORY
- atlcom/ATL::REQUIRED_CATEGORY
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
ms.openlocfilehash: 1d8bbae4608aa661bbc612604f7d85855f325f5f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321601"
---
# <a name="category-macros"></a>Категория Макрос

Эти макросы определяют карты категорий.

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Отметка начала карты категории.|
|[END_CATEGORY_MAP](#end_category_map)|Отметки конца карты категории.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|Отосеяна категория, реализованная объектом COM.|
|[REQUIRED_CATEGORY](#required_category)|Отосеяна категория, требуемая от контейнера объектом COM.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_category_map"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP

Отметка начала карты категории.

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
(в) Название класса, содержащего карту категории.

### <a name="remarks"></a>Remarks

Карта категорий используется для определения того, какие категории компонентов будет реализовывать класс COM и какие категории он требует от своего контейнера.

Добавьте [IMPLEMENTED_CATEGORY](#implemented_category) запись на карту для каждой категории, реализованной классом COM. Добавьте [REQUIRED_CATEGORY](#required_category) запись на карту для каждой категории, которую класс требует от своих клиентов реализовать. Отметьте конец карты с помощью [макроса END_CATEGORY_MAP.](#end_category_map)

Категории компонентов, перечисленные на карте, будут автоматически зарегистрированы, если модуль зарегистрирован, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto)

> [!NOTE]
> ATL использует менеджера стандартных категорий компонентов для регистрации категорий компонентов. Если менеджер не присутствует в системе при регистрации модуля, регистрация удалась, но категории компонентов не будут зарегистрированы для этого класса.

Для получения дополнительной информации о категориях компонентов см., [что такое категории компонентов и как они работают](/windows/win32/com/component-categories-and-how-they-work) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="end_category_map"></a><a name="end_category_map"></a>END_CATEGORY_MAP

Отметки конца карты категории.

```
END_CATEGORY_MAP()
```

### <a name="example"></a>Пример

Смотрите пример [для BEGIN_CATEGORY_MAP](#begin_category_map).

## <a name="implemented_category"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY

Добавьте IMPLEMENTED_CATEGORY макрос амебиоток на [карту категории](#begin_category_map) компонента, чтобы указать, что он должен быть зарегистрирован как реализация категории, идентифицированной параметром *catID.*

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Параметры

*catID*<br/>
(в) Постоянный или переменный CATID с уникальным идентификатором (GUID) для реализованной категории. Адрес *catID* будет взят и добавлен на карту. Смотрите таблицу ниже для выбора фондовых категорий.

### <a name="remarks"></a>Remarks

Категории компонентов, перечисленные на карте, будут автоматически зарегистрированы, если модуль зарегистрирован, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать информацию о категории, зарегистрированную для класса, для определения его возможностей и требований без необходимости создания экземпляра.

Для получения дополнительной информации о категориях компонентов см., [что такое категории компонентов и как они работают](/windows/win32/com/component-categories-and-how-they-work) в SDK Windows.

### <a name="a-selection-of-stock-categories"></a>Выбор фондовых категорий

|Описание|Символ|Реестр GUID|
|-----------------|------------|-------------------|
|Безопасный для сценариев|CATID_SafeForScripting|7DD95801-9882-11CF-9FA9-00AA06C42C4|
|Безопасный для инициализации|CATID_SafeForInitializing|7DD95802-9882-11CF-9FA9-00AA06C42C4|
|Простой кадр сайта сдерживание|CATID_SimpleFrameControl|157083E0-2368-11cf-87B9-00AA006C8166|
|простую привязку данных|CATID_PropertyNotifyControl|157083E1-2368-11cf-87B9-00AA006C8166|
|Расширенная связывание данных|CATID_VBDataBound|157083E2-2368-11cf-87B9-00AA006C8166|
|Элементы управления без окон|CATID_WindowlessObject|1D06B600-3AE3-11cf-87B9-00AA006C8166|
|Объекты, осведомленные об Интернете|Для списка примеров можно ознакомиться с [объектами информирования](/windows/win32/com/internet-aware-objects) об Интернете в SDK Windows.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

## <a name="required_category"></a><a name="required_category"></a>REQUIRED_CATEGORY

Добавьте REQUIRED_CATEGORY макроса к [карте категории](#begin_category_map) компонента, чтобы указать, что он должен быть зарегистрирован как требующий категории, определенной параметром *catID.*

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Параметры

*catID*<br/>
(в) Постоянный или переменный CATID с уникальным идентификатором (GUID) для требуемой категории. Адрес *catID* будет взят и добавлен на карту. Смотрите таблицу ниже для выбора фондовых категорий.

### <a name="remarks"></a>Remarks

Категории компонентов, перечисленные на карте, будут автоматически зарегистрированы, если модуль зарегистрирован, если класс имеет связанный [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.

Клиенты могут использовать информацию о категории, зарегистрированную для класса, для определения его возможностей и требований без необходимости создания экземпляра. Например, для элемента управления может потребоваться привязка данных контейнерной поддержки. Контейнер может узнать, есть ли у него возможности, необходимые для размещения элемента управления, задав запрос менеджеру категории для категорий, требуемых этим управлением. Если контейнер не поддерживает требуемую функцию, он может отказатьву от размещения объекта COM.

Для получения дополнительной информации о категориях [What are Component Categories and how do they work](/windows/win32/com/component-categories-and-how-they-work) компонентов, включая список выборок, см.

### <a name="a-selection-of-stock-categories"></a>Выбор фондовых категорий

|Описание|Символ|Реестр GUID|
|-----------------|------------|-------------------|
|Безопасный для сценариев|CATID_SafeForScripting|7DD95801-9882-11CF-9FA9-00AA06C42C4|
|Безопасный для инициализации|CATID_SafeForInitializing|7DD95802-9882-11CF-9FA9-00AA06C42C4|
|Простой кадр сайта сдерживание|CATID_SimpleFrameControl|157083E0-2368-11cf-87B9-00AA006C8166|
|простую привязку данных|CATID_PropertyNotifyControl|157083E1-2368-11cf-87B9-00AA006C8166|
|Расширенная связывание данных|CATID_VBDataBound|157083E2-2368-11cf-87B9-00AA006C8166|
|Элементы управления без окон|CATID_WindowlessObject|1D06B600-3AE3-11cf-87B9-00AA006C8166|
|Объекты, осведомленные об Интернете|Для списка примеров можно ознакомиться с [объектами информирования](/windows/win32/com/internet-aware-objects) об Интернете в SDK Windows.||

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
