---
title: "Класс CMFCRibbonButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButton class
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 08672f10cf67a773f2af8d12130c4e3f5b497e11
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbutton-class"></a>Класс CMFCRibbonButton
Класс `CMFCRibbonButton` реализует кнопки, которые можно размещать на элементах ленты, например на панелях, панелях быстрого доступа и во всплывающих меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonButton::CMFCRibbonButton](#cmfcribbonbutton)|Создает объект "кнопка ленты".|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonButton::AddSubItem](#addsubitem)|Добавляет во всплывающее меню элемент, связанный с кнопкой.|  
|[CMFCRibbonButton::CanBeStretched](#canbestretched)|(Переопределяет [CMFCRibbonBaseElement::CanBeStretched](../../mfc/reference/cmfcribbonbaseelement-class.md#canbestretched).)|  
|[CMFCRibbonButton::CleanUpSizes](#cleanupsizes)|(Переопределяет [CMFCRibbonBaseElement::CleanUpSizes](../../mfc/reference/cmfcribbonbaseelement-class.md#cleanupsizes).)|  
|[CMFCRibbonButton::ClosePopupMenu](#closepopupmenu)|(Переопределяет [CMFCRibbonBaseElement::ClosePopupMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#closepopupmenu).)|  
|[CMFCRibbonButton::DrawBottomText](#drawbottomtext)||  
|[CMFCRibbonButton::DrawImage](#drawimage)|(Переопределяет [CMFCRibbonBaseElement::DrawImage](../../mfc/reference/cmfcribbonbaseelement-class.md#drawimage).)|  
|[CMFCRibbonButton::DrawRibbonText](#drawribbontext)||  
|[CMFCRibbonButton::FindSubItemIndexByID](#findsubitemindexbyid)|Возвращает индекс элемента всплывающего меню, связанного с указанным идентификатором команды.|  
|[CMFCRibbonButton::GetCommandRect](#getcommandrect)||  
|[CMFCRibbonButton::GetCompactSize](#getcompactsize)|Возвращает компактный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetCompactSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getcompactsize).)|  
|[CMFCRibbonButton::GetIcon](#geticon)||  
|[CMFCRibbonButton::GetImageIndex](#getimageindex)|Возвращает индекс изображения, связанного с кнопкой.|  
|[CMFCRibbonButton::GetImageSize](#getimagesize)|Возвращает размер изображения элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButton::GetIntermediateSize](#getintermediatesize)|Возвращает размер элемента ленты в промежуточное состояние. (Переопределяет [CMFCRibbonBaseElement::GetIntermediateSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getintermediatesize).)|  
|[CMFCRibbonButton::GetMenu](#getmenu)|Возвращает дескриптор меню Windows, назначенному кнопке ленты.|  
|[CMFCRibbonButton::GetMenuRect](#getmenurect)||  
|[CMFCRibbonButton::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButton::GetSubItems](#getsubitems)||  
|[CMFCRibbonButton::GetTextRowHeight](#gettextrowheight)||  
|[CMFCRibbonButton::GetToolTipText](#gettooltiptext)|Возвращает текст всплывающей подсказки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::GetToolTipText](../../mfc/reference/cmfcribbonbaseelement-class.md#gettooltiptext).)|  
|[CMFCRibbonButton::HasCompactMode](#hascompactmode)|Задает, доступен ли для элемента ленты компактный режим. (Переопределяет [CMFCRibbonBaseElement::HasCompactMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hascompactmode).)|  
|[CMFCRibbonButton::HasIntermediateMode](#hasintermediatemode)|Задает, доступен ли для элемента ленты промежуточный режим. (Переопределяет [CMFCRibbonBaseElement::HasIntermediateMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hasintermediatemode).)|  
|[CMFCRibbonButton::HasLargeMode](#haslargemode)|Определяет, доступен ли для элемента ленты крупный режим. (Переопределяет [CMFCRibbonBaseElement::HasLargeMode](../../mfc/reference/cmfcribbonbaseelement-class.md#haslargemode).)|  
|[CMFCRibbonButton::HasMenu](#hasmenu)|(Переопределяет [CMFCRibbonBaseElement::HasMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#hasmenu).)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](#isalwaysdrawborder)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](#isalwayslargeimage)|(Переопределяет [CMFCRibbonBaseElement::IsAlwaysLargeImage](../../mfc/reference/cmfcribbonbaseelement-class.md#isalwayslargeimage).)|  
|[CMFCRibbonButton::IsApplicationButton](#isapplicationbutton)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](#iscommandareahighlighted)||  
|[CMFCRibbonButton::IsDefaultCommand](#isdefaultcommand)|Определяет, доступна ли для кнопки ленты команда по умолчанию.|  
|[CMFCRibbonButton::IsDefaultPanelButton](#isdefaultpanelbutton)||  
|[CMFCRibbonButton::IsDrawTooltipImage](#isdrawtooltipimage)||  
|[CMFCRibbonButton::IsLargeImage](#islargeimage)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](#ismenuareahighlighted)||  
|[CMFCRibbonButton::IsMenuOnBottom](#ismenuonbottom)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](#ispopupdefaultmenulook)||  
|[CMFCRibbonButton::IsRightAlignMenu](#isrightalignmenu)|Определяет, выровнено ли меню по правому краю.|  
|[CMFCRibbonButton::IsSingleLineText](#issinglelinetext)||  
|[CMFCRibbonButton::OnCalcTextSize](#oncalctextsize)|(Переопределяет [CMFCRibbonBaseElement::OnCalcTextSize](../../mfc/reference/cmfcribbonbaseelement-class.md#oncalctextsize).)|  
|[CMFCRibbonButton::OnDrawBorder](#ondrawborder)||  
|[CMFCRibbonButton::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonButton::OnFillBackground](#onfillbackground)||  
|[CMFCRibbonButton::RemoveAllSubItems](#removeallsubitems)|Удаляет из всплывающего меню все элементы.|  
|[CMFCRibbonButton::RemoveSubItem](#removesubitem)|Удаляет элемент из всплывающего меню.|  
|[CMFCRibbonButton::SetACCData](#setaccdata)|(Переопределяет [CMFCRibbonBaseElement::SetACCData](../../mfc/reference/cmfcribbonbaseelement-class.md#setaccdata).)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](#setalwayslargeimage)|Задает размер свернутой кнопки: крупная или малая.|  
|[CMFCRibbonButton::SetDefaultCommand](#setdefaultcommand)|Делает для кнопки ленты доступной команду по умолчанию.|  
|[CMFCRibbonButton::SetDescription](#setdescription)|Задает описание элемента ленты. (Переопределяет [CMFCRibbonBaseElement::SetDescription](../../mfc/reference/cmfcribbonbaseelement-class.md#setdescription).)|  
|[CMFCRibbonButton::SetImageIndex](#setimageindex)|Назначает индекс изображению кнопки.|  
|[CMFCRibbonButton::SetMenu](#setmenu)|Назначает всплывающее меню кнопке ленты.|  
|[CMFCRibbonButton::SetParentCategory](#setparentcategory)|(Переопределяет [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
|[CMFCRibbonButton::SetRightAlignMenu](#setrightalignmenu)|Располагает всплывающее меню справа от кнопки.|  
|[CMFCRibbonButton::SetText](#settext)|Задает текст элемента ленты. (Переопределяет [CMFCRibbonBaseElement::SetText](../../mfc/reference/cmfcribbonbaseelement-class.md#settext).)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonButton::OnClick](#onclick)|Вызывается платформой по нажатию кнопки.|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных методов класса `CMFCRibbonButton`. Показывается создание объекта класса `CMFCRibbonButton`, назначение всплывающего меню кнопке ленты, назначение кнопке описания, удаление элемента из всплывающего меню, а также расположение всплывающего меню справа от края кнопки.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_1.cpp)]  
  
## <a name="remarks"></a>Примечания  
 Для использования кнопки на ленте в приложении, конструируется объект кнопки и добавьте его в нужную ленту [панель](../../mfc/reference/cmfcribbonpanel-class.md).  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"), // Panel name  
    m_PanelIcons.ExtractIcon (0)); // Panel icon  

// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton = 
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);

// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);

// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));
```  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonbutton.h  
  
##  <a name="a-nameaddsubitema--cmfcribbonbuttonaddsubitem"></a><a name="addsubitem"></a>CMFCRibbonButton::AddSubItem  
 Добавляет во всплывающее меню элемент, связанный с кнопкой.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pSubItem`  
 Задает указатель на новый элемент для добавления.  
  
 [in] `nIndex`  
 Указывает индекс, по которому следует добавить элемент в массив элементов меню кнопки. значение -1, добавьте элемент в конец массива элементов меню.  
  
##  <a name="a-namecanbestretcheda--cmfcribbonbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCRibbonButton::CanBeStretched  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecleanupsizesa--cmfcribbonbuttoncleanupsizes"></a><a name="cleanupsizes"></a>CMFCRibbonButton::CleanUpSizes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameclosepopupmenua--cmfcribbonbuttonclosepopupmenu"></a><a name="closepopupmenu"></a>CMFCRibbonButton::ClosePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecmfcribbonbuttona--cmfcribbonbuttoncmfcribbonbutton"></a><a name="cmfcribbonbutton"></a>CMFCRibbonButton::CMFCRibbonButton  
 Создает объект "кнопка ленты".  
  
```  
CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1,  
    BOOL bAlwaysShowDescription=FALSE);

CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon,  
    BOOL bAlwaysShowDescription=FALSE,  
    HICON hIconSmall=NULL,  
    BOOL bAutoDestroyIcon=FALSE,  
    BOOL bAlphaBlendIcon=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Указывает идентификатор команды кнопки.  
  
 [in] `lpszText`  
 Задает текст метки кнопки.  
  
 [in] `nSmallImageIndex`  
 Задает отсчитываемый от нуля индекс небольшое изображение кнопки в списке изображений родительской категории.  
  
 [in] `nLargeImageIndex`  
 Задает отсчитываемый от нуля индекс кнопки большого изображения в списке изображений родительской категории.  
  
 [in] `hIcon`  
 Указывает дескриптор значка, который приложение использует в качестве изображения кнопки.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCRibbonButton` объекта.  
  
 [!code-cpp[NVC_MFC_RibbonApp №&6;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_2.cpp)]  
  
##  <a name="a-namedrawbottomtexta--cmfcribbonbuttondrawbottomtext"></a><a name="drawbottomtext"></a>CMFCRibbonButton::DrawBottomText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CSize DrawBottomText(
    CDC* pDC,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawimagea--cmfcribbonbuttondrawimage"></a><a name="drawimage"></a>CMFCRibbonButton::DrawImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `type`  
 [in] `rectImage`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawribbontexta--cmfcribbonbuttondrawribbontext"></a><a name="drawribbontext"></a>CMFCRibbonButton::DrawRibbonText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int DrawRibbonText(
    CDC* pDC,  
    const CString& strText,  
    CRect rectText,  
    UINT uiDTFlags,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `strText`  
 [in] `rectText`  
 [in] `uiDTFlags`  
 [in] `clrText`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindsubitemindexbyida--cmfcribbonbuttonfindsubitemindexbyid"></a><a name="findsubitemindexbyid"></a>CMFCRibbonButton::FindSubItemIndexByID  
 Возвращает индекс элемента всплывающего меню, связанного с указанным идентификатором команды.  
  
```  
int FindSubItemIndexByID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Указывает идентификатор команды элемента во всплывающем меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс вложенным элементом, с которым связан `uiID`. -1, если такой вложенный элемент.  
  
##  <a name="a-namegetcommandrecta--cmfcribbonbuttongetcommandrect"></a><a name="getcommandrect"></a>CMFCRibbonButton::GetCommandRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetCommandRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcompactsizea--cmfcribbonbuttongetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonButton::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegeticona--cmfcribbonbuttongeticon"></a><a name="geticon"></a>CMFCRibbonButton::GetIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HICON GetIcon(BOOL bLargeIcon = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bLargeIcon`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetimageindexa--cmfcribbonbuttongetimageindex"></a><a name="getimageindex"></a>CMFCRibbonButton::GetImageIndex  
 Возвращает индекс изображения, связанного с кнопкой.  
  
```  
int GetImageIndex(BOOL bLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bLargeImage`  
 Если `TRUE`, возвращает индекс изображения в списке изображений, который содержит большие изображения; в противном случае возвращает индекс изображения в списке изображений, содержащий маленькие изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения кнопки в список связанных изображений.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbuttongetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButton::GetImageSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetImageSize(RibbonImageType type) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `type`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetintermediatesizea--cmfcribbonbuttongetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonButton::GetIntermediateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetmenua--cmfcribbonbuttongetmenu"></a><a name="getmenu"></a>CMFCRibbonButton::GetMenu  
 Возвращает дескриптор меню Windows, назначенному кнопке ленты.  
  
```  
HMENU GetMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор меню Windows, назначенные для кнопки. `NULL` Если нет меню не назначен.  
  
##  <a name="a-namegetmenurecta--cmfcribbonbuttongetmenurect"></a><a name="getmenurect"></a>CMFCRibbonButton::GetMenuRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetMenuRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetregularsizea--cmfcribbonbuttongetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButton::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetsubitemsa--cmfcribbonbuttongetsubitems"></a><a name="getsubitems"></a>CMFCRibbonButton::GetSubItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& GetSubItems() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettextrowheighta--cmfcribbonbuttongettextrowheight"></a><a name="gettextrowheight"></a>CMFCRibbonButton::GetTextRowHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTextRowHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettooltiptexta--cmfcribbonbuttongettooltiptext"></a><a name="gettooltiptext"></a>CMFCRibbonButton::GetToolTipText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehascompactmodea--cmfcribbonbuttonhascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonButton::HasCompactMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehasintermediatemodea--cmfcribbonbuttonhasintermediatemode"></a><a name="hasintermediatemode"></a>CMFCRibbonButton::HasIntermediateMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehaslargemodea--cmfcribbonbuttonhaslargemode"></a><a name="haslargemode"></a>CMFCRibbonButton::HasLargeMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehasmenua--cmfcribbonbuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonButton::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisalwaysdrawbordera--cmfcribbonbuttonisalwaysdrawborder"></a><a name="isalwaysdrawborder"></a>CMFCRibbonButton::IsAlwaysDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysDrawBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisalwayslargeimagea--cmfcribbonbuttonisalwayslargeimage"></a><a name="isalwayslargeimage"></a>CMFCRibbonButton::IsAlwaysLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisapplicationbuttona--cmfcribbonbuttonisapplicationbutton"></a><a name="isapplicationbutton"></a>CMFCRibbonButton::IsApplicationButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsApplicationButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiscommandareahighlighteda--cmfcribbonbuttoniscommandareahighlighted"></a><a name="iscommandareahighlighted"></a>CMFCRibbonButton::IsCommandAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsCommandAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdefaultcommanda--cmfcribbonbuttonisdefaultcommand"></a><a name="isdefaultcommand"></a>CMFCRibbonButton::IsDefaultCommand  
 Указывает, включена ли команда по умолчанию для кнопки на ленте.  
  
```  
BOOL IsDefaultCommand() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена команда по умолчанию для кнопки на ленте; `FALSE` в противном случае.  
  
##  <a name="a-nameisdefaultpanelbuttona--cmfcribbonbuttonisdefaultpanelbutton"></a><a name="isdefaultpanelbutton"></a>CMFCRibbonButton::IsDefaultPanelButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultPanelButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdrawtooltipimagea--cmfcribbonbuttonisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonButton::IsDrawTooltipImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameislargeimagea--cmfcribbonbuttonislargeimage"></a><a name="islargeimage"></a>CMFCRibbonButton::IsLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLargeImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameismenuareahighlighteda--cmfcribbonbuttonismenuareahighlighted"></a><a name="ismenuareahighlighted"></a>CMFCRibbonButton::IsMenuAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsMenuAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameismenuonbottoma--cmfcribbonbuttonismenuonbottom"></a><a name="ismenuonbottom"></a>CMFCRibbonButton::IsMenuOnBottom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuOnBottom() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameispopupdefaultmenulooka--cmfcribbonbuttonispopupdefaultmenulook"></a><a name="ispopupdefaultmenulook"></a>CMFCRibbonButton::IsPopupDefaultMenuLook  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsPopupDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisrightalignmenua--cmfcribbonbuttonisrightalignmenu"></a><a name="isrightalignmenu"></a>CMFCRibbonButton::IsRightAlignMenu  
 Указывает, является ли меню по правому краю.  
  
```  
BOOL IsRightAlignMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если меню по правому краю; в противном случае `FALSE`.  
  
##  <a name="a-nameissinglelinetexta--cmfcribbonbuttonissinglelinetext"></a><a name="issinglelinetext"></a>CMFCRibbonButton::IsSingleLineText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsSingleLineText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoncalctextsizea--cmfcribbonbuttononcalctextsize"></a><a name="oncalctextsize"></a>CMFCRibbonButton::OnCalcTextSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonclicka--cmfcribbonbuttononclick"></a><a name="onclick"></a>CMFCRibbonButton::OnClick  
 Вызывается платформой по нажатию кнопки.  
  
```  
virtual void OnClick(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Задает положение щелчка мыши.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если требуется обработать это событие.  
  
##  <a name="a-nameondrawa--cmfcribbonbuttonondraw"></a><a name="ondraw"></a>CMFCRibbonButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawbordera--cmfcribbonbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonButton::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonfillbackgrounda--cmfcribbonbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonButton::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremoveallsubitemsa--cmfcribbonbuttonremoveallsubitems"></a><a name="removeallsubitems"></a>CMFCRibbonButton::RemoveAllSubItems  
 Удаляет из всплывающего меню все элементы.  
  
```  
void RemoveAllSubItems();
```  
  
##  <a name="a-nameremovesubitema--cmfcribbonbuttonremovesubitem"></a><a name="removesubitem"></a>CMFCRibbonButton::RemoveSubItem  
 Удаляет элемент из всплывающего меню.  
  
```  
BOOL RemoveSubItem(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс элемента меню, который требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанный элемент был удален успешно; в противном случае `FALSE` Если `nIndex` меньше нуля или превышает число элементов меню в контекстном меню.  
  
##  <a name="a-namesetaccdataa--cmfcribbonbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonButton::SetACCData  
 Задает данные специальных возможностей для кнопки ленты.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);  
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Родительское окно для элемента ленты.  
  
 `data`  
 Данные специальных возможностей для элемента ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `TRUE` , если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetalwayslargeimagea--cmfcribbonbuttonsetalwayslargeimage"></a><a name="setalwayslargeimage"></a>CMFCRibbonButton::SetAlwaysLargeImage  
 Задает размер свернутой кнопки: крупная или малая.  
  
```  
void SetAlwaysLargeImage(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 Если `TRUE`, на кнопке отображается большое изображение. В противном случае — кнопка отображает небольшое изображение.  
  
##  <a name="a-namesetdefaultcommanda--cmfcribbonbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFCRibbonButton::SetDefaultCommand  
 Делает для кнопки ленты доступной команду по умолчанию.  
  
```  
void SetDefaultCommand(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 Если `TRUE`, можно выполнять команды по умолчанию кнопка. Если `FALSE`, не может выполнять команды по умолчанию кнопка.  
  
### <a name="remarks"></a>Примечания  
 `bSet`действителен только в том случае, если кнопка имеет меню. Если `bSet` — `TRUE`, можно выполнять команды по умолчанию кнопка и назначенный во всплывающем меню отображается только в том случае, когда пользователь щелкает стрелку справа от кнопки. В противном случае — не может выполнять команды по умолчанию кнопка и во всплывающем меню отображается независимо от того, какие области кнопки пользователь нажимает кнопку.  
  
##  <a name="a-namesetdescriptiona--cmfcribbonbuttonsetdescription"></a><a name="setdescription"></a>CMFCRibbonButton::SetDescription  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetimageindexa--cmfcribbonbuttonsetimageindex"></a><a name="setimageindex"></a>CMFCRibbonButton::SetImageIndex  
 Назначает индекс изображению кнопки.  
  
```  
void SetImageIndex(
    int nIndex,  
    BOOL bLargeImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс изображения.  
  
 [in] `bLargeImage`  
 Если `TRUE`, указанный индекс относится к списку больших изображений. В противном случае — индекс относится к списку изображений небольшого размера.  
  
##  <a name="a-namesetmenua--cmfcribbonbuttonsetmenu"></a><a name="setmenu"></a>CMFCRibbonButton::SetMenu  
 Назначает всплывающее меню кнопке ленты.  
  
```  
void SetMenu(
    HMENU hMenu,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);

void SetMenu(
    UINT uiMenuResID,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `hMenu`  
 Дескриптор меню Windows.  
  
 `bIsDefaultCommand`  
 Если `TRUE`, кнопки могут выполнять команды по умолчанию; в противном случае — кнопка отображает всплывающее меню.  
  
 `bRightAlign`  
 Если `TRUE`, меню по правому краю. В противном случае — меню по левому краю.  
  
 `uiMenuResID`  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Когда приложение присваивает кнопки меню, кнопки отображает стрелку справа от него. Если `bIsDefaultCommand` — `TRUE`, меню отображается только в том случае, когда пользователь щелкает стрелку. Если пользователь нажимает кнопку, выполняется его команда по умолчанию. Если `bIsDefaultCommand` — `FALSE`, появится меню, щелкнув в любом месте на кнопке.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbuttonsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButton::SetParentCategory  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParent`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetrightalignmenua--cmfcribbonbuttonsetrightalignmenu"></a><a name="setrightalignmenu"></a>CMFCRibbonButton::SetRightAlignMenu  
 Выравнивание края кнопки контекстного меню.  
  
```  
void SetRightAlignMenu(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSet`  
 Если `TRUE`, меню по правому краю. В противном случае — меню по левому краю  
  
##  <a name="a-namesettexta--cmfcribbonbuttonsettext"></a><a name="settext"></a>CMFCRibbonButton::SetText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszText`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

