---
title: "Класс CMFCRibbonCategory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCategory
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCategory class
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: 38
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
ms.openlocfilehash: dccbaac6450985f0d5255a790d83f374b52f06f9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncategory-class"></a>Класс CMFCRibbonCategory
`CMFCRibbonCategory` Класс реализует вкладки ленты, которая содержит группу [ленте панелей](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](#cmfcribboncategory)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonCategory::AddHidden](#addhidden)|Добавляет элемент hidden категория ленты.|  
|[CMFCRibbonCategory::AddPanel](#addpanel)|Добавляет новую панель категория ленты.|  
|[CMFCRibbonCategory::CopyFrom](#copyfrom)||  
|[CMFCRibbonCategory::FindByData](#findbydata)||  
|[CMFCRibbonCategory::FindByID](#findbyid)||  
|[CMFCRibbonCategory::FindPanelWithElem](#findpanelwithelem)||  
|[CMFCRibbonCategory::GetContextID](#getcontextid)|Возвращает идентификатор контекста категория ленты.|  
|[CMFCRibbonCategory::GetData](#getdata)|Возвращает определяемые пользователем данные, связанные с категорией ленты.|  
|[CMFCRibbonCategory::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonCategory::GetElements](#getelements)||  
|[CMFCRibbonCategory::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](#getfirstvisibleelement)|Получите первый видимый элемент, принадлежащие к категории ленты.|  
|[CMFCRibbonCategory::GetFocused](#getfocused)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonCategory::GetHighlighted](#gethighlighted)|Возвращает выделенный элемент.|  
|[CMFCRibbonCategory::GetImageCount](#getimagecount)||  
|[CMFCRibbonCategory::GetImageSize](#getimagesize)||  
|[CMFCRibbonCategory::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonCategory::GetLastVisibleElement](#getlastvisibleelement)|Получение последнего видимого элемента, принадлежащие к категории ленты|  
|[CMFCRibbonCategory::GetLargeImages](#getlargeimages)|Возвращает ссылку на список больших изображений, используемых категория ленты.|  
|[CMFCRibbonCategory::GetMaxHeight](#getmaxheight)||  
|[CMFCRibbonCategory::GetName](#getname)||  
|[CMFCRibbonCategory::GetPanel](#getpanel)|Возвращает указатель на панель ленты, расположенный по указанному индексу.|  
|[CMFCRibbonCategory::GetPanelCount](#getpanelcount)|Возвращает количество элементов управления ленты в категории «лента».|  
|[CMFCRibbonCategory::GetPanelFromPoint](#getpanelfrompoint)||  
|[CMFCRibbonCategory::GetPanelIndex](#getpanelindex)|Возвращает индекс указанного ленты панели.|  
|[CMFCRibbonCategory::GetParentButton](#getparentbutton)||  
|[CMFCRibbonCategory::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonCategory::GetParentRibbonBar](#getparentribbonbar)||  
|[CMFCRibbonCategory::GetRect](#getrect)||  
|[CMFCRibbonCategory::GetSmallImages](#getsmallimages)|Возвращает ссылку на список изображений небольшого размера, которые использует категорию.|  
|[CMFCRibbonCategory::GetTabColor](#gettabcolor)|Возвращает текущий цвет категории вкладки ленты.|  
|[CMFCRibbonCategory::GetTabRect](#gettabrect)||  
|[CMFCRibbonCategory::GetTextTopLine](#gettexttopline)||  
|[CMFCRibbonCategory::GetVisibleElements](#getvisibleelements)|Получите все видимые элементы, принадлежащие к категории ленты.|  
|[CMFCRibbonCategory::HighlightPanel](#highlightpanel)||  
|[CMFCRibbonCategory::HitTest](#hittest)||  
|[CMFCRibbonCategory::HitTestEx](#hittestex)||  
|[CMFCRibbonCategory::HitTestScrollButtons](#hittestscrollbuttons)||  
|[CMFCRibbonCategory::IsActive](#isactive)||  
|[CMFCRibbonCategory::IsVisible](#isvisible)|Определяет, видима ли категория ленты.|  
|[CMFCRibbonCategory::IsWindows7Look](#iswindows7look)|Указывает, имеет ли родительский ленты оформление Windows 7 стиля (небольшое приложение прямоугольная кнопка)|  
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
|[CMFCRibbonCategory::SetCollapseOrder](#setcollapseorder)|Определяет порядок свертывания панели ленты, присутствующие в категории «лента».|  
|[CMFCRibbonCategory::SetData](#setdata)|Сохраняет данные, определенные пользователем в категория ленты.|  
|[CMFCRibbonCategory::SetKeys](#setkeys)|Свойство KeyTip присваивается категория ленты.|  
|[CMFCRibbonCategory::SetName](#setname)||  
|[CMFCRibbonCategory::SetTabColor](#settabcolor)|Задает цвет категория ленты.|  
  
## <a name="remarks"></a>Примечания  
 Как правило, косвенно создать категорию ленты, вызвав [CMFCRibbonBar::AddCategory](../../mfc/reference/cmfcribbonbar-class.md#addcategory), который возвращает указатель на категории созданной ленты. Добавление панелей в категории, вызвав [CMFCRibbonCategory::AddPanel](#addpanel).  
  
 `CMFCRibbonTab` Класс прорисовывает категории ленты. Он является производным от [CMFCRibbonBaseElement класса](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
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
  
 На следующей диаграмме показан рисунок категории домашней из примера приложения RibbonApp.  
  
 ![Изображение CMFCRibbonCategory](../../mfc/reference/media/cmfcribboncategory.png "cmfcribboncategory")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCRibbonCategory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribboncategory.h  
  
##  <a name="a-nameaddhiddena--cmfcribboncategoryaddhidden"></a><a name="addhidden"></a>CMFCRibbonCategory::AddHidden  
 Добавляет элемент в указанной ленты в массив элементов ленты, которые отображаются в диалоговом окне настройки.  
  
```  
void AddHidden(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElem`  
 Указатель на элемент ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты в диалоговом окне настройки представлены команды, которые можно добавить на панель быстрого доступа.  
  
##  <a name="a-nameaddpanela--cmfcribboncategoryaddpanel"></a><a name="addpanel"></a>CMFCRibbonCategory::AddPanel  
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
 Указатель на данные класса среды выполнения в панели пользовательские ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый панель ленты, если метод был выполнен успешно; в противном случае `NULL` Если панель не была создана.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите создать панель настраиваемой ленты, необходимо указать сведения о его класса среды выполнения в `pRTI`. В классе panel настраиваемой ленты должен быть производным от `CMFCRibbonPanel` класса.  
  
 Значок по умолчанию для панели ленты отображается в том случае, если недостаточно места для отображения элементов ленты.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddPanel` метод `CMFCRibbonCategory` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#10;](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_1.cpp)]  
  
##  <a name="a-namecmfcribboncategorya--cmfcribboncategorycmfcribboncategory"></a><a name="cmfcribboncategory"></a>CMFCRibbonCategory::CMFCRibbonCategory  
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
 Идентификатор ресурса для списка изображений для небольших изображений, используемых элементов ленты в ribbon категории.  
  
 [in] `uiLargeImagesResID`  
 Идентификатор ресурса для списка изображений для больших изображений, используемых элементов ленты в ribbon категории.  
  
 [in] `sizeSmallImage`  
 По умолчанию размер изображений небольшого размера для элементов ленты в ribbon категории.  
  
 [in] `sizeLargeImage`  
 Размер больших изображений для элементов ленты в ribbon категории по умолчанию.  
  
##  <a name="a-namecopyfroma--cmfcribboncategorycopyfrom"></a><a name="copyfrom"></a>CMFCRibbonCategory::CopyFrom  
 Копирует состояние указанного [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) с текущим [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) объекта.  
  
```  
virtual void CopyFrom(CMFCRibbonCategory& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Исходный объект `CMFCRibbonCategory`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindbydataa--cmfcribboncategoryfindbydata"></a><a name="findbydata"></a>CMFCRibbonCategory::FindByData  
 Извлекает элемент ленты, связанные с указанными данными.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Данные, связанные с элементом ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`Чтобы включить элементы ленты для быстрого доступа в поиск; `FALSE` для исключения элементов ленты быстрого доступа в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindbyida--cmfcribboncategoryfindbyid"></a><a name="findbyid"></a>CMFCRibbonCategory::FindByID  
 Извлекает элемент ленты, связанные с идентификатором указанную команду.  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды, связанный с элементом ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`Чтобы включить элементы ленты для быстрого доступа в поиск; `FALSE` для исключения элементов ленты быстрого доступа в поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindpanelwithelema--cmfcribboncategoryfindpanelwithelem"></a><a name="findpanelwithelem"></a>CMFCRibbonCategory::FindPanelWithElem  
 Получает панель ленты, содержащей элемент указанной ленты.  
  
```  
CMFCRibbonPanel* FindPanelWithElem(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель на элемент ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcontextida--cmfcribboncategorygetcontextid"></a><a name="getcontextid"></a>CMFCRibbonCategory::GetContextID  
 Получает идентификатор категории ленты.  
  
```  
UINT GetContextID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста категория ленты.  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста равно 0, если категория ленты контекста не является категорией ленты.  
  
##  <a name="a-namegetdataa--cmfcribboncategorygetdata"></a><a name="getdata"></a>CMFCRibbonCategory::GetData  
 Получает определяемые пользователем данные, связанные с категорией ленты.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемые пользователем данные, связанные с категорией ленты.  
  
##  <a name="a-namegetdroppeddowna--cmfcribboncategorygetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonCategory::GetDroppedDown  
 Извлекает указатель на элемент ленты, в настоящее время имеет отображенным всплывающих меню.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetelementsa--cmfcribboncategorygetelements"></a><a name="getelements"></a>CMFCRibbonCategory::GetElements  
 Извлекает все элементы ленты в ribbon категории.  
  
```  
void GetElements(
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `arElements`  
 Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панель быстрого доступа включаются в массиве.  
  
##  <a name="a-namegetelementsbyida--cmfcribboncategorygetelementsbyid"></a><a name="getelementsbyid"></a>CMFCRibbonCategory::GetElementsByID  
 Извлекает все элементы ленты, связанные с идентификатором указанную команду.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray <CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды, связанный с элементом ленты.  
  
 [in, out] `arElements`  
 Ссылка на [CArray](../../mfc/reference/carray-class.md) элементов ленты.  
  
### <a name="remarks"></a>Примечания  
 Элементы ленты, которые предназначены для использования на панель быстрого доступа включаются в массиве.  
  
##  <a name="a-namegetfirstvisibleelementa--cmfcribboncategorygetfirstvisibleelement"></a><a name="getfirstvisibleelement"></a>CMFCRibbonCategory::GetFirstVisibleElement  
 Возвращает первый элемент видимым, к которой принадлежит категория ленты.  
  
```  
CMFCRibbonBaseElement* GetFirstVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первый элемент видимым; может быть `NULL` Если категории не имеют все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetfocuseda--cmfcribboncategorygetfocused"></a><a name="getfocused"></a>CMFCRibbonCategory::GetFocused  
 Возвращает элемент, имеющий фокус ввода.  
  
```  
CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с фокусом ввода или `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegethighlighteda--cmfcribboncategorygethighlighted"></a><a name="gethighlighted"></a>CMFCRibbonCategory::GetHighlighted  
 Возвращает выделенный элемент.  
  
```  
CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделенный элемент или `NULL` Если элементы не выделяются.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetimagecounta--cmfcribboncategorygetimagecount"></a><a name="getimagecount"></a>CMFCRibbonCategory::GetImageCount  
 Получает число изображений в списке указанный образ, который содержится в категории «лента».  
  
```  
int GetImageCount(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsLargeImage`  
 `TRUE`число изображений в списке большое изображение; `FALSE` число изображений в списке небольшое изображение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число изображений в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetimagesizea--cmfcribboncategorygetimagesize"></a><a name="getimagesize"></a>CMFCRibbonCategory::GetImageSize  
 Получает размер изображения в списке указанный образ, который содержится в категории «лента».  
  
```  
CSize GetImageSize(BOOL bIsLargeImage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsLargeImage`  
 `TRUE`для размера больших изображений. `FALSE` размер изображений небольшого размера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер изображения в списке указанное изображение.  
  
### <a name="remarks"></a>Примечания  
 Получить размер включает в себя глобальный образ коэффициент масштабирования.  
  
##  <a name="a-namegetitemidslista--cmfcribboncategorygetitemidslist"></a><a name="getitemidslist"></a>CMFCRibbonCategory::GetItemIDsList  
 Извлекает идентификаторы команд для элементов ленты, которые находятся в категории «лента».  
  
```  
void GetItemIDsList(
    CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lstItems`  
 Список идентификаторов команд для элементов ленты в ribbon категории.  
  
 [in] `bHiddenOnly`  
 `TRUE`Чтобы исключить элементы ленты, которые отображаются на панели ленты в ribbon категории; `FALSE` для включения всех элементов ленты в категории «лента».  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetlargeimagesa--cmfcribboncategorygetlargeimages"></a><a name="getlargeimages"></a>CMFCRibbonCategory::GetLargeImages  
 Получает список больших изображений, содержащихся в категории «лента».  
  
```  
CMFCToolBarImages& GetLargeImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список больших изображений, содержащихся в категории «лента».  
  
##  <a name="a-namegetlastvisibleelementa--cmfcribboncategorygetlastvisibleelement"></a><a name="getlastvisibleelement"></a>CMFCRibbonCategory::GetLastVisibleElement  
 Возвращает последний элемент видимым, к которой принадлежит категория ленты.  
  
```  
CMFCRibbonBaseElement* GetLastVisibleElement() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на последний элемент отображается; может быть `NULL` Если категории не имеют все видимые элементы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetmaxheighta--cmfcribboncategorygetmaxheight"></a><a name="getmaxheight"></a>CMFCRibbonCategory::GetMaxHeight  
 Возвращает максимальную высоту панели ленты, содержащихся в категории «лента».  
  
```  
int GetMaxHeight(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальная высота панели ленты, содержащихся в категории «лента».  
  
### <a name="remarks"></a>Примечания  
 Значение, полученное включает высоту верхнего и нижнего полей для панели ленты.  
  
##  <a name="a-namegetnamea--cmfcribboncategorygetname"></a><a name="getname"></a>CMFCRibbonCategory::GetName  
 Получает имя категории ленты.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetpanela--cmfcribboncategorygetpanel"></a><a name="getpanel"></a>CMFCRibbonCategory::GetPanel  
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
  
##  <a name="a-namegetpanelcounta--cmfcribboncategorygetpanelcount"></a><a name="getpanelcount"></a>CMFCRibbonCategory::GetPanelCount  
 Возвращает количество элементов управления ленты в категории «лента».  
  
```  
int GetPanelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов управления ленты в категория ленты.  
  
##  <a name="a-namegetpanelfrompointa--cmfcribboncategorygetpanelfrompoint"></a><a name="getpanelfrompoint"></a>CMFCRibbonCategory::GetPanelFromPoint  
 Извлекает указатель на панель ленты, если заданная точка находится в нем.  
  
```  
CMFCRibbonPanel* GetPanelFromPoint(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только панели ленты, содержащихся в категории «лента».  
  
##  <a name="a-namegetpanelindexa--cmfcribboncategorygetpanelindex"></a><a name="getpanelindex"></a>CMFCRibbonCategory::GetPanelIndex  
 Возвращает отсчитываемый от нуля индекс панели указанной ленты.  
  
```  
int GetPanelIndex(const CMFCRibbonPanel* pPanel) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPanel`  
 Указатель на панель ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс панели указанного ленты, если метод был выполнен успешно; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Поиск будет вестись только панели ленты, содержащихся в категории «лента».  
  
##  <a name="a-namegetparentbuttona--cmfcribboncategorygetparentbutton"></a><a name="getparentbutton"></a>CMFCRibbonCategory::GetParentButton  
 Получает родительский элемент ленты категория ленты.  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на родительский элемент ленты, или `NULL` Если нет родительского элемента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetparentmenubara--cmfcribboncategorygetparentmenubar"></a><a name="getparentmenubar"></a>CMFCRibbonCategory::GetParentMenuBar  
 Возвращает указатель на строку меню родительского `CMFCRibbonCategory` объекта.  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает содержимое `m_pParentMenuBar` защищенных членов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetparentribbonbara--cmfcribboncategorygetparentribbonbar"></a><a name="getparentribbonbar"></a>CMFCRibbonCategory::GetParentRibbonBar  
 Извлекает строки ленты родительской категории ленты.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панель ленты родительской категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetrecta--cmfcribboncategorygetrect"></a><a name="getrect"></a>CMFCRibbonCategory::GetRect  
 Возвращает прямоугольник, отображаемое для категории ленты.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отображаемый прямоугольник для категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Отображаемый прямоугольник для категории ленты не включает вкладку «Категория».  
  
##  <a name="a-namegetsmallimagesa--cmfcribboncategorygetsmallimages"></a><a name="getsmallimages"></a>CMFCRibbonCategory::GetSmallImages  
 Получает список изображений небольшого размера, содержащихся в категории «лента».  
  
```  
CMFCToolBarImages& GetSmallImages();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Список изображений небольшого размера, содержащихся в категории «лента».  
  
##  <a name="a-namegettabcolora--cmfcribboncategorygettabcolor"></a><a name="gettabcolor"></a>CMFCRibbonCategory::GetTabColor  
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
  
##  <a name="a-namegettabrecta--cmfcribboncategorygettabrect"></a><a name="gettabrect"></a>CMFCRibbonCategory::GetTabRect  
 Возвращает прямоугольник, отображаемое для категории вкладки ленты.  
  
```  
CRect GetTabRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник отображения для категории вкладки ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettexttoplinea--cmfcribboncategorygettexttopline"></a><a name="gettexttopline"></a>CMFCRibbonCategory::GetTextTopLine  
 Возвращает вертикальное расположение текста на кнопок ленты в ribbon категории отображения больших изображений.  
  
```  
int GetTextTopLine() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вертикальное расположение текста в пикселях на отображение больших изображений кнопок ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetvisibleelementsa--cmfcribboncategorygetvisibleelements"></a><a name="getvisibleelements"></a>CMFCRibbonCategory::GetVisibleElements  
 Извлекает все видимые элементы, принадлежащие к категории ленты.  
  
```  
void GetVisibleElements(
    CArray <CMFCRibbonBaseElement*,  
    CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Параметры  
 `arElements`  
 Массив всех видимых элементов.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehighlightpanela--cmfcribboncategoryhighlightpanel"></a><a name="highlightpanel"></a>CMFCRibbonCategory::HighlightPanel  
 Выделяет панель указанной ленты.  
  
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
 Указатель на панель ранее выделенные ленты; в противном случае `NULL` Если нет панели ленты выделяется при вызове этого метода.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о выделении панель ленты см. в разделе [CMFCRibbonPanel::Highlight](../../mfc/reference/cmfcribbonpanel-class.md#highlight).  
  
##  <a name="a-namehittesta--cmfcribboncategoryhittest"></a><a name="hittest"></a>CMFCRibbonCategory::HitTest  
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
 `TRUE`Чтобы проверить заголовок панели ленты; `FALSE` исключить заголовок панели ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые находятся в категории «лента».  
  
##  <a name="a-namehittestexa--cmfcribboncategoryhittestex"></a><a name="hittestex"></a>CMFCRibbonCategory::HitTestEx  
 Возвращает отсчитываемый от нуля индекс элемента ленты, если заданная точка находится в нем.  
  
```  
int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс элемента ленты, если метод был выполнен успешно; в противном случае — значение -1.  
  
### <a name="remarks"></a>Примечания  
 Проверяются только элементы ленты, которые находятся в категории «лента».  
  
##  <a name="a-namehittestscrollbuttonsa--cmfcribboncategoryhittestscrollbuttons"></a><a name="hittestscrollbuttons"></a>CMFCRibbonCategory::HitTestScrollButtons  
 Если точка находится в рамках кнопки прокрутки влево или вправо категория ленты, возвращает указатель на эту кнопку.  
  
```  
CMFCRibbonBaseElement* HitTestScrollButtons(CPoint point) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Точка для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `point` находится внутри ограничивающего прямоугольника либо влево или кнопки прокрутки вправо категория ленты, возвращает указатель на эту кнопку или в противном случае — возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisactivea--cmfcribboncategoryisactive"></a><a name="isactive"></a>CMFCRibbonCategory::IsActive  
 Указывает, является ли категория ленты активной категории на ленте.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория ленты активной категории; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категория ленты, активная отображает его панели ленты.  
  
##  <a name="a-nameisvisiblea--cmfcribboncategoryisvisible"></a><a name="isvisible"></a>CMFCRibbonCategory::IsVisible  
 Указывает, видима ли категория ленты.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория ленты является видимым. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категории ленты, которые являются видимыми вкладка категории.  
  
##  <a name="a-nameiswindows7looka--cmfcribboncategoryiswindows7look"></a><a name="iswindows7look"></a>CMFCRibbonCategory::IsWindows7Look  
 Указывает, имеет ли ленты родительского поиска (небольшое приложение прямоугольная кнопка) Windows 7.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительский ленты Windows 7 поиска; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namenotifycontrolcommanda--cmfcribboncategorynotifycontrolcommand"></a><a name="notifycontrolcommand"></a>CMFCRibbonCategory::NotifyControlCommand  
 Доставляет сообщение команды WM_NOTIFY все `CMFCRibbonPanel` элементов в `CMFCRibbonCategory` до обработки сообщения.  
  
```  
virtual BOOL NotifyControlCommand(
    BOOL bAccelerator,  
    int nNotifyCode,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAccelerator`  
 `TRUE`Если эта команда была создана из ускорителя или `FALSE` в противном случае.  
  
 [in] `nNotifyCode`  
 Код уведомления.  
  
 [in] `wParam`  
 Поле WPARAM сообщения.  
  
 [in] `lParam`  
 Поле LPARAM сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если сообщение было обработано, или `FALSE` Если нет.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoncancelmodea--cmfcribboncategoryoncancelmode"></a><a name="oncancelmode"></a>CMFCRibbonCategory::OnCancelMode  
 Вызывает режим "Отмена" во всех `CMFCRibbonPanel` элементы `CMFCRibbonCategory`.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawa--cmfcribboncategoryondraw"></a><a name="ondraw"></a>CMFCRibbonCategory::OnDraw  
 Вызывается платформой для рисования категория ленты.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawimagea--cmfcribboncategoryondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonCategory::OnDrawImage  
 Вызывается платформой для рисования указанное изображение с категорией ленты.  
  
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
 `TRUE`Если изображение имеет большой размер; `FALSE` Если изображение малого размера.  
  
 [in] `nImageIndex`  
 Отсчитываемый от нуля индекс изображения в массиве образ, который содержится в категории «лента».  
  
 [in] `bCenter`  
 `TRUE`центр изображения в прямоугольник отображения; `FALSE` для прорисовки изображения в верхнем левом углу отображаемый прямоугольник.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenubordera--cmfcribboncategoryondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCRibbonCategory::OnDrawMenuBorder  
 Вызывается платформой для рисования границы всплывающее меню.  
  
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
 По умолчанию этот метод не выполняет никаких действий. Переопределите этот метод для рисования границы всплывающее меню.  
  
##  <a name="a-nameonkeya--cmfcribboncategoryonkey"></a><a name="onkey"></a>CMFCRibbonCategory::OnKey  
 Вызывается платформой, когда пользователь нажимает клавишу клавиатуры.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 `nChar`  
 Виртуальный код клавиши для ключа, нажал пользователь.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonlbuttondowna--cmfcribboncategoryonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonCategory::OnLButtonDown  
 Вызывается платформой для извлечения элемента ленты в указанной точке при нажатии левой кнопки мыши.  
  
```  
virtual CMFCRibbonBaseElement* OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя мыши относительно левого верхнего угла окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если метод был выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonlbuttonupa--cmfcribboncategoryonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonCategory::OnLButtonUp  
 Вызывается платформой, когда пользователь отпускает кнопку мыши и указатель находится над категория ленты.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonmousemovea--cmfcribboncategoryonmousemove"></a><a name="onmousemove"></a>CMFCRibbonCategory::OnMouseMove  
 Вызывается инфраструктурой при перемещении указателя на ленте, чтобы обновить список категорий ленты.  
  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Координаты x и y указателя относительно верхнего левого угла окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrtlchangeda--cmfcribboncategoryonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonCategory::OnRTLChanged  
 Вызывается инфраструктурой при изменении направления макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
 `TRUE`Если макет справа налево; `FALSE` Если макет справа налево.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет расположение всех панелей ленты и элементы ленты, которые находятся в категории «лента».  
  
##  <a name="a-nameonscrollhorza--cmfcribboncategoryonscrollhorz"></a><a name="onscrollhorz"></a>CMFCRibbonCategory::OnScrollHorz  
 Прокручивает категория ленты в горизонтальном направлении.  
  
```  
virtual BOOL OnScrollHorz(
    BOOL bScrollLeft,  
    int nScrollOffset = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bScrollLeft`  
 `TRUE`для прокрутки влево; `FALSE` выполнить прокрутку вправо.  
  
 [in] `nScrollOffset`  
 Расстояние прокрутки в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория ленты перемещен в горизонтальном направлении; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonupdatecmduia--cmfcribboncategoryonupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCRibbonCategory::OnUpdateCmdUI  
 Вызовы `OnUpdateCmdUI` функции-члена в каждом из `CMFCRibbonPanel` элементы `CMFCRibbonCategory` Включение и отключение элементов пользовательского интерфейса в них.  
  
```  
virtual void OnUpdateCmdUI(
    CMFCRibbonCmdUI* pCmdUI,  
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCmdUI`  
 Указатель на `CMFCRibbonCmdUI` объект, который определяет элементы пользовательского интерфейса должны быть включена и который, следует отключить.  
  
 [in] `pTarget`  
 Указатель на окно, которое определяет включение или отключение элементов пользовательского интерфейса.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`отключение элемента пользовательского интерфейса, если обработчик не определен в схеме сообщений; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namerecalclayouta--cmfcribboncategoryrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonCategory::RecalcLayout  
 Изменение макета всех элементов управления на ленте категории.  
  
```  
virtual void RecalcLayout(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для категории ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremovepanela--cmfcribboncategoryremovepanel"></a><a name="removepanel"></a>CMFCRibbonCategory::RemovePanel  
 Удаляет панель ленты из категории ленты.  
  
```cpp  
BOOL RemovePanel(
    int nIndex,  
    BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Номер индекса панели для удаления. Полученные с помощью вызова [CMFCRibbonCategory::GetPanelIndex](#getpanelindex) метод.  
  
 [in] `bDelete`  
 `TRUE`Чтобы удалить объект панели из памяти; `FALSE` удаляемый объект панели без его удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE`, если метод выполнен успешно; в противном случае — значение `FALSE`.  
  
##  <a name="a-namerepospanelsa--cmfcribboncategoryrepospanels"></a><a name="repospanels"></a>CMFCRibbonCategory::ReposPanels  
 Изменение макета всех элементов управления на панели ленты, содержащихся в категории «лента».  
  
```  
virtual void ReposPanels(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели ленты, содержащихся в категории «лента».  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetcollapseordera--cmfcribboncategorysetcollapseorder"></a><a name="setcollapseorder"></a>CMFCRibbonCategory::SetCollapseOrder  
 Определяет порядок, в котором сворачивать панели ленты категория ленты.  
  
```  
void SetCollapseOrder(const CArray<int,int>& arCollapseOrder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `arCollapseOrder`  
 Указывает порядок свернуть. Массив содержит отсчитываемые с нуля индексы панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Библиотека определяет порядок свернуть. Однако это поведение можно настроить, предоставляя список индексов, которое указывает порядок Свернуть категорию.  
  
 Если категории обнаруживает наличие свернуть панель ленты, он ищет следующего элемента в указанном списке. Если список пуст или не определены достаточно элементов, категории использует внутренний алгоритм.  
  
 Например категория имеет три панели ленты и можно свернуть несколько раз, пока не будут полностью свернутое состояние всех панелей. Можно установить следующий порядок свернуть: 0, 0, 2, 2. В этом случае категория будет свернуть панель 0 два раза, панели 2 двух раз. Панель, которая содержит индекс 1 остается свернут.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetCollapseOrder` метод `CMFCRibbonCategory` класса. В примере показано, как создать массив для заказа свернуть и как задать порядок Свернуть категорию ленты.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#13;](../../mfc/reference/codesnippet/cpp/cmfcribboncategory-class_2.cpp)]  
  
##  <a name="a-namesetdataa--cmfcribboncategorysetdata"></a><a name="setdata"></a>CMFCRibbonCategory::SetData  
 Задает определяемые пользователем данные, связываемого с категорией ленты.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Определенные пользователем данные.  
  
##  <a name="a-namesetkeysa--cmfcribboncategorysetkeys"></a><a name="setkeys"></a>CMFCRibbonCategory::SetKeys  
 Свойство KeyTip присваивается категория ленты.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszKeys`  
 Значение свойства keytip текст.  
  
### <a name="remarks"></a>Примечания  
 Ключевые подсказки отображаются, когда пользователь нажимает клавишу Alt и клавишу F10.  
  
##  <a name="a-namesetnamea--cmfcribboncategorysetname"></a><a name="setname"></a>CMFCRibbonCategory::SetName  
 Присваивает имя и значение свойства keytip категория ленты.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя и значение свойства keytip категории ленты.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать значение свойства keytip категории ленты, добавления новой строки последовательности, следуют символы, значение свойства keytip `lpszName`.  
  
##  <a name="a-namesettabcolora--cmfcribboncategorysettabcolor"></a><a name="settabcolor"></a>CMFCRibbonCategory::SetTabColor  
 Задает цвет категория ленты.  
  
```  
void SetTabColor(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Указывает новый цвет категория ленты.  
  
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
 [CObject-класс](../../mfc/reference/cobject-class.md)

