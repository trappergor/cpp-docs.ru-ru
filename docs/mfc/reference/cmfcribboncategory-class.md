---
title: Класс CMFCRibbonCategory | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CMFCRibbonCategory
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddHidden
- AFXRIBBONCATEGORY/CMFCRibbonCategory::AddPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::CopyFrom
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::FindPanelWithElem
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetContextID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetDroppedDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetElementsByID
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFirstVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetFocused
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetHighlighted
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetImageSize
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetItemIDsList
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLastVisibleElement
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetLargeImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetMaxHeight
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelCount
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelFromPoint
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetPanelIndex
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentButton
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentMenuBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetParentRibbonBar
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetSmallImages
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabColor
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTabRect
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetTextTopLine
- AFXRIBBONCATEGORY/CMFCRibbonCategory::GetVisibleElements
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HighlightPanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTest
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestEx
- AFXRIBBONCATEGORY/CMFCRibbonCategory::HitTestScrollButtons
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsActive
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsVisible
- AFXRIBBONCATEGORY/CMFCRibbonCategory::IsWindows7Look
- AFXRIBBONCATEGORY/CMFCRibbonCategory::NotifyControlCommand
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnCancelMode
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDraw
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawImage
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnDrawMenuBorder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnKey
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonDown
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnLButtonUp
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnMouseMove
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnRTLChanged
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnScrollHorz
- AFXRIBBONCATEGORY/CMFCRibbonCategory::OnUpdateCmdUI
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RecalcLayout
- AFXRIBBONCATEGORY/CMFCRibbonCategory::RemovePanel
- AFXRIBBONCATEGORY/CMFCRibbonCategory::ReposPanels
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetCollapseOrder
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetData
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetKeys
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetName
- AFXRIBBONCATEGORY/CMFCRibbonCategory::SetTabColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory [MFC], CMFCRibbonCategory
- CMFCRibbonCategory [MFC], AddHidden
- CMFCRibbonCategory [MFC], AddPanel
- CMFCRibbonCategory [MFC], CopyFrom
- CMFCRibbonCategory [MFC], FindByData
- CMFCRibbonCategory [MFC], FindByID
- CMFCRibbonCategory [MFC], FindPanelWithElem
- CMFCRibbonCategory [MFC], GetContextID
- CMFCRibbonCategory [MFC], GetData
- CMFCRibbonCategory [MFC], GetDroppedDown
- CMFCRibbonCategory [MFC], GetElements
- CMFCRibbonCategory [MFC], GetElementsByID
- CMFCRibbonCategory [MFC], GetFirstVisibleElement
- CMFCRibbonCategory [MFC], GetFocused
- CMFCRibbonCategory [MFC], GetHighlighted
- CMFCRibbonCategory [MFC], GetImageCount
- CMFCRibbonCategory [MFC], GetImageSize
- CMFCRibbonCategory [MFC], GetItemIDsList
- CMFCRibbonCategory [MFC], GetLastVisibleElement
- CMFCRibbonCategory [MFC], GetLargeImages
- CMFCRibbonCategory [MFC], GetMaxHeight
- CMFCRibbonCategory [MFC], GetName
- CMFCRibbonCategory [MFC], GetPanel
- CMFCRibbonCategory [MFC], GetPanelCount
- CMFCRibbonCategory [MFC], GetPanelFromPoint
- CMFCRibbonCategory [MFC], GetPanelIndex
- CMFCRibbonCategory [MFC], GetParentButton
- CMFCRibbonCategory [MFC], GetParentMenuBar
- CMFCRibbonCategory [MFC], GetParentRibbonBar
- CMFCRibbonCategory [MFC], GetRect
- CMFCRibbonCategory [MFC], GetSmallImages
- CMFCRibbonCategory [MFC], GetTabColor
- CMFCRibbonCategory [MFC], GetTabRect
- CMFCRibbonCategory [MFC], GetTextTopLine
- CMFCRibbonCategory [MFC], GetVisibleElements
- CMFCRibbonCategory [MFC], HighlightPanel
- CMFCRibbonCategory [MFC], HitTest
- CMFCRibbonCategory [MFC], HitTestEx
- CMFCRibbonCategory [MFC], HitTestScrollButtons
- CMFCRibbonCategory [MFC], IsActive
- CMFCRibbonCategory [MFC], IsVisible
- CMFCRibbonCategory [MFC], IsWindows7Look
- CMFCRibbonCategory [MFC], NotifyControlCommand
- CMFCRibbonCategory [MFC], OnCancelMode
- CMFCRibbonCategory [MFC], OnDraw
- CMFCRibbonCategory [MFC], OnDrawImage
- CMFCRibbonCategory [MFC], OnDrawMenuBorder
- CMFCRibbonCategory [MFC], OnKey
- CMFCRibbonCategory [MFC], OnLButtonDown
- CMFCRibbonCategory [MFC], OnLButtonUp
- CMFCRibbonCategory [MFC], OnMouseMove
- CMFCRibbonCategory [MFC], OnRTLChanged
- CMFCRibbonCategory [MFC], OnScrollHorz
- CMFCRibbonCategory [MFC], OnUpdateCmdUI
- CMFCRibbonCategory [MFC], RecalcLayout
- CMFCRibbonCategory [MFC], RemovePanel
- CMFCRibbonCategory [MFC], ReposPanels
- CMFCRibbonCategory [MFC], SetCollapseOrder
- CMFCRibbonCategory [MFC], SetData
- CMFCRibbonCategory [MFC], SetKeys
- CMFCRibbonCategory [MFC], SetName
- CMFCRibbonCategory [MFC], SetTabColor
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee097dd95a1a88b8cf2cb3dc48c4406499001443
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721401"
---
# <a name="cmfcribboncategory-class"></a>Класс CMFCRibbonCategory
`CMFCRibbonCategory` Класс реализует вкладку ленты, содержащую группу [ленте панелей](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|Добавляет скрытый элемент в категорию ленты.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|Добавляет новую область категорию ленты.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Возвращает идентификатор контекста категорию ленты.|  
|[CMFCRibbonCategory::GetData](#getdata)|Возвращает пользовательские данные, связанный с данной категорией ленты.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Получите первый видимый элемент, которые принадлежат к категории ленты.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Возвращает выделенный элемент.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Получить последний видимый элемент, которые принадлежат к категории ленты|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Возвращает ссылку на список больших изображений, которые использует категорию ленты.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Возвращает указатель на панель ленты, расположенную по указанному индексу.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Возвращает число панелей ленты в категорию ленты.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Возвращает индекс указанной ленты.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Возвращает ссылку на список изображений небольшого размера, которые использует категорию.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Возвращает текущий цвет категории вкладки на ленте.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Получите все видимые элементы, принадлежащие к категории ленты.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|Определяет, отображается ли категорию ленты.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Указывает, имеет ли лента родительский Windows 7 в стиле (небольшая прямоугольная кнопка приложения)|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает кнопку клавиатуры.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Определяет порядок свернуть панели ленты, которые присутствуют в категорию ленты.|  
|[CMFCRibbonCategory::SetData](#setdata)|Сохраняет пользовательские данные в категорию ленты.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Присваивает значение свойства keytip категорию ленты.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Задает цвет категорию ленты.|  
  
## <a name="remarks"></a>Примечания  
 Как правило, косвенно создать категорию ленты, вызвав [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), которая возвращает указатель на категорию только что созданный ленты. Добавление панелей в категории путем вызова [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 `CMFCRibbonTab` Класс рисует категорий ленты. Он является производным от [класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 В следующем примере показано, как создать категорию ленты и добавить элемент управления к нему.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 На следующей схеме показано рис домашней категории из примера приложения RibbonApp.  
  
 ![Изображение CMFCRibbonCategory](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncategory.h  
  
##  <a name="addhidden"></a>  CMFCRibbonCategory::AddHidden  
 Добавляет элемент ленты указанный массив элементов ленты, которые отображаются в диалоговом окне настройки.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
*pElem*<br/>
[in] Указатель на элемент ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты в диалоговом окне настройки являются командами, можно добавить на панель быстрого доступа.  
  
##  <a name="addpanel"></a>  CMFCRibbonCategory::AddPanel  
 Создает панель ленты для категорию ленты.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Параметры  
*lpszPanelName*<br/>
[in] Указатель на имя новой панели ленты.  
  
*hIcon*<br/>
[in] Дескриптор значок по умолчанию для новой панели ленты.  
  
*pRTI*<br/>
[in] Указатель на сведения о классе среды выполнения для панели настраиваемой ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новой панели ленты, если метод был выполнен успешно; в противном случае — значение NULL, если панель не был создан.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать панели настраиваемой ленты, необходимо указать его сведения о классе среды выполнения в *pRTI*. Класс panel настраиваемой ленты должен быть производным от `CMFCRibbonPanel` класса.  
  
 Значок на ленте панели отображается в том случае, если недостаточно места для отображения элементов ленты.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `AddPanel` метод в `CMFCRibbonCategory` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>  CMFCRibbonCategory::CMFCRibbonCategory  
 Создает и инициализирует [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) объекта.  
  
```  
CMFCRibbonCategory(
    CMFCRibbonBar* pParenrRibbonBar,  
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32));
```  
  
### <a name="parameters"></a>Параметры  
*pParenrRibbonBar*<br/>
[in] Указатель на панель ленты родительской категории ленты.  
  
*lpszName*<br/>
[in] Имя категории ленты.  
  
*uiSmallImagesResID*<br/>
[in] Идентификатор ресурса для списка изображений для небольших изображений, используемых элементов ленты в категорию ленты.  
  
*uiLargeImagesResID*<br/>
[in] Идентификатор ресурса для списка изображений для больших изображений, используемых элементов ленты в категорию ленты.  
  
*sizeSmallImage*<br/>
[in] По умолчанию размер изображений небольшого размера для элементов ленты в категорию ленты.  
  
*sizeLargeImage*<br/>
[in] По умолчанию размер больших изображений для элементов ленты в категорию ленты.  
  
##  <a name="copyfrom"></a>  CMFCRibbonCategory::CopyFrom  
 Копирует состояние указанного [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) текущему [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) объекта.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Параметры  
*src*<br/>
[in] Источник `CMFCRibbonCategory` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findbydata"></a>  CMFCRibbonCategory::FindByData  
 Извлекает элемент ленты, связанные с указанными данными.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
*dwData*<br/>
[in] Данные, связанные с элемента ленты.  
  
*bVisibleOnly*<br/>
[in] Значение TRUE для включения элементов ленты для быстрого доступа в поиск; Значение FALSE, чтобы исключить элементы быстрого доступа ленты в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findbyid"></a>  CMFCRibbonCategory::FindByID  
 Извлекает элемент ленты, связанный с указанным идентификатором команды.  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
*uiCmdID*<br/>
[in] Идентификатор команды, связанные с элемента ленты.  
  
*bVisibleOnly*<br/>
[in] Значение TRUE для включения элементов ленты для быстрого доступа в поиск; Значение FALSE, чтобы исключить элементы быстрого доступа ленты в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findpanelwithelem"></a>  CMFCRibbonCategory::FindPanelWithElem  
 Получает панель ленты, содержащую элемента указанной ленты.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
*pElement*<br/>
[in] Указатель на элемент ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontextid"></a>  CMFCRibbonCategory::GetContextID  
 Получает контекстный идентификатор класса категорию ленты.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста категорию ленты.  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста равно 0, если категории ленты контекста не является категорией ленты.  
  
##  <a name="getdata"></a>  CMFCRibbonCategory::GetData  
 Получает определяемые пользователем данные, связанный с данной категорией ленты.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемые пользователем данные, связанные с категорией ленты.  
  
##  <a name="getdroppeddown"></a>  CMFCRibbonCategory::GetDroppedDown  
 Извлекает указатель на элемент ленты, которой отображается всплывающее меню.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getelements"></a>  CMFCRibbonCategory::GetElements  
 Извлекает все элементы ленты в категорию ленты.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
*arElements*<br/>
[in, out] Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панели быстрого доступа, включаются в массиве.  
  
##  <a name="getelementsbyid"></a>  CMFCRibbonCategory::GetElementsByID  
 Извлекает все элементы ленты, которые связаны с указанным идентификатором команды.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
*uiCmdID*<br/>
[in] Идентификатор команды, связанные с элемента ленты.  
  
*arElements*<br/>
[in, out] Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панели быстрого доступа, включаются в массиве.  
  
##  <a name="getfirstvisibleelement"></a>  CMFCRibbonCategory::GetFirstVisibleElement  
 Извлекает первый элемент видимым, который принадлежит к категории ленты.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первый видимый элемент; может иметь значение NULL, если категории не содержит все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfocused"></a>  CMFCRibbonCategory::GetFocused  
 Возвращает элемент, имеющий фокус ввода.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с фокусом или значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethighlighted"></a>  CMFCRibbonCategory::GetHighlighted  
 Возвращает выделенный элемент.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный элемент или значение NULL, если элементы не выделены.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getimagecount"></a>  CMFCRibbonCategory::GetImageCount  
 Возвращает число изображений в списке указанное изображение, содержащийся в категорию ленты.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
*bIsLargeImage*<br/>
[in] Значение TRUE, если число изображений в списке большое изображение; Значение FALSE означает, что число изображений в списке небольшое изображение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число изображений в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getimagesize"></a>  CMFCRibbonCategory::GetImageSize  
 Получает размер изображения в списке указанное изображение, содержащийся в категорию ленты.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
*bIsLargeImage*<br/>
[in] Значение TRUE, если для размера больших изображений; Значение FALSE означает, что размер изображений небольшого размера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер изображения в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
 Получить размер включает универсальный образ коэффициент масштабирования.  
  
##  <a name="getitemidslist"></a>  CMFCRibbonCategory::GetItemIDsList  
 Извлекает идентификаторы команд для элементов ленты, которые содержатся в категорию ленты.  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
*lstItems*<br/>
[out] Список идентификаторов команд для элементов ленты в категорию ленты.  
  
*bHiddenOnly*<br/>
[in] Значение TRUE, чтобы исключить элементы ленты, отображаемые на панели ленты в категорию ленты; Значение FALSE означает, что для включения всех элементов ленты в категорию ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlargeimages"></a>  CMFCRibbonCategory::GetLargeImages  
 Получение списка больших изображений, которые содержатся в категорию ленты.  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список больших изображений, которые содержатся в категорию ленты.  
  
##  <a name="getlastvisibleelement"></a>  CMFCRibbonCategory::GetLastVisibleElement  
 Возвращает последний элемент видимым, принадлежит к категории ленты.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель к последнему отображаемому элементу; может иметь значение NULL, если категория не содержит все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmaxheight"></a>  CMFCRibbonCategory::GetMaxHeight  
 Получает максимальную высоту панели ленты, которые содержатся в категорию ленты.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная высота панели ленты, которые содержатся в категорию ленты.  
  
### <a name="remarks"></a>Примечания  
 Значение, полученное включает высоту верхнего и нижнего полей для панели ленты.  
  
##  <a name="getname"></a>  CMFCRibbonCategory::GetName  
 Получает имя категории ленты.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanel"></a>  CMFCRibbonCategory::GetPanel  
 Возвращает указатель на панель ленты, расположенную по указанному индексу.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
*nIndex*<br/>
[in] Отсчитываемый от нуля индекс панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, расположенную по указанному индексу.  
  
### <a name="remarks"></a>Примечания  
 Исключение возникает в том случае, если *nIndex* выходит за пределы диапазона.  
  
##  <a name="getpanelcount"></a>  CMFCRibbonCategory::GetPanelCount  
 Возвращает число панелей ленты в категорию ленты.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество панелей ленты в категорию ленты.  
  
##  <a name="getpanelfrompoint"></a>  CMFCRibbonCategory::GetPanelFromPoint  
 Извлекает указатель на панель ленты, если указанная точка находится в нем.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя, относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только панелей ленты, которые содержатся в категорию ленты.  
  
##  <a name="getpanelindex"></a>  CMFCRibbonCategory::GetPanelIndex  
 Получает отсчитываемый от нуля индекс на указанной ленте панели.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Параметры  
*pPanel*<br/>
[in] Указатель на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс панели указанной ленты, если метод был выполнен успешно; в противном случае-1.  
  
### <a name="remarks"></a>Примечания  
 Поиск выполняется только для ленты, которые содержатся в категорию ленты.  
  
##  <a name="getparentbutton"></a>  CMFCRibbonCategory::GetParentButton  
 Извлекает родительский элемент ленты категорию ленты.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на родительский элемент ленты, или значение NULL, если нет родительского элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentmenubar"></a>  CMFCRibbonCategory::GetParentMenuBar  
 Возвращает указатель на строку меню родительского `CMFCRibbonCategory` объекта.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает содержимое `m_pParentMenuBar` защищенного члена.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentribbonbar"></a>  CMFCRibbonCategory::GetParentRibbonBar  
 Извлекает панели ленты родительской категории ленты.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты родительской категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrect"></a>  CMFCRibbonCategory::GetRect  
 Возвращает прямоугольник, отображаемое для категории ленты.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник отображения для категорию ленты.  
  
### <a name="remarks"></a>Примечания  
 Отображаемая область для категории ленты отсутствует вкладка категории.  
  
##  <a name="getsmallimages"></a>  CMFCRibbonCategory::GetSmallImages  
 Извлекает список изображений небольшого размера, которые содержатся в категорию ленты.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список изображений небольшого размера, которые содержатся в категорию ленты.  
  
##  <a name="gettabcolor"></a>  CMFCRibbonCategory::GetTabColor  
 Возвращает текущий цвет категории вкладки на ленте.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет категории вкладки на ленте.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение может быть одно из следующих значений:  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>  CMFCRibbonCategory::GetTabRect  
 Возвращает прямоугольник, отображаемое для категории вкладки ленты.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник отображения для категории вкладки ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettexttopline"></a>  CMFCRibbonCategory::GetTextTopLine  
 Получает вертикальное расположение текста на кнопок ленты в категорию ленты, отображение больших изображений.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное расположение текста в пикселях на кнопок ленты, которые отображения больших изображений.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvisibleelements"></a>  CMFCRibbonCategory::GetVisibleElements  
 Извлекает все видимые элементы, принадлежащие к категории ленты.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 *arElements*  
 Массив всех видимых элементов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="highlightpanel"></a>  CMFCRibbonCategory::HighlightPanel  
 Выделяет панель указанной ленты.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*pHLPanel*<br/>
[in] Указатель на панель ленты, чтобы выделить.  
  
*точка*<br/>
[in] Координаты x и y указателя, относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, ранее выделенный. в противном случае — значение NULL, если нет панель ленты, выделяется при вызове этого метода.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о выделение на панель ленты, см. в разделе [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="hittest"></a>  CMFCRibbonCategory::HitTest  
 Извлекает указатель на элемент ленты, если указанная точка находится в нем.  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
*bCheckPanelCaption*<br/>
[in] Значение TRUE, чтобы проверить заголовок панели ленты; Значение FALSE, чтобы исключить заголовок панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только те элементы ленты, которые содержатся в категорию ленты.  
  
##  <a name="hittestex"></a>  CMFCRibbonCategory::HitTestEx  
 Получает отсчитываемый от нуля индекс элемента ленты, если указанная точка находится в нем.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента ленты, если метод был выполнен успешно; в противном случае-1.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только те элементы ленты, которые содержатся в категорию ленты.  
  
##  <a name="hittestscrollbuttons"></a>  CMFCRibbonCategory::HitTestScrollButtons  
 Если точка находится в пределах категории ленты кнопку прокрутки влево или вправо, возвращает указатель на эту кнопку.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Точка для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если *точки* попадает в ограничивающий прямоугольник либо слева или кнопки прокрутки вправо категории ленты, возвращает указатель на эту кнопку или в противном случае возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isactive"></a>  CMFCRibbonCategory::IsActive  
 Указывает, является ли категорию ленты активную категорию на панели ленты.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если категория ленты активную категорию; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Категории ленты, активная отображает его панелей ленты.  
  
##  <a name="isvisible"></a>  CMFCRibbonCategory::IsVisible  
 Указывает, видима ли категорию ленты.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если категория ленты является видимым. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Категорий ленты, которые видны вкладка категории.  
  
##  <a name="iswindows7look"></a>  CMFCRibbonCategory::IsWindows7Look  
 Указывает, имеет ли лента родительский Windows 7 найдите (небольшая прямоугольная кнопка приложения).  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если лента родительский имеет Windows 7 поиска; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="notifycontrolcommand"></a>  CMFCRibbonCategory::NotifyControlCommand  
 Доставляет сообщения WM_NOTIFY команды ко всем `CMFCRibbonPanel` элементов в `CMFCRibbonCategory` до обработки сообщения.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
*bAccelerator*<br/>
[in] Значение TRUE, если команда, являющийся источником ускорителя, либо FALSE в противном случае.  
  
*nNotifyCode*<br/>
[in] Код уведомления.  
  
*wParam*<br/>
[in] Поле WPARAM сообщения.  
  
*lParam*<br/>
[in] Поле LPARAM сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если сообщение было обработано, или значение FALSE, если это не так.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncancelmode"></a>  CMFCRibbonCategory::OnCancelMode  
 Вызывает режим "Отмена" во всех `CMFCRibbonPanel` элементы `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>  CMFCRibbonCategory::OnDraw  
 Вызывается платформой для отрисовки категорию ленты.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для категорию ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawimage"></a>  CMFCRibbonCategory::OnDrawImage  
 Вызывается платформой для отрисовки указанное изображение в категорию ленты.  
  
```  
virtual BOOL OnDrawImage(
    CDC* pDC,  
    CRect rect,  
    CMFCRibbonBaseElement* pElement,  
    BOOL bIsLargeImage,  
    BOOL nImageIndex,  
    BOOL bCenter);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для образа.  
  
*Rect*<br/>
[in] Отображаемый прямоугольник для изображения.  
  
*pElement*<br/>
[in] Указатель на элемент ленты, содержащий изображение.  
  
*bIsLargeImage*<br/>
[in] Значение TRUE, если изображение имеет большой размер. Значение FALSE, если изображение малого размера.  
  
*nImageIndex*<br/>
[in] Отсчитываемый от нуля индекс изображения в изображение массива, содержащийся в категорию ленты.  
  
*bCenter*<br/>
[in] Значение TRUE, чтобы поместить изображение в прямоугольник отображения; Значение FALSE означает, что для рисования изображения в верхнем левом углу прямоугольник отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawmenuborder"></a>  CMFCRibbonCategory::OnDrawMenuBorder  
 Вызывается платформой для рисования границы всплывающего меню.  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Этот параметр не используется.  
  
*pMenuBar*<br/>
[in] Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод для рисования границы всплывающего меню.  
  
##  <a name="onkey"></a>  CMFCRibbonCategory::OnKey  
 Вызывается платформой, когда пользователь нажимает кнопку клавиатуры.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 *NChar*  
 Виртуального кода клавиши для ключа, который пользователь нажал клавиши.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonCategory::OnLButtonDown  
 Вызывается платформой для извлечения элемента ленты в указанной точке, когда пользователь нажимает левую кнопку мыши.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonCategory::OnLButtonUp  
 Вызывается платформой, когда пользователь отпускает левую кнопку мыши и указатель находится над категорию ленты.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя, относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onmousemove"></a>  CMFCRibbonCategory::OnMouseMove  
 Вызывается платформой при перемещении указателя на ленте, чтобы обновить список категорий ленты.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*точка*<br/>
[in] Координаты x и y указателя, относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonCategory::OnRTLChanged  
 Вызывается платформой при изменении направления макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
*bIsRTL*<br/>
[in] Значение TRUE, если макет справа налево; Значение FALSE, если макет слева направо.  
  
### <a name="remarks"></a>Примечания  
 Этот метод настраивает макет всех панелей ленты и элементы ленты, которые содержатся в категорию ленты.  
  
##  <a name="onscrollhorz"></a>  CMFCRibbonCategory::OnScrollHorz  
 Прокручивает категорию ленты в горизонтальном направлении.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Параметры  
*bScrollLeft*<br/>
[in] Значение TRUE, чтобы прокрутить влево; Значение FALSE, чтобы прокрутить вправо.  
  
*nScrollOffset*<br/>
[in] Расстояние прокрутки в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переместить категорию ленты в горизонтальном направлении; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onupdatecmdui"></a>  CMFCRibbonCategory::OnUpdateCmdUI  
 Вызовы `OnUpdateCmdUI` функция-член в каждом из `CMFCRibbonPanel` элементы `CMFCRibbonCategory` Включение или отключение элементов пользовательского интерфейса в них.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
*pCmdUI*<br/>
[in] Указатель на `CMFCRibbonCmdUI` , указывающий элементы пользовательского интерфейса, которые требуется включить, а также какие — должно быть отключено.  
  
*pTarget*<br/>
[in] Указатель на окно, которое контролирует Включение или отключение элементов пользовательского интерфейса.  
  
*bDisableIfNoHndler*<br/>
[in] Значение TRUE, чтобы отключить элемент пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="recalclayout"></a>  CMFCRibbonCategory::RecalcLayout  
 Настраивает макет всех элементов управления на категорию ленты.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для категорию ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removepanel"></a>  CMFCRibbonCategory::RemovePanel  
 Удаляет панель ленты из категорию ленты.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*nIndex*<br/>
[in] Номер индекса панель, удаляемую. Получен путем вызова [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) метод.  
  
*bDelete*<br/>
[in] Значение TRUE, чтобы удалить объект панели из памяти; Значение FALSE, чтобы удалить объект панели, не удаляя его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
##  <a name="repospanels"></a>  CMFCRibbonCategory::ReposPanels  
 Настраивает макет всех элементов управления на панели ленты, которые содержатся в категорию ленты.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
*основного контроллера домена*<br/>
[in] Указатель на контекст устройства для панели ленты, которые содержатся в категорию ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcollapseorder"></a>  CMFCRibbonCategory::SetCollapseOrder  
 Определяет порядок, в котором свернуть панелей ленты категории ленты.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Параметры  
*arCollapseOrder*<br/>
[in] Указывает порядок свернуть. Массив содержит отсчитываемые с нуля индексы панелей ленты.  
  
### <a name="remarks"></a>Примечания  
 Библиотека определяет порядок свернуть. Тем не менее это поведение можно настроить, предоставляя список индексов, которое указывает порядок Свернуть категории.  
  
 Обнаружив категории наличии свернуть панель ленты, он ищет следующий элемент в указанном списке. Если список пуст, или вы не указали достаточно элементов, категории использует внутренний алгоритм.  
  
 Например категории имеет три панели ленты и можно ли свернуть несколько раз, пока все элементы управления находятся в полностью свернутое состояние. Можно задать следующий порядок свернуть: 0, 0, 2, 2. В этом случае категория будет свернуть панель 0 два раза, панель 2 два раза. Панель, которая имеет индекс 1 остается свернут.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `SetCollapseOrder` метод в `CMFCRibbonCategory` класса. В примере показано, как создать массив для заказа свернуть и как установить порядок Свернуть категорию ленты.  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>  CMFCRibbonCategory::SetData  
 Задает определяемые пользователем данные должны быть сопоставлены категорию ленты.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
*dwData*<br/>
[in] Определяемые пользователем данные.  
  
##  <a name="setkeys"></a>  CMFCRibbonCategory::SetKeys  
 Присваивает значение свойства keytip категорию ленты.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Параметры  
*lpszKeys*<br/>
[in] Текст подсказки клавиши.  
  
### <a name="remarks"></a>Примечания  
 Ключевые подсказки отображаются в том случае, когда пользователь нажимает клавишу Alt и клавишу F10.  
  
##  <a name="setname"></a>  CMFCRibbonCategory::SetName  
 Назначает имя и подсказки клавиши категорию ленты.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
*lpszName*<br/>
[in] Имя и подсказки клавиши категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать подсказки клавиши для категории ленты, добавьте escape-последовательность новой строки, следуют символы подсказки клавиши для *lpszName*.  
  
##  <a name="settabcolor"></a>  CMFCRibbonCategory::SetTabColor  
 Задает цвет категорию ленты.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Параметры  
*Цвет*<br/>
[in] Указывает новый цвет категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Цвет может принимать одно из следующих значений:  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
