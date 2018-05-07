---
title: Категория макросы | Документы Microsoft
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
ms.openlocfilehash: b1eba97ef5253041752d4b8abfcd6ea7300b8492
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="category-macros"></a>Макросы категории
Эти макросы определяют категории карты.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Отмечает начало карты категории.|  
|[END_CATEGORY_MAP](#end_category_map)|Отмечает конец карты категории.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|Указывает категории, реализуемые COM-объекта.|  
|[REQUIRED_CATEGORY](#required_category)|Указывает категории, которые требуются контейнера COM-объектом.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  

##  <a name="begin_category_map"></a>  BEGIN_CATEGORY_MAP  
 Отмечает начало карты категории.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Имя класса, содержащего схему категории.  
  
### <a name="remarks"></a>Примечания  
 Категория карта используется указание категорий компонентов COM-класс будет реализовывать и категорий, он требует от своего контейнера.  
  
 Добавить [IMPLEMENTED_CATEGORY](#implemented_category) запись в сопоставление для каждой категории, реализованный в COM-класс. Добавить [REQUIRED_CATEGORY](#required_category) входа на карте для каждой категории, класс требует, чтобы реализовать его клиенты. Отметить конец карты с [END_CATEGORY_MAP](#end_category_map) макрос.  
  
 Категории компонентов, перечисленный в карте будет зарегистрирована автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .  
  
> [!NOTE]
>  ATL использует диспетчер категорий стандартный компонент для регистрации категорий компонентов. Если диспетчер не находится в системе, при регистрации модуля, регистрация выполняется успешно, но категории компонентов не будут регистрироваться для этого класса.  
  
 Дополнительные сведения о категории компонентов см. в разделе [Каковы категории компонентов, и принципы их работы](http://msdn.microsoft.com/library/windows/desktop/ms694322) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>  END_CATEGORY_MAP  
 Отмечает конец карты категории.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="implemented_category"></a>  IMPLEMENTED_CATEGORY  
 Добавить `IMPLEMENTED_CATEGORY` макрос к компоненту [карты категории](#begin_category_map) для указания, должен быть зарегистрирован как реализация категории, обозначенную `catID` параметра.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Параметры  
 `catID`  
 [in] Объект **CATID** константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для категории реализовано. Адрес `catID` будут выполнены и добавляются на карту. В приведенной ниже таблице для выбора из стандартных категорий.  
  
### <a name="remarks"></a>Примечания  
 Категории компонентов, перечисленный в карте будет зарегистрирована автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.  
  
 Клиенты могут использовать сведения о категории, зарегистрированные для класса для определения его возможности и требования без необходимости создавать его экземпляр.  
  
 Дополнительные сведения о категории компонентов см. в разделе [Каковы категории компонентов, и принципы их работы](http://msdn.microsoft.com/library/windows/desktop/ms694322) в Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий  
  
|Описание|Символ|Идентификатор GUID реестра|  
|-----------------|------------|-------------------|  
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Объекты с поддержкой Интернета|В разделе [виду объектов Интернет](http://msdn.microsoft.com/library/windows/desktop/ms690561) в Windows SDK для простого списка.||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>  REQUIRED_CATEGORY  
 Добавить `REQUIRED_CATEGORY` макрос к компоненту [карты категории](#begin_category_map) для указания, должен быть зарегистрирован как требующее категории, обозначенную `catID` параметра.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Параметры  
 `catID`  
 [in] Объект **CATID** константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для необходимая категория. Адрес `catID` будут выполнены и добавляются на карту. В приведенной ниже таблице для выбора из стандартных категорий.  
  
### <a name="remarks"></a>Примечания  
 Категории компонентов, перечисленный в карте будет зарегистрирована автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.  
  
 Клиенты могут использовать сведения о категории, зарегистрированные для класса для определения его возможности и требования без необходимости создавать его экземпляр. Например элемент управления может потребоваться, что контейнер поддерживают привязку данных. Контейнер можно выяснить наличие возможности, необходимые для размещения элемента управления, запрашивая диспетчер категории для категорий, необходимые для этого элемента управления. Если контейнер не поддерживает функцию, необходимую, может отказаться размещения COM-объекта.  
  
 Дополнительные сведения о категории компонентов, включая список примеров, в разделе [Каковы категории компонентов, и принципы их работы](http://msdn.microsoft.com/library/windows/desktop/ms694322) в Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий  
  
|Описание|Символ|Идентификатор GUID реестра|  
|-----------------|------------|-------------------|  
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Объекты с поддержкой Интернета|В разделе [виду объектов Интернет](http://msdn.microsoft.com/library/windows/desktop/ms690561) в Windows SDK для простого списка.||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
