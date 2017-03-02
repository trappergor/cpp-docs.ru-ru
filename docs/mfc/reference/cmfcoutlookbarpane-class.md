---
title: "Класс CMFCOutlookBarPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
dev_langs:
- C++
helpviewer_keywords:
- Dock method
- IsChangeState method
- SmartUpdate method
- OnBeforeFloat method
- RestoreOriginalstate method
- CMFCOutlookBarPane class
- CanBeRestored method
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
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
ms.openlocfilehash: da4fab1a6d94e962090f21414062dc2da0c9482c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbarpane-class"></a>Класс CMFCOutlookBarPane
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Элемент управления, производный от [класса CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) , могут быть вставлены в панель Outlook ( [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md)). Область панели Outlook содержит столбец больших кнопок. Пользователь может прокрутить список с кнопками вверх и вниз, если он больше области, в которой отображается. Когда пользователь окончательно удаляет область панели Outlook из панели Outlook, она может стать плавающей или прикрепиться к окну основного фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Добавляет кнопку область панели Outlook.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Определяет ли область можно прикрепить к другой области окна или рамке окна. (Переопределяет [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|Определяет ли система восстановить панели инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Освобождает ресурсы, используемые изображения в область панели Outlook.|  
|[CMFCOutlookBarPane::Create](#create)|Создает область панели Outlook.|  
|`CMFCOutlookBarPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCOutlookBarPane::Dock`|Вызывается средой, чтобы закрепить область панели Outlook. (Переопределяет `CPane::Dock`.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Указывает ли стрелок прокрутки на область панели Outlook переместить список кнопок на странице или в кнопку.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Возвращает цвет обычный текст (не выбрано) область панели Outlook.|  
|`CMFCOutlookBarPane::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Определяет, будет ли фоновое изображение, загрузки для область панели Outlook.|  
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может ли закрепляться плавающей панели. (Переопределяет `CPane::IsChangeState`.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Определяет границы кнопки затененный при выделенной кнопке и фоновое изображение отображается.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Вызывается инфраструктурой при область о число с плавающей запятой. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Удаляет кнопку, которая имеет идентификатор указанной команды.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Восстанавливает первоначальное состояние панели инструментов. (Переопределяет [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Задает цвет фона.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Задает фоновое изображение.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Восстанавливает исходный набор кнопок область панели Outlook.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Задает количество точек поля вокруг кнопки в область панели Outlook.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Задает цвета обычных и выделенного текста в область панели Outlook.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Задает прозрачный цвет для область панели Outlook.|  
|`CMFCOutlookBarPane::SmartUpdate`|Используется для обновления панели Outlook. (Переопределяет `CMFCToolBar::SmartUpdate`.)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Указывает, какие элементы контекстного меню отображаются в режим настройки.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Удаляет все кнопки в область панели Outlook. (Переопределяет [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>Примечания  
 Сведения о реализации панель Outlook в разделе [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Пример панели Outlook см. пример проекта OutlookDemo.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных методов `CMFCOutlookBarPane` класса. В примере показано создание область панели Outlook, включить режим прокрутки страниц, закрепление и задать цвет фона панели Outlook. Этот фрагмент кода является частью [нескольких представлений Outlook образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&#3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&#4;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxoutlookbarpane.h  
  
##  <a name="a-nameaddbuttona--cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a>CMFCOutlookBarPane::AddButton  
 Добавляет кнопку область панели Outlook.  
  
```  
BOOL AddButton(
    UINT uiImage,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    UINT uiImage,  
    UINT uiLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    LPCTSTR szBmpFileName,  
    LPCTSTR szLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HBITMAP hBmp,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1);

 
BOOL AddButton(
    HICON hIcon,  
    LPCTSTR lpszLabel,  
    UINT iIdCommand,  
    int iInsertAt=-1,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiImage`  
 Указывает идентификатор ресурса растрового изображения.  
  
 [in] `lpszLabel`  
 Задает текст кнопки.  
  
 [in] `iIdCommand`  
 Указывает идентификатор элемента управления button.  
  
 [in] `iInsertAt`  
 Отсчитываемый от нуля индекс указывает на странице панели outlook, по которому следует вставить кнопку.  
  
 [in] `uiLabel`  
 Идентификатор строки ресурса.  
  
 [in] `szBmpFileName`  
 Задает имя файла образа диска для загрузки.  
  
 [in] `szLabel`  
 Задает текст кнопки.  
  
 [in] `hBmp`  
 Дескриптор точечного рисунка для кнопки.  
  
 [in] `hIcon`  
 Дескриптор значок кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка был успешно добавлен; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для вставки новой кнопки панели Outlook страницу. Изображение кнопки можно загрузить из ресурсов приложения или из файла на диске.  
  
 Если идентификатор страницы, указанной `uiPageID` равно -1, кнопки вставляется в первой страницы.  
  
 Если указанный индекс `iInsertAt` равно -1, будет добавлена кнопка в конце страницы.  
  
##  <a name="a-namecanbeattacheda--cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameclearalla--cmfcoutlookbarpaneclearall"></a><a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Освобождает ресурсы, используемые изображений на область панели Outlook.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод напрямую вызывает [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), который вызывается для изображений, используемых в область панели Outlook.  
  
##  <a name="a-namecreatea--cmfcoutlookbarpanecreate"></a><a name="create"></a>CMFCOutlookBarPane::Create  
 Создает область панели Outlook.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT uiID=(UINT)-1,  
    DWORD dwControlBarStyle=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указывает родительского окна элемента управления панели Outlook. Значение не должно быть равно `NULL`.  
  
 [in] `dwStyle`  
 Стиль окна.  Список стилей окна, в разделе [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `uiID`  
 Идентификатор элемента управления. Должно быть уникальным, чтобы включить сохранение состояния элемента управления.  
  
 [in] `dwControlBarStyle`  
 Указывает специальные стили, определяющие поведение элемента управления панели Outlook при отсоединении их от панели Outlook.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для создания `CMFCOutlookBarPane` , сначала вызовите конструктор, а затем вызвать `Create`, который создает панели управления панели Outlook и присоединяет его к `CMFCOutlookBarPane` объекта.  
  
 Дополнительные сведения о `dwControlBarStyle` разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
##  <a name="a-nameenablecontextmenuitemsa--cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 Указывает, какие элементы контекстного меню отображаются в режим настройки.  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку панели инструментов, нажата.  
  
 [in] `pPopup`  
 Указатель в контекстном меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` если должен быть контекстное меню отображается; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы изменить стандартный контекстное меню framework, платформа отображает в режим настройки.  
  
 Реализация по умолчанию проверяет режим настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) и, если задано значение `TRUE`, отключает все элементы контекстного меню за исключением **удаление**. После этого он просто передает входных параметров для `CMFCToolBar::EnableContextMenuItems`.  
  
> [!NOTE]
> *Контекстное меню* является синонимом для контекстного меню.  
  
##  <a name="a-nameenablepagescrollmodea--cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Указывает ли стрелок прокрутки на область панели Outlook переместить список кнопок страницу по или по кнопка.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPageScroll`  
 Если `TRUE`, включить режим прокрутки страниц. Если `FALSE`, отключите режим прокрутки страниц.  
  
##  <a name="a-namegetregularcolora--cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 Возвращает обычный (то есть невыбранных) цвет текста область панели Outlook.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет текста как значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCOutlookBarPane::SetTextColor](#settextcolor) задать текущий цвет текста (обычных и выбранного) панели Outlook. Цвет текста по умолчанию можно получить, вызвав [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) работать с `COLOR_WINDOW` индекса.  
  
##  <a name="a-nameisbackgroundtexturea--cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Определяет, будет ли фоновое изображение, загрузки для область панели Outlook.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если фоновое изображение для отображения; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Можно добавить фоновое изображение, вызвав [CMFCOutlookBarPane::SetBackImage](#setbackimage) функции.  
  
 Если фоновое изображение отсутствует, фон закрашивается цветом, указанные с помощью [CMFCOutlookBarPane::SetBackColor](#setbackcolor).  
  
##  <a name="a-nameisdrawshadedhighlighta--cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 Определяет границы кнопки затененный при выделенной кнопке и фоновое изображение отображается.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если границы кнопки затенены; в противном случае `FALSE`.  
  
##  <a name="a-nameremoveallbuttonsa--cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Удаляет все кнопки в область панели Outlook.  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="a-nameremovebuttona--cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a>CMFCOutlookBarPane::RemoveButton  
 Удаляет кнопку, которая имеет идентификатор указанной команды.  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIdCommand`  
 Указывает идентификатор команды кнопки для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки был успешно удален; `FALSE` если заданный идентификатор команды не является допустимым.  
  
##  <a name="a-namesetbackcolora--cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Задает цвет фона панели Outlook.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Указывает новый цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию для задания текущий цвет фона панели Outlook. Цвет фона используется только в том случае, если фоновое изображение отсутствует.  
  
##  <a name="a-namesetbackimagea--cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 Задает фоновое изображение.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiImageID`  
 Указывает идентификатор ресурса изображения.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы задать Outlook линейки фоновое изображение. Управляемый список фоновые изображения, внедренные [CMFCToolBarImages класс](../../mfc/reference/cmfctoolbarimages-class.md) объекта.  
  
##  <a name="a-namesetdefaultstatea--cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 Восстанавливает исходный набор кнопок область панели Outlook.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает исходный набор кнопок панели Outlook. Этот метод аналогичен `CMFCOutlookBarPane::RestoreOriginalstate`, за исключением того, что не вызывает обновление область панели Outlook.  
  
##  <a name="a-namesetextraspacea--cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Задает количество точек поля вокруг кнопки в область панели Outlook.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="a-namesettextcolora--cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Задает цвета обычных и выделенного текста в область панели Outlook.  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrRegText`  
 Указывает новый цвет для невыбранных текста.  
  
 [in] `clrSelText`  
 Указывает новый цвет для выбранного текста.  
  
##  <a name="a-namesettransparentcolora--cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor  
 Задает прозрачный цвет для область панели Outlook.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Указывает новый прозрачный цвет.  
  
### <a name="remarks"></a>Примечания  
 Прозрачный цвет необходим для отображения прозрачные изображения. Все вхождения этого цвета в изображении вместо окрашен цветом фона.  Нет, не наложения изображений фона и переднего плана.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

