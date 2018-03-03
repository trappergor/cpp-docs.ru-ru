---
title: "Класс CMFCRibbonCategory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4e78017946ef335e04c8190b6ec4cd20e74ca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncategory-class"></a>Класс CMFCRibbonCategory
`CMFCRibbonCategory` Класс реализует вкладку ленты, которая содержит группу [панелей ленты](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|Добавляет скрытый элемент в категорию ленты.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|Добавляет новую область в категорию ленты.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Возвращает идентификатор контекста категорию ленты.|  
|[CMFCRibbonCategory::GetData](#getdata)|Возвращает определяемые пользователем данные, связанные с категорией ленты.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Получите первый видимый элемент, который принадлежит к категории ленты.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Возвращает выделенный элемент.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Получить последнему отображаемому элементу, который принадлежит к категории ленты|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Возвращает ссылку на список больших изображений, которые использует категорию ленты.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Возвращает указатель на панель ленты, расположенный по указанному индексу.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Возвращает количество элементов управления ленты в категорию ленты.|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Возвращает индекс указанного ленты панели.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Возвращает ссылку на список изображений небольшого размера, которые использует категории.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Возвращает текущий цвет категории вкладки ленты.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Получите все видимые элементы, которые принадлежат к категории ленты.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|Определяет, видима ли категория ленты.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Указывает, имеет ли родительский ленты оформление Windows стиль 7 (небольшая прямоугольная кнопка приложения)|  
|[CMFCRibbonCategory::NotifyControlCommand](#notifycontrolcommand)||  
|[CMFCRibbonCategory::OnCancelMode](#oncancelmode)||  
|[CMFCRibbonCategory::OnDraw](#ondraw)||  
|[CMFCRibbonCategory::OnDrawImage](#ondrawimage)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](#ondrawmenuborder)||  
|[CMFCRibbonCategory::OnKey](#onkey)|Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.|  
|[CMFCRibbonCategory::OnLButtonDown](#onlbuttondown)||  
|[CMFCRibbonCategory::OnLButtonUp](#onlbuttonup)||  
|[CMFCRibbonCategory::OnMouseMove](#onmousemove)||  
|[CMFCRibbonCategory::OnRTLChanged](#onrtlchanged)||  
|[CMFCRibbonCategory::OnScrollHorz](#onscrollhorz)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](#onupdatecmdui)||  
|[CMFCRibbonCategory::RecalcLayout](#recalclayout)||  
|[CMFCRibbonCategory::RemovePanel](#removepanel)||  
|[CMFCRibbonCategory::ReposPanels](#repospanels)||  
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Определяет порядок свернуть панелей ленты, которые присутствуют в категории ленты.|  
|[CMFCRibbonCategory::SetData](#setdata)|Сохраняет данные, определенные пользователем в категорию ленты.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Присваивает значение свойства keytip категорию ленты.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Задает цвет категорию ленты.|  
  
## <a name="remarks"></a>Примечания  
 Как правило, косвенно создать категорию ленты, вызвав [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), который возвращает указатель на категорию ленты только что созданный. Добавление панелей в категорию, вызвав [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 `CMFCRibbonTab` Класс прорисовывает категорий ленты. Он является производным от [CMFCRibbonBaseElement класса](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
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
  
 На следующей диаграмме показан рисунок категории домашней из образца приложения RibbonApp.  
  
 ![Изображение CMFCRibbonCategory](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncategory.h  
  
##  <a name="addhidden"></a>CMFCRibbonCategory::AddHidden  
 Добавляет элемент ленты указанного массива элементов ленты, которые отображаются в диалоговом окне настройки.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElem`  
 Указатель на элемент ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементов ленты в диалоговом окне настройки — это команды, которые можно добавить на панель быстрого доступа.  
  
##  <a name="addpanel"></a>CMFCRibbonCategory::AddPanel  
 Создает панель ленты для ленты категории.  
  
```  
CMFCRibbonPanel* AddPanel(
    LPCTSTR lpszPanelName,  
    HICON hIcon = 0,  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPanelName`  
 Указатель на имя новой панели ленты.  
  
 [in] `hIcon`  
 Дескриптор значка по умолчанию для новой панели ленты.  
  
 [in] `pRTI`  
 Указатель на сведения о классе среды выполнения для панели настраиваемой ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый панель ленты, если метод выполнен успешно; в противном случае `NULL` Если панель не была создана.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать панель настраиваемой ленты, необходимо указать его сведения о классе среды выполнения в `pRTI`. Класс настраиваемой ленты панели должен быть производным от `CMFCRibbonPanel` класса.  
  
 Значок по умолчанию для панели ленты отображается в том случае, если недостаточно места для отображения элементов ленты.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddPanel` метод `CMFCRibbonCategory` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp#10](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="cmfcribboncategory"></a>CMFCRibbonCategory::CMFCRibbonCategory  
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
 [in] `pParenrRibbonBar`  
 Указатель на панель ленты родительской категории ленты.  
  
 [in] `lpszName`  
 Имя категории ленты.  
  
 [in] `uiSmallImagesResID`  
 Идентификатор ресурса изображения списка маленьких изображений, используемых элементов ленты в категорию ленты.  
  
 [in] `uiLargeImagesResID`  
 Идентификатор ресурса изображения списка больших изображений, используемых элементов ленты в категорию ленты.  
  
 [in] `sizeSmallImage`  
 По умолчанию размер маленькие изображения для элементов ленты в категорию ленты.  
  
 [in] `sizeLargeImage`  
 По умолчанию размер больших изображений для элементов ленты в категорию ленты.  
  
##  <a name="copyfrom"></a>CMFCRibbonCategory::CopyFrom  
 Копирует состояние указанного [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) с текущим [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) объекта.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Исходный объект `CMFCRibbonCategory`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findbydata"></a>CMFCRibbonCategory::FindByData  
 Извлекает элемент ленты, связанные с указанными данными.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Данные, связанные с элемента ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`Чтобы включить в поиск; элементов ленты для быстрого доступа `FALSE` для исключения элементов ленты быстрого доступа в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findbyid"></a>CMFCRibbonCategory::FindByID  
 Извлекает элемент ленты, связанные с указанным идентификатором команды.  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды, связанные с элемента ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`Чтобы включить в поиск; элементов ленты для быстрого доступа `FALSE` для исключения элементов ленты быстрого доступа в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findpanelwithelem"></a>CMFCRibbonCategory::FindPanelWithElem  
 Получает панель ленты, содержащей элемент указанной ленты.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель на элемент ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcontextid"></a>CMFCRibbonCategory::GetContextID  
 Получает контекстный идентификатор категории ленты.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста категорию ленты.  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста равно 0, если категорию ленты контекста не является категорией ленты.  
  
##  <a name="getdata"></a>CMFCRibbonCategory::GetData  
 Получает определяемые пользователем данные, связанные с категорией ленты.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемые пользователем данные, связанные с категорией ленты.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonCategory::GetDroppedDown  
 Извлекает указатель на элемент ленты, в настоящее время имеет отображенным всплывающего меню.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getelements"></a>CMFCRibbonCategory::GetElements  
 Извлекает все элементы ленты в категорию ленты.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `arElements`  
 Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панели инструментов быстрого доступа включаются в массиве.  
  
##  <a name="getelementsbyid"></a>CMFCRibbonCategory::GetElementsByID  
 Извлекает все элементы ленты, связанные с указанным идентификатором команды.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды, связанные с элемента ленты.  
  
 [in, out] `arElements`  
 Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панели инструментов быстрого доступа включаются в массиве.  
  
##  <a name="getfirstvisibleelement"></a>CMFCRibbonCategory::GetFirstVisibleElement  
 Возвращает первый элемент видимым, к которой принадлежит категория ленты.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первый элемент видимым; может быть `NULL` Если категории не поддерживает все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfocused"></a>CMFCRibbonCategory::GetFocused  
 Возвращает элемент, имеющий фокус ввода.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с фокусом ввода или `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethighlighted"></a>CMFCRibbonCategory::GetHighlighted  
 Возвращает выделенный элемент.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный элемент или `NULL` Если нет элементы, выделяются.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getimagecount"></a>CMFCRibbonCategory::GetImageCount  
 Возвращает число изображений в списке указанный образ, который содержится в категории ленты.  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsLargeImage`  
 `TRUE`число изображений в списке больших изображений. `FALSE` число изображений в списке мелкое изображение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество изображений в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getimagesize"></a>CMFCRibbonCategory::GetImageSize  
 Получает размер изображения в списке указанный образ, который содержится в категории ленты.  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsLargeImage`  
 `TRUE`для размера больших изображений. `FALSE` размера изображений небольшого размера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер изображения в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
 Получить размер включает универсальный образ коэффициент масштабирования.  
  
##  <a name="getitemidslist"></a>CMFCRibbonCategory::GetItemIDsList  
 Извлекает идентификаторы команд для элементов ленты, которые находятся в категории ленты.  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lstItems`  
 Список идентификаторов команд для элементов ленты в категорию ленты.  
  
 [in] `bHiddenOnly`  
 `TRUE`Чтобы исключить элементы ленты, которые отображаются на панели ленты в категории ленты; `FALSE` для включения всех элементов ленты в категорию ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlargeimages"></a>CMFCRibbonCategory::GetLargeImages  
 Извлечение списка больших изображений, которые находятся в категории ленты.  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список больших изображений, которые находятся в категории ленты.  
  
##  <a name="getlastvisibleelement"></a>CMFCRibbonCategory::GetLastVisibleElement  
 Возвращает последний элемент видимым, к которой принадлежит категория ленты.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на последний элемент видимым; может быть `NULL` Если категории не поддерживает все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmaxheight"></a>CMFCRibbonCategory::GetMaxHeight  
 Возвращает максимальную высоту панели ленты, которые находятся в категории ленты.  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная высота панели ленты, которые находятся в категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Извлекаемое значение включает высоту верхнего и нижнего полей для панели ленты.  
  
##  <a name="getname"></a>CMFCRibbonCategory::GetName  
 Получает имя категории ленты.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanel"></a>CMFCRibbonCategory::GetPanel  
 Возвращает указатель на панель ленты, расположенный по указанному индексу.  
  
```  
CMFCRibbonPanel* GetPanel(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, расположенный по указанному индексу.  
  
### <a name="remarks"></a>Примечания  
 Исключение возникает, если `nIndex` выходит за пределы диапазона.  
  
##  <a name="getpanelcount"></a>CMFCRibbonCategory::GetPanelCount  
 Возвращает количество элементов управления ленты в категорию ленты.  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов управления ленты в категорию ленты.  
  
##  <a name="getpanelfrompoint"></a>CMFCRibbonCategory::GetPanelFromPoint  
 Извлекает указатель на панель ленты, если заданная точка находится в нем.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только панелей ленты, которые находятся в категории ленты.  
  
##  <a name="getpanelindex"></a>CMFCRibbonCategory::GetPanelIndex  
 Возвращает отсчитываемый от нуля индекс панели указанной ленты.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPanel`  
 Указатель на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс панели указанной ленты, если метод выполнен успешно; в противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
 Поиск будет производиться только панелей ленты, которые находятся в категории ленты.  
  
##  <a name="getparentbutton"></a>CMFCRibbonCategory::GetParentButton  
 Получает родительский элемент ленты категории ленты.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на родительский элемент ленты, или `NULL` Если нет родительского элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentmenubar"></a>CMFCRibbonCategory::GetParentMenuBar  
 Возвращает указатель на строку меню родительского `CMFCRibbonCategory` объекта.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает содержимое `m_pParentMenuBar` защищенного члена.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getparentribbonbar"></a>CMFCRibbonCategory::GetParentRibbonBar  
 Получает панель ленты родительской категории ленты.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты родительской категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrect"></a>CMFCRibbonCategory::GetRect  
 Возвращает прямоугольник, отображаемое для категории ленты.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отображаемый прямоугольник для категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Отображаемый прямоугольник для категории ленты не включает вкладку «Категория».  
  
##  <a name="getsmallimages"></a>CMFCRibbonCategory::GetSmallImages  
 Извлекает список изображений небольшого размера, содержащихся в категории ленты.  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список изображений небольшого размера, содержащихся в категории ленты.  
  
##  <a name="gettabcolor"></a>CMFCRibbonCategory::GetTabColor  
 Возвращает текущий цвет категории вкладки ленты.  
  
```  
AFX_RibbonCategoryColor GetTabColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет категории вкладки ленты.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение может быть одним из следующих значений:  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="gettabrect"></a>CMFCRibbonCategory::GetTabRect  
 Возвращает прямоугольник, отображаемое для категории вкладки ленты.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отображаемый прямоугольник для категории вкладки ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettexttopline"></a>CMFCRibbonCategory::GetTextTopLine  
 Получает вертикальное расположение текста на кнопок ленты в категории ленты отображения больших изображений.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное расположение текста в пикселях на кнопки ленты, которые выводятся больших изображений.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvisibleelements"></a>CMFCRibbonCategory::GetVisibleElements  
 Извлекает все видимые элементы, которые принадлежат к категории ленты.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 `arElements`  
 Массив всех видимых элементов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="highlightpanel"></a>CMFCRibbonCategory::HighlightPanel  
 Выделяет панели указанной ленты.  
  
```  
CMFCRibbonPanel* HighlightPanel(
    CMFCRibbonPanel* pHLPanel,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pHLPanel`  
 Указатель на панель ленты, чтобы выделить.  
  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, ранее выделенный; в противном случае `NULL` Если нет панели ленты, выделяется при вызове этого метода.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о выделении панели ленты см. в разделе [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="hittest"></a>CMFCRibbonCategory::HitTest  
 Извлекает указатель на элемент ленты, если заданная точка находится в нем.  
  
```  
CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckPanelCaption = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`Чтобы проверить заголовок панели ленты; `FALSE` исключаемый заголовок панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только те элементы ленты, которые содержатся в категорию ленты.  
  
##  <a name="hittestex"></a>CMFCRibbonCategory::HitTestEx  
 Возвращает отсчитываемый от нуля индекс элемента ленты, если заданная точка находится в нем.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента ленты, если метод выполнен успешно; в противном случае значение -1.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только те элементы ленты, которые содержатся в категорию ленты.  
  
##  <a name="hittestscrollbuttons"></a>CMFCRibbonCategory::HitTestScrollButtons  
 Если точка находится в рамках кнопка прокрутки влево или вправо категория ленты, возвращает указатель на эту кнопку.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точки для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `point` попадает в прямоугольник, ограничивающий либо влево или кнопка прокрутки вправо категории ленты, возвращает указатель на эту кнопку или в противном случае возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isactive"></a>CMFCRibbonCategory::IsActive  
 Указывает, является ли категория ленты активную категорию на панели ленты.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория ленты активную категорию; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категория ленты, активная отображает его панелей ленты.  
  
##  <a name="isvisible"></a>CMFCRibbonCategory::IsVisible  
 Указывает, видима ли категория ленты.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория ленты является видимым. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категории ленты, которые являются видимыми вкладка категории.  
  
##  <a name="iswindows7look"></a>CMFCRibbonCategory::IsWindows7Look  
 Указывает, имеет ли ленты родительского Windows 7 (небольшая прямоугольная кнопка приложения) найдите.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительский ленты Windows 7 поиска; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="notifycontrolcommand"></a>CMFCRibbonCategory::NotifyControlCommand  
 Доставляет сообщения WM_NOTIFY команды ко всем `CMFCRibbonPanel` элементов в `CMFCRibbonCategory` до обработки сообщения.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAccelerator`  
 `TRUE`Если эта команда исходит от сочетаний клавиш или `FALSE` в противном случае.  
  
 [in] `nNotifyCode`  
 Код уведомления.  
  
 [in] `wParam`  
 WPARAM поле сообщения.  
  
 [in] `lParam`  
 Поле LPARAM сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если сообщение было обработано, или `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncancelmode"></a>CMFCRibbonCategory::OnCancelMode  
 Вызывает режим "Отмена" во всех `CMFCRibbonPanel` элементы `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>CMFCRibbonCategory::OnDraw  
 Вызывается платформой для отрисовки категорию ленты.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawimage"></a>CMFCRibbonCategory::OnDrawImage  
 Вызывается платформой для отрисовки заданное изображение в категорию ленты.  
  
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
 [in] `pDC`  
 Указатель на контекст устройства для изображения.  
  
 [in] `rect`  
 Отображаемый прямоугольник для изображения.  
  
 [in] `pElement`  
 Указатель на элемент ленты, содержащую образ.  
  
 [in] `bIsLargeImage`  
 `TRUE`Если изображение имеет большой размер. `FALSE` Если изображение имеет небольшой размер.  
  
 [in] `nImageIndex`  
 Отсчитываемый от нуля индекс в массиве образ, который содержится в категории ленты изображения.  
  
 [in] `bCenter`  
 `TRUE`Чтобы центрировать изображения в прямоугольник отображения; `FALSE` для прорисовки изображения в верхнем левом углу прямоугольник отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawmenuborder"></a>CMFCRibbonCategory::OnDrawMenuBorder  
 Вызывается платформой для рисования границы всплывающего меню.  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Этот параметр не используется.  
  
 [in] `pMenuBar`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод для рисования границы всплывающего меню.  
  
##  <a name="onkey"></a>CMFCRibbonCategory::OnKey  
 Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Виртуального кода клавиши для ключа, который пользователь нажал клавиши.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttondown"></a>CMFCRibbonCategory::OnLButtonDown  
 Вызывается платформой для извлечения элемента ленты в указанной точке при нажатии левой кнопки мыши.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onlbuttonup"></a>CMFCRibbonCategory::OnLButtonUp  
 Вызывается платформой, когда пользователь отпускает левую кнопку мыши и указатель находится над категорию ленты.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onmousemove"></a>CMFCRibbonCategory::OnMouseMove  
 Вызывается платформой при наведении указателя мыши на панели ленты для обновления отображения категорию ленты.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrtlchanged"></a>CMFCRibbonCategory::OnRTLChanged  
 Вызывается платформой при изменении направление макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
 `TRUE`Если макет справа налево; `FALSE` Если макет справа налево.  
  
### <a name="remarks"></a>Примечания  
 Этот метод настраивает макет всех панелей ленты и элементов ленты, которые находятся в категории ленты.  
  
##  <a name="onscrollhorz"></a>CMFCRibbonCategory::OnScrollHorz  
 Прокручивает категории ленты в горизонтальном направлении.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bScrollLeft`  
 `TRUE`для прокрутки влево; `FALSE` для прокрутки вправо.  
  
 [in] `nScrollOffset`  
 Расстояние прокрутки в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если переместить категорию ленты в горизонтальном направлении; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onupdatecmdui"></a>CMFCRibbonCategory::OnUpdateCmdUI  
 Вызовы `OnUpdateCmdUI` функции-члена в каждом из `CMFCRibbonPanel` элементы `CMFCRibbonCategory` Включение и отключение элементов пользовательского интерфейса в них.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCmdUI`  
 Указатель на `CMFCRibbonCmdUI` , указывающий элементы пользовательского интерфейса, которые должны быть включены, а какие нужно отключить.  
  
 [in] `pTarget`  
 Указатель определяет включение или отключение элементов пользовательского интерфейса.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`отключение элемента пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="recalclayout"></a>CMFCRibbonCategory::RecalcLayout  
 Настраивает макет всех элементов управления на категорию ленты.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removepanel"></a>CMFCRibbonCategory::RemovePanel  
 Удаляет панель ленты из категории ленты.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Номер индекса панели для удаления. Получается вызовом [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) метод.  
  
 [in] `bDelete`  
 `TRUE`Чтобы удалить объект панели из памяти; `FALSE` удалить панель объект не удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE`, если метод выполнен успешно; в противном случае — значение `FALSE`.  
  
##  <a name="repospanels"></a>CMFCRibbonCategory::ReposPanels  
 Настраивает макет всех элементов управления на панели ленты, которые находятся в категории ленты.  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панелей ленты, которые находятся в категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcollapseorder"></a>CMFCRibbonCategory::SetCollapseOrder  
 Определяет порядок, в котором свернуть панелей ленты категории ленты.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `arCollapseOrder`  
 Указывает порядок свернуть. Массив содержит отсчитываемый от нуля индексы панелей ленты.  
  
### <a name="remarks"></a>Примечания  
 Библиотека определяет порядок свернуть. Тем не менее это поведение можно настроить, предоставляя список индексов, указывающее порядок Свернуть категорию.  
  
 Обнаружив категории наличии свернуть панель ленты, выполняет поиск следующего элемента в указанном списке. Если список пуст или не определены достаточно элементов, категории использует внутренний алгоритм.  
  
 Например категория имеет три панели ленты и может быть свернута несколько раз, пока не будут полностью свернутое состояние всех панелей. Можно задать следующий порядок свернуть: 0, 0, 2, 2. В этом случае категория будет свернуть панель 0 два раза, панели 2 двух раз. Панель, которая имеет индекс 1 остается свернут.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetCollapseOrder` метод `CMFCRibbonCategory` класса. В примере показано, как создать массив для свертывания заказа и настройка порядка Свернуть категорию ленты.  
  
 [!code-cpp[NVC_MFC_RibbonApp#13](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="setdata"></a>CMFCRibbonCategory::SetData  
 Задает определяемые пользователем данные, необходимо сопоставить с категорию ленты.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Определенные пользователем данные.  
  
##  <a name="setkeys"></a>CMFCRibbonCategory::SetKeys  
 Присваивает значение свойства keytip категорию ленты.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszKeys`  
 Текст клавишную подсказку.  
  
### <a name="remarks"></a>Примечания  
 Ключевые подсказки отображаются в том случае, когда пользователь нажимает клавишу Alt и клавишу F10.  
  
##  <a name="setname"></a>CMFCRibbonCategory::SetName  
 Назначает имя и значение свойства keytip категорию ленты.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя и значение свойства keytip категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Для установки keytip для категории ленты добавьте последовательности escape новой строки, следуют символы keytip `lpszName`.  
  
##  <a name="settabcolor"></a>CMFCRibbonCategory::SetTabColor  
 Задает цвет категорию ленты.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Указывает новый цвет категории ленты.  
  
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
