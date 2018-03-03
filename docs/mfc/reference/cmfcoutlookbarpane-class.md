---
title: "Класс CMFCOutlookBarPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59eb92e44a26577866a797243f3a32d53b854365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcoutlookbarpane-class"></a>Класс CMFCOutlookBarPane
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Элементы управления, производные от [класса CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) , могут быть вставлены в панель Outlook ( [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)). Область панели Outlook содержит столбец больших кнопок. Пользователь может прокрутить список с кнопками вверх и вниз, если он больше области, в которой отображается. Когда пользователь окончательно удаляет область панели Outlook из панели Outlook, она может стать плавающей или прикрепиться к окну основного фрейма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](#addbutton)|Добавляет кнопку область панели Outlook.|  
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Определяет, можно ли прикрепить к другой панели или окне фрейма области. (Переопределяет [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|  
|`CMFCOutlookBarPane::CanBeRestored`|Определяет ли система восстановить панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCOutlookBarPane::ClearAll](#clearall)|Освобождает ресурсы, используемые изображения в область панели Outlook.|  
|[CMFCOutlookBarPane::Create](#create)|Создает область панели Outlook.|  
|`CMFCOutlookBarPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCOutlookBarPane::Dock`|Вызывается платформой, чтобы закрепить область панели Outlook. (Переопределяет `CPane::Dock`.)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Указывает ли стрелками на область панели Outlook переместить список кнопок на странице или в кнопку.|  
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Возвращает цвет обычный текст (невыбранных) область панели Outlook.|  
|`CMFCOutlookBarPane::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Определяет, существует ли фонового изображения, загруженные для область панели Outlook.|  
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может быть закреплено плавающей панели. (Переопределяет `CPane::IsChangeState`.)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Определяет, является ли граница кнопки затененные при выделенной кнопки и отображается фоновое изображение.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Вызывается платформой, когда область о к float. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Удаляет кнопки, которая имеет указанный идентификатор команды.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Восстанавливает первоначальное состояние панели инструментов. (Переопределяет [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|  
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Задает цвет фона.|  
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Задает фоновое изображение.|  
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Устанавливает область панели Outlook исходный набор кнопок.|  
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Задает количество пикселей заполнения, используемого вокруг кнопки в область панели Outlook.|  
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Задает цвета обычных и выделенный текст в область панели Outlook.|  
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Задает прозрачный цвет область панели Outlook.|  
|`CMFCOutlookBarPane::SmartUpdate`|Используется внутренним образом для обновления панели Outlook. (Переопределяет `CMFCToolBar::SmartUpdate`.)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Указывает, какие элементы контекстного меню отображаются в режим настройки.|  
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Удаляет все кнопки в область панели Outlook. (Переопределяет [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|  
  
## <a name="remarks"></a>Примечания  
 Сведения о реализации панель Outlook см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Пример панели Outlook см. пример проекта OutlookDemo.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать различные методы `CMFCOutlookBarPane` класса. В примере показано создание область панели Outlook, включить режим прокрутки страницы, Включение закрепления и задать цвет фона панели Outlook. Этот фрагмент кода является частью [пример нескольких представлениях Outlook](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]  
  
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
  
##  <a name="addbutton"></a>CMFCOutlookBarPane::AddButton  
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
 Указывает идентификатор ресурса точечного рисунка.  
  
 [in] `lpszLabel`  
 Задает текст кнопки.  
  
 [in] `iIdCommand`  
 Указывает идентификатор элемента управления button.  
  
 [in] `iInsertAt`  
 Отсчитываемый от нуля индекс указывает на страницу панели outlook, по которому следует вставить кнопку.  
  
 [in] `uiLabel`  
 Идентификатор строки ресурса.  
  
 [in] `szBmpFileName`  
 Задает имя файла образа диска для загрузки.  
  
 [in] `szLabel`  
 Задает текст кнопки.  
  
 [in] `hBmp`  
 Дескриптор для изображения кнопки.  
  
 [in] `hIcon`  
 Дескриптор значок кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка был успешно добавлен; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для вставки новой кнопки панели Outlook страницу. Изображение кнопки можно загрузить из ресурсов приложения или из файла на диске.  
  
 Если идентификатор страницы, указанной `uiPageID` равно -1, кнопка будет вставлена в первой страницы.  
  
 Если указанный индекс `iInsertAt` равно -1, будет добавлена кнопка в конце страницы.  
  
##  <a name="canbeattached"></a>CMFCOutlookBarPane::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="clearall"></a>CMFCOutlookBarPane::ClearAll  
 Освобождает ресурсы, используемые в образы на область панели Outlook.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод напрямую вызывает [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), который вызывается для изображения, которые используются в область панели Outlook.  
  
##  <a name="create"></a>CMFCOutlookBarPane::Create  
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
 Указывает родительского окна элемента управления области панели Outlook. Значение не должно быть равно `NULL`.  
  
 [in] `dwStyle`  
 Стиль окна.  Список стилей окна см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `uiID`  
 Идентификатор элемента управления. Должно быть уникальным для включения сохранения состояния элемента управления.  
  
 [in] `dwControlBarStyle`  
 Указывает специальные стили, определяющие поведение элемента управления области панели Outlook при отключении из панели Outlook.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для создания `CMFCOutlookBarPane` объекта, сначала вызовите конструктор, а затем вызвать `Create`, который создает панели управления панели Outlook и прикрепляет его к `CMFCOutlookBarPane` объекта.  
  
 Дополнительные сведения о `dwControlBarStyle` разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane::EnableContextMenuItems  
 Указывает, какие элементы контекстного меню отображаются в режим настройки.  
  
```  
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,  
    CMenu* pPopup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку панели инструментов, который был щелкнут пользователем.  
  
 [in] `pPopup`  
 Указатель в контекстном меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` ли контекстное меню отображается; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы изменить стандартный контекстное меню framework, платформа отображает в режим настройки.  
  
 Реализация по умолчанию проверяет режим настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) и, если оно равно `TRUE`, отключает все элементы контекстного меню за исключением **удалить**. Затем он просто передает входных параметров для `CMFCToolBar::EnableContextMenuItems`.  
  
> [!NOTE]
> *Контекстное меню* является синонимом для контекстного меню.  
  
##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane::EnablePageScrollMode  
 Указывает ли стрелками на область панели Outlook переместить список кнопок страницу за страницей, или кнопки, кнопки.  
  
```  
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPageScroll`  
 Если `TRUE`, включить режим прокрутки страницы. Если `FALSE`, отключите режим прокрутки страницы.  
  
##  <a name="getregularcolor"></a>CMFCOutlookBarPane::GetRegularColor  
 Возвращает обычного (то есть Невыбранный) цвет текста область панели Outlook.  
  
```  
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий цвет текста как значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCOutlookBarPane::SetTextColor](#settextcolor) для задания текущего цвета текста (обычных и выбранного) панели Outlook. Цвет по умолчанию можно получить, вызвав [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) функционировать с `COLOR_WINDOW` индекса.  
  
##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane::IsBackgroundTexture  
 Определяет, существует ли фонового изображения, загруженные для область панели Outlook.  
  
```  
BOOL IsBackgroundTexture() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если фоновое изображение для отображения; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Можно добавить фоновое изображение, вызвав [CMFCOutlookBarPane::SetBackImage](#setbackimage) функции.  
  
 Если фоновое изображение отсутствует, фон закрашивается цветом, указанный с помощью [CMFCOutlookBarPane::SetBackColor](#setbackcolor).  
  
##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane::IsDrawShadedHighlight  
 Определяет, является ли граница кнопки затененные при выделенной кнопки и отображается фоновое изображение.  
  
```  
BOOL IsDrawShadedHighlight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если границы кнопки затенены; в противном случае `FALSE`.  
  
##  <a name="removeallbuttons"></a>CMFCOutlookBarPane::RemoveAllButtons  
 Удаляет все кнопки в область панели Outlook.  
  
```  
virtual void RemoveAllButtons();
```  
  
##  <a name="removebutton"></a>CMFCOutlookBarPane::RemoveButton  
 Удаляет кнопки, которая имеет указанный идентификатор команды.  
  
```  
BOOL RemoveButton(UINT iIdCommand);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iIdCommand`  
 Указывает идентификатор команды кнопки для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки был успешно удален. `FALSE` Если указанный идентификатор команды недопустим.  
  
##  <a name="setbackcolor"></a>CMFCOutlookBarPane::SetBackColor  
 Задает цвет фона панели Outlook.  
  
```  
void SetBackColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 Указывает новый цвет фона.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию для задания текущего цвета фона панели Outlook. Цвет фона используется только в том случае, если фоновое изображение отсутствует.  
  
##  <a name="setbackimage"></a>CMFCOutlookBarPane::SetBackImage  
 Задает фоновое изображение.  
  
```  
void SetBackImage(UINT uiImageID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiImageID`  
 Указывает идентификатор ресурса изображения.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для установки Outlook линейки фоновое изображение. Управляемые список фоновые изображения, внедренные [CMFCToolBarImages класс](../../mfc/reference/cmfctoolbarimages-class.md) объекта.  
  
##  <a name="setdefaultstate"></a>CMFCOutlookBarPane::SetDefaultState  
 Устанавливает область панели Outlook исходный набор кнопок.  
  
```  
void SetDefaultState();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод восстанавливает исходный набор кнопок панели Outlook. Этот метод аналогичен `CMFCOutlookBarPane::RestoreOriginalstate`, за исключением того, что это не вызывает перерисовку область панели Outlook.  
  
##  <a name="setextraspace"></a>CMFCOutlookBarPane::SetExtraSpace  
 Задает количество пикселей заполнения, используемого вокруг кнопки в область панели Outlook.  
  
```  
void SetExtraSpace()  
```  
  
##  <a name="settextcolor"></a>CMFCOutlookBarPane::SetTextColor  
 Задает цвета обычных и выделенный текст в область панели Outlook.  
  
```  
void SetTextColor(
    COLORREF clrRegText,  
    COLORREF clrSelText=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrRegText`  
 Указывает новый цвет для невыбранных текста.  
  
 [in] `clrSelText`  
 Указывает новый цвет для выделенного текста.  
  
##  <a name="settransparentcolor"></a>CMFCOutlookBarPane::SetTransparentColor  
 Задает прозрачный цвет область панели Outlook.  
  
```  
void SetTransparentColor(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Указывает новый прозрачный цвет.  
  
### <a name="remarks"></a>Примечания  
 Прозрачный цвет, необходимого для отображения прозрачные изображения. Все вхождения этого цвета в изображении вместо окрашен цветом фона.  Нет, не наложения изображения фона и переднего плана.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
