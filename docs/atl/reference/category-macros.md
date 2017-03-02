---
title: "Категория макросы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 26eea5cc8ce8e18af84a9ca89e5ddc94272be44c
ms.lasthandoff: 02/24/2017

---
# <a name="category-macros"></a>Макросы категории
Эти макросы определить категории карт.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Отмечает начало карты категории.|  
|[END_CATEGORY_MAP](#end_category_map)|Отмечает конец карты категории.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|Указывает категории, реализуемые COM-объекта.|  
|[REQUIRED_CATEGORY](#required_category)|Указывает категории, которые требуются контейнера COM-объектом.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  

##  <a name="a-namebegincategorymapa--begincategorymap"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP  
 Отмечает начало карты категории.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Имя класса, содержащего схему категории.  
  
### <a name="remarks"></a>Примечания  
 Карта категория используется для указания категорий компонентов COM класс реализует и категорий, к которым он требует от его контейнера.  
  
 Добавить [IMPLEMENTED_CATEGORY](#implemented_category) запись карту для каждой категории, реализованный COM-класса. Добавить [REQUIRED_CATEGORY](#required_category) запись в сопоставление для каждой категории, классу требуется для реализации своих клиентов. Конец карты с [END_CATEGORY_MAP](#end_category_map) макрос.  
  
 Категории компонентов, перечисленных в сопоставлении регистрируются автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto).  
  
> [!NOTE]
>  Диспетчер категорий стандартный компонент использует ATL для регистрации категории компонентов. Если менеджер не присутствует в системе, при регистрации модуля, регистрация прошла успешно, но для этого класса не будет зарегистрирована категории компонентов.  
  
 Дополнительные сведения о категории компонентов см. в разделе [Каковы категории компонентов и как они работают](http://msdn.microsoft.com/library/windows/desktop/ms694322) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="a-nameendcategorymapa--endcategorymap"></a><a name="end_category_map"></a>END_CATEGORY_MAP  
 Отмечает конец карты категории.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Пример  
 В примере показано [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="a-nameimplementedcategorya--implementedcategory"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY  
 Добавить `IMPLEMENTED_CATEGORY` макрос к компоненту [карты категории](#begin_category_map) для указания, должен быть зарегистрирован как реализация категории, идентифицируемый `catID` параметр.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Параметры  
 `catID`  
 [in] Объект **CATID** константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для категории реализовано. Адрес `catID` будут выполнены и добавляются на карту. Выбор из стандартных категорий см.  
  
### <a name="remarks"></a>Примечания  
 Категории компонентов, перечисленных в сопоставлении регистрируются автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.  
  
 Клиенты могут использовать сведения о категории, зарегистрированные для класса для определения его возможности и требования без необходимости создавать его экземпляр.  
  
 Дополнительные сведения о категории компонентов см. в разделе [Каковы категории компонентов и как они работают](http://msdn.microsoft.com/library/windows/desktop/ms694322) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий  
  
|Описание|Символ|Реестр идентификатор GUID|  
|-----------------|------------|-------------------|  
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Объекты с поддержкой Интернета|В разделе [виду объектов Internet](http://msdn.microsoft.com/library/windows/desktop/ms690561) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для простого списка.||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="a-namerequiredcategorya--requiredcategory"></a><a name="required_category"></a>REQUIRED_CATEGORY  
 Добавить `REQUIRED_CATEGORY` макрос к компоненту [карты категории](#begin_category_map) для указания, что он должен быть зарегистрирован как требующий категории, идентифицируемый `catID` параметр.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Параметры  
 `catID`  
 [in] Объект **CATID** константой или переменной, содержащей глобальный уникальный идентификатор (GUID) для категории «обязательные». Адрес `catID` будут выполнены и добавляются на карту. Выбор из стандартных категорий см.  
  
### <a name="remarks"></a>Примечания  
 Категории компонентов, перечисленных в сопоставлении регистрируются автоматически при регистрации модуля, если класс имеет связанный с ним [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) или [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) макрос.  
  
 Клиенты могут использовать сведения о категории, зарегистрированные для класса для определения его возможности и требования без необходимости создавать его экземпляр. Например элемент управления может потребоваться, что контейнер поддерживают привязку данных. Контейнер можно выяснить наличие возможности, необходимые для размещения элемента управления с помощью запроса manager категории для категорий, необходимые для этого элемента управления. Если контейнер не поддерживает необходимые функции, она может отклонить для размещения COM-объекта.  
  
 Дополнительные сведения о категории компонентов, включая список примеров, в разделе [Каковы категории компонентов и как они работают](http://msdn.microsoft.com/library/windows/desktop/ms694322) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="a-selection-of-stock-categories"></a>Выбор из стандартных категорий  
  
|Описание|Символ|Реестр идентификатор GUID|  
|-----------------|------------|-------------------|  
|Безопасно для сценариев|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Безопасно для инициализации|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Простая рамка сайта вложения|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|простую привязку данных|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Расширенная привязка данных|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Элементы управления без окон|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Объекты с поддержкой Интернета|В разделе [виду объектов Internet](http://msdn.microsoft.com/library/windows/desktop/ms690561) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для простого списка.||  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#135;](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

