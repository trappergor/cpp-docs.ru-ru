---
title: "Класс CMFCToolBarMenuButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarMenuButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarMenuButton class
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
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
ms.openlocfilehash: a06fd323862c6869463b4db0977816b5707c3e18
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarmenubutton-class"></a>Класс CMFCToolBarMenuButton
Кнопка панели инструментов, содержащая всплывающее меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](#cmfctoolbarmenubutton)|Создает объект `CMFCToolBarMenuButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](#comparewith)|Сравнивает данный экземпляр с указанным `CMFCToolBarButton` объекта. (Переопределяет [CMFCToolBarButton::CompareWith](../../mfc/reference/cmfctoolbarbutton-class.md#comparewith).)|  
|[CMFCToolBarMenuButton::CopyFrom](#copyfrom)|Копирует свойства кнопки панели инструментов, для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)|Инициализирует меню панели инструментов из дескриптора меню Windows.|  
|[CMFCToolBarMenuButton::CreateMenu](#createmenu)|Создает меню Windows, которое состоит из команд в меню панели инструментов. Возвращает дескриптор меню Windows.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](#createpopupmenu)|Создает объект всплывающего меню ( [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md)) для отображения меню панели инструментов.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](#enablequickcustomize)||  
|[CMFCToolBarMenuButton::GetCommands](#getcommands)|Предоставляет доступ только для чтения список команд в меню панели инструментов.|  
|[CMFCToolBarMenuButton::GetImageRect](#getimagerect)|Возвращает ограничивающий прямоугольник для изображения на кнопке.|  
|[CMFCToolBarMenuButton::GetPaletteRows](#getpaletterows)|Возвращает количество строк во всплывающем меню, когда меню в режиме палитры.|  
|[CMFCToolBarMenuButton::GetPopupMenu](#getpopupmenu)|Возвращает указатель на объект всплывающего меню, связанное с кнопкой.|  
|[CMFCToolBarMenuButton::HasButton](#hasbutton)||  
|[CMFCToolBarMenuButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarMenuButton::IsBorder](#isborder)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](#isclickedonmenu)||  
|[CMFCToolBarMenuButton::IsDroppedDown](#isdroppeddown)|Определяет, будет ли отображаться во всплывающем меню.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Вызывается средой, чтобы определить, является ли пользователь может открыть вложенное меню из выбранного пункта меню.|  
|[CMFCToolBarMenuButton::IsExclusive](#isexclusive)|Определяет, является ли кнопки в монопольном режиме, то есть ли всплывающие меню остается открытым, даже в том случае, когда пользователь перемещает указатель на другую панель инструментов или кнопка.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](#ismenupalettemode)|Определяет, является ли контекстного меню в режиме палитры.|  
|[CMFCToolBarMenuButton::IsQuickMode](#isquickmode)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](#istearoffmenu)|Определяет строку перемещаемые во всплывающем меню.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](#onaftercreatepopupmenu)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](#onbeforedrag)|Указывает, можно ли перетаскивать кнопки. (Переопределяет [CMFCToolBarButton::OnBeforeDrag](../../mfc/reference/cmfctoolbarbutton-class.md#onbeforedrag).)|  
|[CMFCToolBarMenuButton::OnCalculateSize](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarMenuButton::OnCancelMode](#oncancelmode)|Вызывается платформой для обработки [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) сообщений. (Переопределяет [CMFCToolBarButton::OnCancelMode](../../mfc/reference/cmfctoolbarbutton-class.md#oncancelmode).)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarMenuButton::OnClick](#onclick)|Вызывается инфраструктурой при нажатии кнопки мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](#onclickmenuitem)|Вызывается платформой, когда пользователь выбирает элемент в раскрывающемся меню.|  
|[CMFCToolBarMenuButton::OnContextHelp](#oncontexthelp)|Вызывается инфраструктурой при обработке родительского инструментов `WM_HELPHITTEST` сообщение. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCToolBarMenuButton::OnDraw](#ondraw)|Вызывается платформой для отображения кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой для отображения кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](#openpopupmenu)|Вызывается инфраструктурой при открытии контекстного меню.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](#resetimagetodefault)|Задает значение по умолчанию изображение, связанное с кнопкой. (Переопределяет [CMFCToolBarButton::ResetImageToDefault](../../mfc/reference/cmfctoolbarbutton-class.md#resetimagetodefault).)|  
|[CMFCToolBarMenuButton::SaveBarState](#savebarstate)|Сохраняет состояние кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SaveBarState](../../mfc/reference/cmfctoolbarbutton-class.md#savebarstate).)|  
|[CMFCToolBarMenuButton::Serialize](#serialize)|Считывает этот объект из архива и записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCToolBarMenuButton::SetACCData](#setaccdata)|Заполняет предоставленный `CAccessibilityData` объекта специальных возможностей данными из кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|[CMFCToolBarMenuButton::SetMenuOnly](#setmenuonly)|Указывает, можно ли добавить кнопки панели инструментов.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)|Указывает, является ли контекстного меню в режиме палитры.|  
|[CMFCToolBarMenuButton::SetMessageWnd](#setmessagewnd)||  
|[CMFCToolBarMenuButton::SetRadio](#setradio)|Принудительно кнопку меню панели инструментов, чтобы отобразить значок, указывающий, что установлен флажок.|  
|[CMFCToolBarMenuButton::SetTearOff](#settearoff)|Задает перемещаемое строке идентификатор для контекстного меню.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](#drawdocumenticon)|Рисует значка на кнопке меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw](#m_balwayscallownerdraw)|Если `TRUE`, платформа всегда вызывает [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) при рисовании кнопки.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCToolBarMenuButton` может отображаться как меню, элемент меню имеет вложенные меню, кнопки, которая выполняет команду или отображает меню или кнопку, отображающую только меню. Определить поведение и внешний вид кнопки меню путем указания параметров, таких как изображения, текст, дескриптор меню и команды идентификатор, связанный с кнопкой в конструкторе `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Пользовательский класс, производный от `CMFCToolbarMenuButton` необходимо использовать класс [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос. [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) макрос выдает ошибку при закрытии приложения.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить `CMFCToolBarMenuButton` объекта. Код иллюстрирует способ указать, что раскрывающееся меню в режиме палитры и укажите идентификатор панели перемещаемые, который создается при перетаскивании кнопки меню из строки меню. Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#10;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarmenubutton.h  
  
##  <a name="a-namecmfctoolbarmenubuttona--cmfctoolbarmenubuttoncmfctoolbarmenubutton"></a><a name="cmfctoolbarmenubutton"></a>CMFCToolBarMenuButton::CMFCToolBarMenuButton  
 Создает объект `CMFCToolBarMenuButton`.  
  
```  
CMFCToolBarMenuButton();
CMFCToolBarMenuButton(const CMFCToolBarMenuButton& src);

CMFCToolBarMenuButton(
    UINT uiID,  
    HMENU hMenu,  
    int iImage,  
    LPCTSTR lpszText=NULL,  
    BOOL bUserButton=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Существующий `CMFCToolBarMenuButton` объекта должно быть скопировано в это `CMFCToolBarMenuButton` объекта.  
  
 [in] `uiID`  
 Идентификатор выполнения команды при нажатии кнопки. или ( `UINT`) -1 для кнопки меню, непосредственно выполнить команду.  
  
 [in] `hMenu`  
 Дескриптор меню; или `NULL` Если нет кнопки меню.  
  
 [in] `iImage`  
 Индекс изображения для кнопки. или -1, если эта кнопка отсутствует значок или использует значок для команды, заданной параметром `uiID`. Индекс является одинаковым для каждого `CMFCToolBarImages` объект в приложении.  
  
 [in] `lpszText`  
 Текст кнопки меню панели инструментов.  
  
 [in] `bUserButton`  
 `TRUE`Если на кнопке отображается изображение, определяемых пользователем; `FALSE` Если кнопка отображает предопределенные изображение, связанное с команду, указанную параметром `uiID`.  
  
### <a name="remarks"></a>Примечания  
 Если `uiID` является допустимым ИД команды, кнопка выполняет эту команду, при щелчке по нему. Если `hMenu` является дескриптором допустимым меню кнопки предоставляет раскрывающееся меню, когда он отображается в меню находится в панели инструментов или подменю. Если оба `uiID` и `hMenu` являются допустимыми, кнопка будет Разворачивающаяся кнопка с часть, которая будет выполнять команды, когда пользователь щелкает и часть со стрелкой вниз, будет раскрывающегося меню при щелчке на нем. Однако если `hMenu` допустим, пользователь не сможет нажмите кнопку, чтобы выполнить команду при вставке в меню кнопки.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCToolBarMenuButton` класса. Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad №&9;](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_2.cpp)]  
  
##  <a name="a-namecomparewitha--cmfctoolbarmenubuttoncomparewith"></a><a name="comparewith"></a>CMFCToolBarMenuButton::CompareWith  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `other`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecopyfroma--cmfctoolbarmenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarMenuButton::CopyFrom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatefrommenua--cmfctoolbarmenubuttoncreatefrommenu"></a><a name="createfrommenu"></a>CMFCToolBarMenuButton::CreateFromMenu  
 Инициализирует меню панели инструментов из дескриптора меню Windows.  
  
```  
virtual void CreateFromMenu(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор меню.  
  
### <a name="remarks"></a>Примечания  
 Кнопки панели инструментов меню можно открыть вложенное меню раскрывающегося списка.  
  
 Платформа вызывает этот метод для инициализации команды в подменю из меню.  
  
##  <a name="a-namecreatemenua--cmfctoolbarmenubuttoncreatemenu"></a><a name="createmenu"></a>CMFCToolBarMenuButton::CreateMenu  
 Создает меню, которое состоит из команд в меню панели инструментов. Возвращает дескриптор меню.  
  
```  
virtual HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор типа для меню, если успеха. `NULL`Если список команд, связанных с кнопкой панели инструментов меню пуст.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, чтобы настроить способ создания меню.  
  
##  <a name="a-namecreatepopupmenua--cmfctoolbarmenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCToolBarMenuButton::CreatePopupMenu  
 Создает `CMFCPopupMenu` объект для отображения меню панели инструментов.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMFCPopupMenu` объекта, который отображает раскрывающееся меню, связанное с кнопкой панели инструментов меню.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для подготовки отображения раскрывающееся меню, связанное с кнопкой.  
  
 Реализация по умолчанию просто создает и возвращает новый `CMFCPopupMenu` объекта. Переопределите этот метод, если вы хотите использовать производный тип [CMFCPopupMenu класса](cmfcpopupmenu-class.md) или для выполнения дополнительной инициализации.  
  
##  <a name="a-namedrawdocumenticona--cmfctoolbarmenubuttondrawdocumenticon"></a><a name="drawdocumenticon"></a>CMFCToolBarMenuButton::DrawDocumentIcon  
 Отображает значок документа на кнопке меню.  
  
```  
void DrawDocumentIcon(
    CDC* pDC,  
    const CRect& rectImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectImage`  
 Координаты ограничивающего прямоугольника изображения.  
  
 [in] `hIcon`  
 Дескриптор для значка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует значок документа и отображает его на кнопке меню, по центру в области, указанной `rectImage`.  
  
##  <a name="a-nameenablequickcustomizea--cmfctoolbarmenubuttonenablequickcustomize"></a><a name="enablequickcustomize"></a>CMFCToolBarMenuButton::EnableQuickCustomize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableQuickCustomize();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehasbuttona--cmfctoolbarmenubuttonhasbutton"></a><a name="hasbutton"></a>CMFCToolBarMenuButton::HasButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehavehotbordera--cmfctoolbarmenubuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarMenuButton::HaveHotBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisbordera--cmfctoolbarmenubuttonisborder"></a><a name="isborder"></a>CMFCToolBarMenuButton::IsBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisclickedonmenua--cmfctoolbarmenubuttonisclickedonmenu"></a><a name="isclickedonmenu"></a>CMFCToolBarMenuButton::IsClickedOnMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsClickedOnMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisquickmodea--cmfctoolbarmenubuttonisquickmode"></a><a name="isquickmode"></a>CMFCToolBarMenuButton::IsQuickMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsQuickMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcommandsa--cmfctoolbarmenubuttongetcommands"></a><a name="getcommands"></a>CMFCToolBarMenuButton::GetCommands  
 Предоставляет доступ только для чтения список команд в меню панели инструментов.  
  
```  
const CObList& GetCommands() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константную ссылку [класс CObList](../../mfc/reference/coblist-class.md) объект, который содержит коллекцию [CMFCToolBarButton класс](../../mfc/reference/cmfctoolbarbutton-class.md) объектов.  
  
### <a name="remarks"></a>Примечания  
 Кнопки панели инструментов меню можно открыть вложенное меню. Можно указать список команд в подменю в конструкторе или в [CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu) как дескриптор меню ( `HMENU`). Меню преобразуется в список объектов, которые являются производными от [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и хранятся во внутренней `CObList` объекта. Чтобы открыть этот список путем вызова данного метода.  
  
##  <a name="a-namegetimagerecta--cmfctoolbarmenubuttongetimagerect"></a><a name="getimagerect"></a>CMFCToolBarMenuButton::GetImageRect  
 Возвращает ограничивающий прямоугольник для изображения на кнопке.  
  
```  
void GetImageRect(CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectImage`  
 Ссылку на `CRect` объекта, получающая координаты ограничивающего прямоугольника изображения.  
  
##  <a name="a-namegetpaletterowsa--cmfctoolbarmenubuttongetpaletterows"></a><a name="getpaletterows"></a>CMFCToolBarMenuButton::GetPaletteRows  
 Возвращает количество строк в раскрывающемся меню, когда меню в режиме палитры.  
  
```  
int GetPaletteRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число строк в палитре.  
  
### <a name="remarks"></a>Примечания  
 Когда кнопки меню устанавливается режим палитру, появятся элементы меню в нескольких столбцах с ограниченным числом строк. Вызовите этот метод, чтобы получить количество строк. Можно включить или отключить режим палитры и указать число строк с помощью [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="a-namegetpopupmenua--cmfctoolbarmenubuttongetpopupmenu"></a><a name="getpopupmenu"></a>CMFCToolBarMenuButton::GetPopupMenu  
 Возвращает указатель на [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) , представляющий раскрывающееся меню кнопки.  
  
```  
CMFCPopupMenu* GetPopupMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) объект, который был создан при платформа нарисованную подменю кнопки меню панели инструментов; `NULL` Если меню не отображается.  
  
### <a name="remarks"></a>Примечания  
 Если кнопки панели инструментов меню отображает раскрывающееся меню, кнопки создает [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) объект для представления меню. Вызовите этот метод, чтобы получить указатель на `CMFCPopupMenu` объект. Не следует хранить возвращаемого указателя, поскольку он является временным и становится недействительным при закрытии раскрывающегося меню.  
  
##  <a name="a-nameisdroppeddowna--cmfctoolbarmenubuttonisdroppeddown"></a><a name="isdroppeddown"></a>CMFCToolBarMenuButton::IsDroppedDown  
 Указывает, отображается ли в данный момент во всплывающем меню.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в меню кнопки панели инструментов отображается его подменю; в противном случае `FALSE`.  
  
##  <a name="a-nameisemptymenualloweda--cmfctoolbarmenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCToolBarMenuButton::IsEmptyMenuAllowed  
 Указывает, отображаются ли элементы меню пустой подменю.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа открывается подменю из меню выбранного элемента, даже в том случае, если подменю является пустой; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь пытается открыть подменю из меню выбранного элемента. Если подменю является пустым и `IsEmptyMenuAllowed` возвращает `FALSE`, не будут открываться подменю.  
  
 Реализация по умолчанию возвращает значение `FALSE`. Переопределите этот метод, чтобы изменить это поведение.  
  
##  <a name="a-nameisexclusivea--cmfctoolbarmenubuttonisexclusive"></a><a name="isexclusive"></a>CMFCToolBarMenuButton::IsExclusive  
 Указывает, является ли кнопки в монопольном режиме.  
  
```  
virtual BOOL IsExclusive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка работает в монопольном режиме; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При нажатии открывается контекстное меню для кнопки и затем перемещает указатель мыши на другую кнопку панели инструментов или меню, всплывающее меню закрывается, если кнопка не в монопольном режиме.  
  
 Реализация по умолчанию всегда возвращает `FALSE`. Переопределите этот метод в производном классе, если требуется включить в монопольном режиме.  
  
##  <a name="a-nameismenupalettemodea--cmfctoolbarmenubuttonismenupalettemode"></a><a name="ismenupalettemode"></a>CMFCToolBarMenuButton::IsMenuPaletteMode  
 Определяет, является ли раскрывающееся меню в режиме палитры.  
  
```  
BOOL IsMenuPaletteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включен режим палитры, в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда кнопки меню устанавливается режим палитру, элементы меню появляются в нескольких столбцах с ограниченным числом строк. Вызовите этот метод, чтобы получить количество строк. Можно включить или отключить режим палитры путем вызова [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="a-nameistearoffmenua--cmfctoolbarmenubuttonistearoffmenu"></a><a name="istearoffmenu"></a>CMFCToolBarMenuButton::IsTearOffMenu  
 Указывает, имеет ли раскрывающееся меню панели перемещаемые.  
  
```  
virtual BOOL IsTearOffMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки панели инструментов меню имеет панель перемещаемые; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для включения функций перемещаемые и задать перемещаемое штрих-код, вызовите [CMFCToolBarMenuButton::SetTearOff](#settearoff).  
  
##  <a name="a-namembalwayscallownerdrawa--cmfctoolbarmenubuttonmbalwayscallownerdraw"></a><a name="m_balwayscallownerdraw"></a>CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw  
 Указывает, является ли платформа всегда вызывает [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) при рисовании кнопки.  
  
```  
static BOOL m_bAlwaysCallOwnerDraw;  
```  
  
### <a name="remarks"></a>Примечания  
 Если значение переменной-члена `TRUE`, кнопки всегда вызывает [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) метод для отображения изображения на кнопке. Когда `m_bAlwaysCallOwnerDraw` — `FALSE`, самой кнопке Рисует изображение, если изображение является стандартным. В противном случае, он вызывает `OnDrawMenuImage`.  
  
##  <a name="a-nameonaftercreatepopupmenua--cmfctoolbarmenubuttononaftercreatepopupmenu"></a><a name="onaftercreatepopupmenu"></a>CMFCToolBarMenuButton::OnAfterCreatePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterCreatePopupMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonbeforedraga--cmfctoolbarmenubuttononbeforedrag"></a><a name="onbeforedrag"></a>CMFCToolBarMenuButton::OnBeforeDrag  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoncalculatesizea--cmfctoolbarmenubuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarMenuButton::OnCalculateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `sizeDefault`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoncancelmodea--cmfctoolbarmenubuttononcancelmode"></a><a name="oncancelmode"></a>CMFCToolBarMenuButton::OnCancelMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbarmenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarMenuButton::OnChangeParentWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonclicka--cmfctoolbarmenubuttononclick"></a><a name="onclick"></a>CMFCToolBarMenuButton::OnClick  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 [in] `bDelay`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonclickmenuitema--cmfctoolbarmenubuttononclickmenuitem"></a><a name="onclickmenuitem"></a>CMFCToolBarMenuButton::OnClickMenuItem  
 Вызывается платформой, когда пользователь выбирает элемент в раскрывающемся меню.  
  
```  
virtual BOOL OnClickMenuItem();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `FALSE`Если платформа должны продолжать обработку элементов; меню по умолчанию в противном случае `TRUE`. Реализация по умолчанию всегда возвращает `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает элемент меню, платформа выполняет команду, которая связана с этим элементом.  
  
 Чтобы настроить обработки элемента меню, переопределите `OnClickMenuItem` в классе, производном от `CMFCToolBarMenuButton` класса. Необходимо также переопределить [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) и замените кнопок меню, которые требуют специальной обработки экземплярами производного класса.  
  
##  <a name="a-nameoncontexthelpa--cmfctoolbarmenubuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFCToolBarMenuButton::OnContextHelp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawa--cmfctoolbarmenubuttonondraw"></a><a name="ondraw"></a>CMFCToolBarMenuButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `pImages`  
 [in] `bHorz`  
 [in] `bCustomizeMode`  
 [in] `bHighlight`  
 [in] `bDrawBorder`  
 [in] `bGrayDisabledButtons`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawoncustomizelista--cmfctoolbarmenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarMenuButton::OnDrawOnCustomizeList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `bSelected`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameopenpopupmenua--cmfctoolbarmenubuttonopenpopupmenu"></a><a name="openpopupmenu"></a>CMFCToolBarMenuButton::OpenPopupMenu  
 Вызывается платформой, когда пользователь открывает раскрывающемся меню кнопки панели инструментов.  
  
```  
virtual BOOL OpenPopupMenu(CWnd* pWnd=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Определяет окно, которое получает раскрывающееся меню команд. Он может быть `NULL` только в том случае, если кнопки панели инструментов меню родительского окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Когда [класса CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) объект был создан и открыт успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой, когда пользователь открывает раскрывающемся меню с панели инструментов меню.  
  
##  <a name="a-nameresetimagetodefaulta--cmfctoolbarmenubuttonresetimagetodefault"></a><a name="resetimagetodefault"></a>CMFCToolBarMenuButton::ResetImageToDefault  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesavebarstatea--cmfctoolbarmenubuttonsavebarstate"></a><a name="savebarstate"></a>CMFCToolBarMenuButton::SaveBarState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при создании как результат операции и перетащите кнопку панели инструментов. Этот метод вызывает метод [CMFCPopupMenu::SaveState](../../mfc/reference/cmfcpopupmenu-class.md#savestate) метод верхнего уровня всплывающего меню, кнопки родительского из контекстного меню для воссоздания его меню.  
  
##  <a name="a-nameserializea--cmfctoolbarmenubuttonserialize"></a><a name="serialize"></a>CMFCToolBarMenuButton::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetaccdataa--cmfctoolbarmenubuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarMenuButton::SetACCData  
 Задает данные специальных возможностей для элемента ленты.  
  
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
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод задает данные специальных возможностей для элемента ленты и всегда возвращает значение `TRUE`. Переопределите этот метод, чтобы задать данные специальных возможностей и возвращать значение, указывающее на успешное или неуспешное выполнение.  
  
##  <a name="a-namesetmenuonlya--cmfctoolbarmenubuttonsetmenuonly"></a><a name="setmenuonly"></a>CMFCToolBarMenuButton::SetMenuOnly  
 Указывает, выводится ли кнопки как кнопки меню или разворачивающуюся кнопку, если она имеет идентификатор допустимые команды и подменю.  
  
```  
void SetMenuOnly(BOOL bMenuOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMenuOnly`  
 `TRUE`для отображения кнопки меню эту кнопку, когда она имеет идентификатор допустимые команды и подменю, `FALSE` для отображения этой кнопки Разворачивающаяся кнопка при наличии идентификатор допустимые команды и подменю.  
  
### <a name="remarks"></a>Примечания  
 Как правило Если кнопки панели инструментов меню есть вложенное меню и идентификатор команды, меню вероятно разворачивающуюся кнопку с основной кнопки и прикрепленное кнопка со стрелкой вниз. Если вызвать этот метод и `bMenuOnly` — `TRUE`, кнопки вместо воспринимается как единое меню кнопку со стрелкой вниз на кнопке. При щелчке стрелки в режиме, открывается подменю и при щелчке части не стрелку кнопки в режиме платформа выполняет команду.  
  
##  <a name="a-namesetmenupalettemodea--cmfctoolbarmenubuttonsetmenupalettemode"></a><a name="setmenupalettemode"></a>CMFCToolBarMenuButton::SetMenuPaletteMode  
 Указывает, является ли раскрывающееся меню в режиме палитры.  
  
```  
void SetMenuPaletteMode(
    BOOL bMenuPaletteMode=TRUE,  
    int nPaletteRows=1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMenuPaletteMode`  
 Указывает, является ли раскрывающееся меню в режиме палитры.  
  
 [in] `nPaletteRows`  
 Число строк в палитре.  
  
### <a name="remarks"></a>Примечания  
 В режиме палитры все пункты меню отображаются в виде нескольких столбцов палитры. Укажите число строк с помощью `nPaletteRows`.  
  
##  <a name="a-namesetmessagewnda--cmfctoolbarmenubuttonsetmessagewnd"></a><a name="setmessagewnd"></a>CMFCToolBarMenuButton::SetMessageWnd  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMessageWnd(CWnd* pWndMessage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndMessage`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetradioa--cmfctoolbarmenubuttonsetradio"></a><a name="setradio"></a>CMFCToolBarMenuButton::SetRadio  
 Задает кнопки панели инструментов меню, чтобы отобразить значок стиля кнопки переключателя при его выборе.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>Примечания  
 При рисовании кнопки меню, когда он извлечен, он вызывает [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck) для рисования значок галочки. По умолчанию `OnDrawMenuCheck` запросов, что текущий диспетчер визуального представления рисует флажок стиль метки на кнопке меню. После вызова этого метода текущий диспетчер визуального представления вместо рисует флажок стиль кнопки переключателя на кнопке меню. Это изменение нельзя отменить.  
  
 При вызове этого метода и кнопки меню отображается, она будет обновлена.  
  
##  <a name="a-namesettearoffa--cmfctoolbarmenubuttonsettearoff"></a><a name="settearoff"></a>CMFCToolBarMenuButton::SetTearOff  
 Указывает идентификатор панели перемещаемые раскрывающееся меню.  
  
```  
virtual void SetTearOff(UINT uiBarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiBarID`  
 Указывает новый перемещаемое строке идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для указания идентификатора панели перемещаемые, который создается при перетаскивании кнопки меню из строки меню. Если `uiBarID` параметр равен 0, пользователь не может создать кнопки меню.  
  
 Вызов [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) для включения функции перемещаемое меню в приложении.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)
