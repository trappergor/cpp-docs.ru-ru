---
title: "Класс CMFCRibbonPanel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::Add
- AFXRIBBONPANEL/CMFCRibbonPanel::AddSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::AddToolBar
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByData
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCaptionHeight
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCount
- AFXRIBBONPANEL/CMFCRibbonPanel::GetData
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDefaultButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDroppedDown
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElement
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElements
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElementsByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::GetGalleryRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::GetIndex
- AFXRIBBONPANEL/CMFCRibbonPanel::GetItemIDsList
- AFXRIBBONPANEL/CMFCRibbonPanel::GetName
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentCategory
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentMenuBar
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPreferedMenuLocation
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPressed
- AFXRIBBONPANEL/CMFCRibbonPanel::GetRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetVisibleElements
- AFXRIBBONPANEL/CMFCRibbonPanel::HasElement
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTest
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTestEx
- AFXRIBBONPANEL/CMFCRibbonPanel::Insert
- AFXRIBBONPANEL/CMFCRibbonPanel::InsertSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCollapsed
- AFXRIBBONPANEL/CMFCRibbonPanel::IsHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::IsJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMainPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMenuMode
- AFXRIBBONPANEL/CMFCRibbonPanel::MakeGalleryItemVisible
- AFXRIBBONPANEL/CMFCRibbonPanel::OnKey
- AFXRIBBONPANEL/CMFCRibbonPanel::RecalcWidths
- AFXRIBBONPANEL/CMFCRibbonPanel::Remove
- AFXRIBBONPANEL/CMFCRibbonPanel::RemoveAll
- AFXRIBBONPANEL/CMFCRibbonPanel::Replace
- AFXRIBBONPANEL/CMFCRibbonPanel::ReplaceByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::SetData
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementMenu
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTC
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTCByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::SetJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::SetKeys
- AFXRIBBONPANEL/CMFCRibbonPanel::ShowPopup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonPanel class
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1f833e1fa59f733734da321718d5db73377fa4bd
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonpanel-class"></a>Класс CMFCRibbonPanel
Реализует панель, содержащую набор элементов ленты. Если выводится панель, она отображает столько элементов, сколько возможно, учитывая ее размер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|Создает и инициализирует объект `CMFCRibbonPanel`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](#add)|Добавляет элемент ленты, панель.|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|Добавляет разделитель на панель ленты.|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|Добавление панели инструментов на панель ленты.|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|Возвращает элемент, определенный идентификатор указанной команды.|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|Возвращает количество элементов в панели ленты.|  
|[CMFCRibbonPanel::GetData](#getdata)|Возвращает пользовательские данные, связанные с панелью.|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|Возвращает элемент ленты, расположенный по указанному индексу.|  
|[CMFCRibbonPanel::GetElements](#getelements)|Извлекает все элементы, содержащиеся в панели ленты.|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|Возвращает прямоугольник, ограничивающий элемента коллекции.|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|Возвращает категорию родительской панели ленты.|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|Получает массив видимые элементы.|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|Вставляет элемент ленты в заданной позиции.|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|Вставляет разделитель в заданной позиции.|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|Указывает ли все элементы панели по центру (выравнивание) по вертикали, по столбцу.|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|Указывает, имеют ли все столбцы панели одинаковую ширину.|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|Прокрутка коллекции для отображения заданного элемента ленты.|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|Удаляет и при необходимости элемент, расположенный по указанному индексу.|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|Удаляет все элементы из панели ленты.|  
|[CMFCRibbonPanel::Replace](#replace)|Заменяет один элемент другому в зависимости от их значения соответствующих индексов.|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|Заменяет один элемент с другим на основании заданной команды.|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|Упорядочение панели по вертикали, выравнивание элементов по столбцу.|  
|[CMFCRibbonPanel::SetData](#setdata)|Связывает пользовательские данные с панели ленты.|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|Назначает всплывающее меню для элемента, содержащего идентификатор данной команды.|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|Добавляет элемент ленты, заданные сведения о классах предоставленный среды выполнения на панель ленты.|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|Добавляет элемент ленты, заданные сведения о классах предоставленный среды выполнения на панель ленты.|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|Устанавливает фокус на указанный элемент ленты.|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|Включает или отключает выравнивания столбцов.|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|Задает сочетание клавиш, отображающий панели ленты.|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>Примечания  
 Панели ленты — это логические группы связанных задач, созданных в категориях ленты. Размер, изменения ленты макет панели изменяется для отображения максимально возможное число элементов.  
  
 Ленту можно получить панелей, которые содержатся в нее категорию путем вызова [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel) метод.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить `CMFCRibbonPanel` объектов с помощью различных методов в `CMFCRibbonPanel` класса. В примере показано задать сочетание клавиш, который отображает панель ленты, вертикального выравнивания элементов на панели по столбцу и включить обоснование столбца. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#10;](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonPanel.h  
  
##  <a name="add"></a>CMFCRibbonPanel::Add  
 Добавляет массив элементов ленты, содержащихся на ленте панели ленты указанного элемента.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pElem`  
 Указатель на элемент ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 Добавляет разделитель на панель ленты.  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы добавить разделитель на панель ленты. Разделитель будет добавлен после элемента ленты, было добавлено в результате предыдущего вызова [CMFCRibbonPanel::Add](#add). Использование разделителей в заданной позиции, вызовите [CMFCRibbonPanel::InsertSeparator](#insertseparator).  
  
##  <a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 Добавление панели инструментов на панель ленты.  
  
```  
CMFCRibbonButtonsGroup* AddToolBar(
UINT uiToolbarResID,  
UINT uiColdResID = 0,  
UINT uiHotResID = 0,  
UINT uiDisabledResID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiToolbarResID`  
 Указывает идентификатор ресурса панели инструментов для добавления.  
  
 [in] `uiColdResID`  
 Указывает идентификатор ресурса панели инструментов холодного изображений.  
  
 [in] `uiHotResID`  
 Указывает идентификатор ресурса панели инструментов наиболее часто используемыми изображениями.  
  
 [in] `uiDisabledResID`  
 Указывает идентификатор ресурса изображения отключенные панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вызовите этот метод, чтобы добавить панель инструментов на панель ленты. Будут добавлены панели инструментов рядом с ленты элементов, добавленных с предыдущим вызовом [CMFCRibbonPanel::Add](#add).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о панели инструментов, наиболее часто используемыми изображениями, холодного изображений и изображений отключено. в разделе [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md).  
  
##  <a name="cmfcribbonpanel"></a>CMFCRibbonPanel::CMFCRibbonPanel  
 Создает и инициализирует [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md) объекта.  
  
```  
CMFCRibbonPanel(
LPCTSTR lpszName = NULL,  
HICON hIcon = NULL);  
  
CMFCRibbonPanel(CMFCRibbonGallery* pPaletteButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя панели ленты.  
  
 [in] `hIcon`  
 Дескриптор значок кнопки по умолчанию для панели ленты.  
  
 [in] `pPaletteButton`  
 Указатель на коллекцию ленты для панели ленты.  
  
##  <a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 Извлекает элемент ленты, связанный с указанными данными.  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Данные, связанные с элементом ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 Извлекает элемент ленты, определяемого по указанному идентификатору команды.  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды элемента ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент ленты, определяемый заданным Идентификатором команды; в противном случае `NULL` не элементу ribbon, идентифицируемым с идентификатором указанную команду.  
  
##  <a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 Получает высоту заголовка для панели ленты.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях заголовка для панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcount"></a>CMFCRibbonPanel::GetCount  
 Получает число элементов ленты, содержащиеся в панели ленты.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов ленты, содержащиеся в панели ленты.  
  
##  <a name="getdata"></a>CMFCRibbonPanel::GetData  
 Возвращает пользовательские данные, связанные с панелью.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемые пользователем данные, связанные с панелью.  
  
##  <a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 Извлекает кнопку по умолчанию для панели ленты.  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Кнопка по умолчанию для панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Кнопка по умолчанию отображается в том случае, если панель ленты диске недостаточно места для отображения ее элементов ленты.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 Извлекает указатель на элемент ленты, если выстроены его во всплывающем меню.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты с его во всплывающем меню выстроены; в противном случае `NULL` Если нет элемента ленты выстроены его во всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые содержатся в панели ленты.  
  
##  <a name="getelement"></a>CMFCRibbonPanel::GetElement  
 Возвращает элемент ленты, расположенный по указанному индексу.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс извлекаемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на ленте базовый элемент, расположенный в позиции `nIndex` в панель ленты или `NULL` Если элемента не существует по указанному индексу.  
  
##  <a name="getelements"></a>CMFCRibbonPanel::GetElements  
 Извлекает все элементы ленты, содержащиеся в панели ленты.  
  
```  
void GetElements(CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `arElements`  
 Массив для заполнения элементов ленты, содержащиеся в панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getelementsbyid"></a>CMFCRibbonPanel::GetElementsByID  
 Добавляет элементы ленты, которые имеют заданный идентификатор команды в указанный массив.  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды для элемента ленты.  
  
 [in] `arElements`  
 Массив элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые содержатся в панели ленты.  
  
##  <a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 Извлекает элемент ленты, будет выделен на панели ленты.  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, будет выделен на панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 Возвращает отсчитываемый от нуля индекс элемента, указанного ленты из массива элементов ленты, содержащиеся в панели ленты.  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElem`  
 Указатель на элемент ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента указанного ленты, если метод был выполнен успешно; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 Извлекает идентификаторы команд для всех элементов ленты в панели ленты.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lstItems`  
 Список идентификаторов команд для элементов ленты, содержащиеся в панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getname"></a>CMFCRibbonPanel::GetName  
 Получает имя панели ленты.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 Возвращает категорию родительской панели ленты.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на ленте категорию, которая содержит этот панель ленты.  
  
##  <a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 Возвращает прямоугольник, основное устройство отображения контекстного меню панели ленты.  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rect`  
 Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение `FALSE`. Переопределите этот метод для получения прямоугольника основное устройство отображения всплывающего меню панели ленты.  
  
##  <a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 Извлекает указатель на элемент ленты на панели ленты, если пользователь нажимает ее в настоящее время.  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если пользователь нажимает, в настоящее время. в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrect"></a>CMFCRibbonPanel::GetRect  
 Возвращает прямоугольник, отображаемое на панели ленты.  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отображаемый прямоугольник для панели ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="haselement"></a>CMFCRibbonPanel::HasElement  
 Указывает, содержит элемент указанного ленты панели ленты.  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElem`  
 Указатель на элемент ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель ленты содержит элемент указанного ленты; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="highlight"></a>CMFCRibbonPanel::Highlight  
 Задает цвет выделения для панели выбранной ленты и указанного точкой элемента ленты.  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHighlight`  
 `TRUE`Чтобы выделить панель ленты. `FALSE` для unhighlight панели ленты.  
  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hittest"></a>CMFCRibbonPanel::HitTest  
 Извлекает элемент ленты, если заданная точка находится в нем.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
CPoint point,  
BOOL bCheckPanelCaption = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`Чтобы проверить заголовок панели ленты; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если заданная точка находится в ней; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые содержатся в панели ленты.  
  
##  <a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 Возвращает отсчитываемый от нуля индекс элемента ленты, имеющий заданную точку, расположенных в ней.  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента ленты, имеющий заданную точку, расположенных в ней; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые содержатся в панели ленты.  
  
##  <a name="insert"></a>CMFCRibbonPanel::Insert  
 Вставляет элемент указанной ленты в указанной позиции в массиве элементов ленты, содержащаяся в панели ленты.  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `pElem`  
 Указатель на элемент ленты.  
  
 [in] `nIndex`  
 Отсчитываемое от нуля значение от -1 до числа элементов ленты, содержащихся в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент лента была вставлена успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если значение `nIndex` равно -1, или если `nIndex` равно количеству элементов ленты в массиве, ленты указанный элемент добавляется в конец массива. Если значение `nIndex` находится вне диапазона, метод завершится с ошибкой.  
  
##  <a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 Вставляет разделитель в заданной позиции.  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс места вставки разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если был вставлен разделитель успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для разделителей в позиции, указанной параметром `nIndex`. Для разделителей рядом с недавно добавленных элементов ленты, вызовите [CMFCRibbonPanel::AddSeparator](#addseparator).  
  
##  <a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 Указывает, центрируются ли вертикальное положение элементов ленты в прямоугольник их отображения.  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если положений по вертикали по центру элементы ленты в прямоугольник их отображения; в противном случае `FALSE`.  
  
##  <a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 Указывает, свернута ли размер отображения панели ленты в горизонтальном направлении.  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если размер отображения панели ленты свернута по горизонтали; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При сворачивании панель ленты, только отображает его кнопку по умолчанию, его имя и стрелку раскрывающегося списка.  
  
##  <a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 Указывает, выделяется ли отображение панели ленты.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если выделен отображение панели ленты; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Отображение панели ленты выделяется наведен указатель мыши.  
  
##  <a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 Указывает, задано ли размеры отображения элементы ленты, которые находятся в одном столбце на панели ленты ту же ширину.  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если размеры отображения элементы ленты, которые находятся в одном столбце на панели ленты в ту же ширину; в противном случае `FALSE`.  
  
##  <a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 Указывает, является ли панель ленты панель основных ленты.  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение `FALSE`. Переопределите этот метод, чтобы указать, является ли панель ленты панель основных ленты.  
  
 Панель ленты главного отображается, когда пользователь выбирает кнопку приложения.  
  
##  <a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onkey"></a>CMFCRibbonPanel::OnKey  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 Повторно вычисляет ширину каждого конфигурация макет экрана для панели ленты.  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели ленты.  
  
 [in] `nHeight`  
 Высота панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Панель ленты изменении конфигурации макет при изменении доступную ширину.  
  
##  <a name="remove"></a>CMFCRibbonPanel::Remove  
 Удаляет и при необходимости элемент, расположенный по указанному индексу.  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс элемента, который будет удален из панели ленты.  
  
 [in] `bDelete`  
 `TRUE`Чтобы удалить удаляемый элемент; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент удален и удалены (если `bDelete` — `TRUE`); `FALSE` Если элемент не был удален, или при наличии элемента ленты не находится в `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для удаления элемента из панели ленты.  
  
##  <a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 Удаляет все элементы ленты из панели ленты.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Все элементы ленты удаляются из панели ленты и уничтожения.  
  
##  <a name="replace"></a>CMFCRibbonPanel::Replace  
 Заменяет один элемент другому в зависимости от их значения индекса.  
  
```  
BOOL Replace(
int nIndex,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс заменяемого элемента.  
  
 [in] [out]`pElem`  
 Допустимый указатель на элемент, заменяющий исходный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если исходный элемент лента заменен успешно нового элемента ленты; `FALSE` Если элемент ленты не был заменен или отсутствует элемент по указанному индексу.  
  
### <a name="remarks"></a>Примечания  
 Чтобы заменить элемент ленты, идентификатор команды, вызовите [CMFCRibbonPanel::ReplaceByID](#replacebyid).  
  
##  <a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 Заменяет один элемент с другим на основании заданной команды.  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Указывает идентификатор команды элемента для замены.  
  
 [in] [out]`pElem`  
 Допустимый указатель на элемент, который заменит исходный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если исходный элемент лента заменен успешно нового элемента ленты; `FALSE` Если элемент ленты не был заменен или элемента с заданным Идентификатором команды не существуют.  
  
### <a name="remarks"></a>Примечания  
 Чтобы заменить элемент ленты, исходя из позиции, вызовите [CMFCRibbonPanel::Replace](#replace).  
  
##  <a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 Включает или отключает центрирование вертикальной позиции элементов ленты в прямоугольник их отображения.  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE`Чтобы центрировать вертикальной позиции элементов ленты в прямоугольник их отображения; `FALSE` для отключения этой функции.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdata"></a>CMFCRibbonPanel::SetData  
 Связывает пользовательские данные с панели ленты.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Задает определяемые пользователем данные для установки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для связывания пользовательских данных с панели ленты.  
  
##  <a name="setelementmenu"></a>CMFCRibbonPanel::SetElementMenu  
 Назначает всплывающее меню для элемента, содержащего идентификатор данной команды.  
  
```  
BOOL SetElementMenu(
UINT uiCmdID,  
HMENU hMenu,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);

 
BOOL SetElementMenu(
UINT uiCmdID,  
UINT uiMenuResID,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Указывает идентификатор команды, где добавляется меню элемента ленты.  
  
 [in] `hMenu`  
 Определяет дескриптор меню Windows, чтобы добавить на панель ленты.  
  
 [in] `bIsDefautCommand`  
 `TRUE`Чтобы указать, что команды, связанные с элементом Лента должна выполняться при нажатии элемента ленты. В этом случае меню только открывается при щелчке стрелки рядом с элементом ленты. `FALSE`Чтобы указать, не выполнена команда, связанный с элементом ленты при щелчке элемента ленты. В этом случае всплывающее меню отображается независимо от того, когда пользователь щелкает элемент.  
  
 [in] `bRightAlign`  
 `TRUE`Чтобы указать, что всплывающее меню по правому краю; в противном случае — `FALSE`.  
  
 [in] `uiMenuResID`  
 Указывает идентификатор ресурса меню, чтобы добавить на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если меню был назначен элементу ленты; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы назначить элемент ленты, который имеет идентификатор заданной команды в контекстном меню  
  
##  <a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 Добавляет элемент ленты, определяемый информация о классе предоставленный среды выполнения на панель ленты.  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс элемента ленты.  
  
 [in] [out]`pRTC`  
 Указатель на класс информацию времени выполнения для элемента ленты, который добавляется на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент ленты, который был создан с помощью сведения класса на указанную среду выполнения.  
  
### <a name="remarks"></a>Примечания  
 Если требуется добавить пользовательский элемент (например, цвет кнопки) на панель ленты, необходимо указать сведения о классе среды выполнения пользовательского элемента. Ленты хранит эту информацию, создает пользовательский элемент и заменяет существующий элемент, расположенный (определяемые) идентификатор указанной команды. Затем ленты возвращает указатель на только что созданный элемент.  
  
##  <a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 Добавляет элемент ленты, который определяется информация о классе предоставленный среды выполнения на панель ленты.  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Указывает идентификатор команды для добавления элемента ленты.  
  
 [in] [out]`pRTC`  
 Указатель на класс информацию времени выполнения, связанный с элементом ленты, который добавляется на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент ленты, который был создан с помощью сведения класса на указанную среду выполнения.  
  
### <a name="remarks"></a>Примечания  
 Если требуется добавить пользовательский элемент (например, цвет кнопки) на панель ленты, необходимо указать сведения о классе среды выполнения пользовательского элемента. Ленты хранит эту информацию, создает пользовательский элемент и заменяет существующий элемент, расположенный по указанному идентификатору команды. Затем он возвращает указатель на только что созданный элемент.  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как использовать `SetElementRTCByID` метода:  
  
```  
 
// Load and add toolbar with standard buttons. This toolbar  
// should display a custom color button with id ID_CHAR_COLOR:  
 
pPanel->AddToolBar(IDR_MAINFRAME,
    IDB_MAINFRAME256);

CMFCRibbonColorButton* pColorButton = 
(CMFCRibbonColorButton*)pPanel->SetElementRTCByID(
ID_CHAR_COLOR,
    RUNTIME_CLASS (CMFCRibbonColorButton));

 
// SetElementRTCByID sets runtime class and returns a pointer  
// to the newly created custom button,
    which can be set up immediately:  
pColorButton->EnableAutomaticButton(_T("Automatic"),
    RGB (0,
    0,
    0));  
```  
  
##  <a name="setjustifycolumns"></a>CMFCRibbonPanel::SetJustifyColumns  
 Включает или отключает корректировки ширины элементов ленты в одном столбце.  
  
```  
void SetJustifyColumns(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 `TRUE`Чтобы настроить ширину элементов ленты в тот же столбец по ширине самого большого элемента ленты в столбце; `FALSE` отключение Эта корректировка ширина.  
  
### <a name="remarks"></a>Примечания  
 При включении этой функции на панели ленты ширину элементов ленты в том же столбце корректируются по ширине самого большого элемента ленты в одном столбце.  
  
##  <a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 Задает значение свойства keytip для кнопки по умолчанию панель ленты.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszKeys`  
 Значение свойства keytip для кнопки по умолчанию панель ленты.  
  
### <a name="remarks"></a>Примечания  
 Кнопка по умолчанию отображается в том случае, если панель ленты диске недостаточно места для отображения ее элементов ленты.  
  
##  <a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 Создает и отображает контекстное меню для панели ленты.  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку по умолчанию для панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на контекстного меню панели ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Во всплывающем меню панели ленты доступна только свернутым отображение панели ленты.  
  
##  <a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 Устанавливает фокус на указанный элемент ленты.  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>Параметры  
 `pNewFocus`  
 Указатель на элемент ленты, который получает фокус.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 Прокрутка коллекции для отображения заданного элемента ленты.  
  
```  
void MakeGalleryItemVisible(CMFCRibbonBaseElement* pItem);
```  
  
### <a name="parameters"></a>Параметры  
 `pItem`  
 Указатель на элемент ленты для отображения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="iswindows7look"></a>CMFCRibbonPanel::IsWindows7Look  
 Указывает, имеет ли ленты родительского поиска (небольшое приложение прямоугольная кнопка) Windows 7.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительский ленты Windows 7 поиска; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 Извлекает массив видимые элементы.  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 `arElements`  
 Когда функция возвращает значение, данный параметр содержит массив видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 Возвращает прямоугольник, ограничивающий элемента коллекции.  
  
```  
CRect GetGalleryRect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер и положение элемента коллекции в пределах этой панели.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfocused"></a>CMFCRibbonPanel::GetFocused  
 Возвращает элемент, имеющий фокус ввода.  
  
```  
CMFCRibbonBaseElement* GetFocused() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с фокусом ввода или `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Класс CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

