---
title: "Класс CMFCToolBarMenuButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CMFCToolBarMenuButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CompareWith
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CopyFrom
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateFromMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreateMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::CreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::EnableQuickCustomize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetCommands
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetImageRect
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPaletteRows
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::GetPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HasButton
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::HaveHotBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsBorder
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsClickedOnMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsDroppedDown
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsEmptyMenuAllowed
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsExclusive
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsQuickMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::IsTearOffMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnAfterCreatePopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnBeforeDrag
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCalculateSize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnCancelMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnChangeParentWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClick
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnClickMenuItem
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnContextHelp
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDraw
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OnDrawOnCustomizeList
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::OpenPopupMenu
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::ResetImageToDefault
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SaveBarState
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::Serialize
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetACCData
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuOnly
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMenuPaletteMode
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetMessageWnd
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetRadio
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::SetTearOff
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::DrawDocumentIcon
- AFXTOOLBARMENUBUTTON/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarMenuButton [MFC], CMFCToolBarMenuButton
- CMFCToolBarMenuButton [MFC], CompareWith
- CMFCToolBarMenuButton [MFC], CopyFrom
- CMFCToolBarMenuButton [MFC], CreateFromMenu
- CMFCToolBarMenuButton [MFC], CreateMenu
- CMFCToolBarMenuButton [MFC], CreatePopupMenu
- CMFCToolBarMenuButton [MFC], EnableQuickCustomize
- CMFCToolBarMenuButton [MFC], GetCommands
- CMFCToolBarMenuButton [MFC], GetImageRect
- CMFCToolBarMenuButton [MFC], GetPaletteRows
- CMFCToolBarMenuButton [MFC], GetPopupMenu
- CMFCToolBarMenuButton [MFC], HasButton
- CMFCToolBarMenuButton [MFC], HaveHotBorder
- CMFCToolBarMenuButton [MFC], IsBorder
- CMFCToolBarMenuButton [MFC], IsClickedOnMenu
- CMFCToolBarMenuButton [MFC], IsDroppedDown
- CMFCToolBarMenuButton [MFC], IsEmptyMenuAllowed
- CMFCToolBarMenuButton [MFC], IsExclusive
- CMFCToolBarMenuButton [MFC], IsMenuPaletteMode
- CMFCToolBarMenuButton [MFC], IsQuickMode
- CMFCToolBarMenuButton [MFC], IsTearOffMenu
- CMFCToolBarMenuButton [MFC], OnAfterCreatePopupMenu
- CMFCToolBarMenuButton [MFC], OnBeforeDrag
- CMFCToolBarMenuButton [MFC], OnCalculateSize
- CMFCToolBarMenuButton [MFC], OnCancelMode
- CMFCToolBarMenuButton [MFC], OnChangeParentWnd
- CMFCToolBarMenuButton [MFC], OnClick
- CMFCToolBarMenuButton [MFC], OnClickMenuItem
- CMFCToolBarMenuButton [MFC], OnContextHelp
- CMFCToolBarMenuButton [MFC], OnDraw
- CMFCToolBarMenuButton [MFC], OnDrawOnCustomizeList
- CMFCToolBarMenuButton [MFC], OpenPopupMenu
- CMFCToolBarMenuButton [MFC], ResetImageToDefault
- CMFCToolBarMenuButton [MFC], SaveBarState
- CMFCToolBarMenuButton [MFC], Serialize
- CMFCToolBarMenuButton [MFC], SetACCData
- CMFCToolBarMenuButton [MFC], SetMenuOnly
- CMFCToolBarMenuButton [MFC], SetMenuPaletteMode
- CMFCToolBarMenuButton [MFC], SetMessageWnd
- CMFCToolBarMenuButton [MFC], SetRadio
- CMFCToolBarMenuButton [MFC], SetTearOff
- CMFCToolBarMenuButton [MFC], DrawDocumentIcon
- CMFCToolBarMenuButton [MFC], m_bAlwaysCallOwnerDraw
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6c752d1b9570ce11e232020393cc6d7982baa80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarmenubutton-class"></a>Класс CMFCToolBarMenuButton
Кнопка панели инструментов, содержащая всплывающее меню.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](#cmfctoolbarmenubutton)|Создает объект `CMFCToolBarMenuButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::CompareWith](#comparewith)|Сравнивает данный экземпляр с использованием указанного `CMFCToolBarButton` объекта. (Переопределяет [CMFCToolBarButton::CompareWith](../../mfc/reference/cmfctoolbarbutton-class.md#comparewith).)|  
|[CMFCToolBarMenuButton::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|[CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu)|Инициализирует меню панели инструментов из дескриптор меню Windows.|  
|[CMFCToolBarMenuButton::CreateMenu](#createmenu)|Создает меню Windows, состоящая из команд в меню панели инструментов. Возвращает дескриптор меню Windows.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](#createpopupmenu)|Создает объект всплывающего меню ( [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md)) для отображения меню панели инструментов.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](#enablequickcustomize)||  
|[CMFCToolBarMenuButton::GetCommands](#getcommands)|Предоставляет доступ только для чтения список команд в меню панели инструментов.|  
|[CMFCToolBarMenuButton::GetImageRect](#getimagerect)|Возвращает ограничивающий прямоугольник для изображения на кнопке.|  
|[CMFCToolBarMenuButton::GetPaletteRows](#getpaletterows)|Возвращает количество строк в контекстном меню, когда меню в режиме палитры.|  
|[CMFCToolBarMenuButton::GetPopupMenu](#getpopupmenu)|Возвращает указатель на объект всплывающего меню, связанное с кнопкой.|  
|[CMFCToolBarMenuButton::HasButton](#hasbutton)||  
|[CMFCToolBarMenuButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarMenuButton::IsBorder](#isborder)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](#isclickedonmenu)||  
|[CMFCToolBarMenuButton::IsDroppedDown](#isdroppeddown)|Определяет отображение всплывающего меню.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Вызывается платформой для определения, может ли пользователь открыть подменю из выбранного пункта меню.|  
|[CMFCToolBarMenuButton::IsExclusive](#isexclusive)|Определяет, является ли кнопки в монопольном режиме, то есть ли во всплывающем меню остается открытым, даже в том случае, когда пользователь перемещает указатель на другой панели инструментов или кнопки.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](#ismenupalettemode)|Определяет, является ли всплывающего меню в режиме палитры.|  
|[CMFCToolBarMenuButton::IsQuickMode](#isquickmode)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](#istearoffmenu)|Определяет, имеет ли всплывающего меню перемещаемой панелью.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](#onaftercreatepopupmenu)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](#onbeforedrag)|Указывает, можно ли перетащить кнопки. (Переопределяет [CMFCToolBarButton::OnBeforeDrag](../../mfc/reference/cmfctoolbarbutton-class.md#onbeforedrag).)|  
|[CMFCToolBarMenuButton::OnCalculateSize](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarMenuButton::OnCancelMode](#oncancelmode)|Вызывается платформой для обработки [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) сообщения. (Переопределяет [CMFCToolBarButton::OnCancelMode](../../mfc/reference/cmfctoolbarbutton-class.md#oncancelmode).)|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarMenuButton::OnClick](#onclick)|Вызывается платформой, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarMenuButton::OnClickMenuItem](#onclickmenuitem)|Вызывается платформой, когда пользователь выбирает элемент контекстного меню.|  
|[CMFCToolBarMenuButton::OnContextHelp](#oncontexthelp)|Вызывается платформой при обработке родительского инструментов `WM_HELPHITTEST` сообщения. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCToolBarMenuButton::OnDraw](#ondraw)|Вызывается платформой для отрисовки кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой для отрисовки кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarMenuButton::OpenPopupMenu](#openpopupmenu)|Вызывается платформой, когда пользователь открывает во всплывающем меню.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](#resetimagetodefault)|Задает значение по умолчанию изображение, связанное с кнопкой. (Переопределяет [CMFCToolBarButton::ResetImageToDefault](../../mfc/reference/cmfctoolbarbutton-class.md#resetimagetodefault).)|  
|[CMFCToolBarMenuButton::SaveBarState](#savebarstate)|Сохраняет состояние кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SaveBarState](../../mfc/reference/cmfctoolbarbutton-class.md#savebarstate).)|  
|[CMFCToolBarMenuButton::Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCToolBarMenuButton::SetACCData](#setaccdata)|Заполняет предоставленный `CAccessibilityData` объект с данные специальных возможностей с помощью кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|[CMFCToolBarMenuButton::SetMenuOnly](#setmenuonly)|Указывает, можно ли добавить кнопку на панель инструментов.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode)|Указывает, является ли всплывающего меню в режиме палитры.|  
|[CMFCToolBarMenuButton::SetMessageWnd](#setmessagewnd)||  
|[CMFCToolBarMenuButton::SetRadio](#setradio)|Принудительно кнопку меню панели инструментов, чтобы отобразить значок, обозначающий, что он выбран.|  
|[CMFCToolBarMenuButton::SetTearOff](#settearoff)|Задает перемещаемое панель идентификатор для контекстного меню.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](#drawdocumenticon)|Рисует значок кнопки меню.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw](#m_balwayscallownerdraw)|Если `TRUE`, всегда вызывается платформой [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) при рисовании кнопки.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCToolBarMenuButton` может отображаться как меню, элемент меню есть вложенное меню, кнопки, которая выполняет команду или отображает меню или кнопки, которая отображает только меню. Определите поведение и внешний вид кнопки меню путем указания параметров, таких как изображения, текст, дескриптор меню и команды идентификатор, связанный с кнопкой в конструкторе `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Пользовательский класс, производный от `CMFCToolbarMenuButton` класс должен использовать [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) макрос. [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) макрос приводит к ошибке при закрытии приложения.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способы настройки `CMFCToolBarMenuButton` объекта. Код показывает, как указать, что раскрывающееся меню в режиме палитры и укажите идентификатор для перемещаемой панелью, которая создается, когда пользователь перетаскивает кнопки меню из строки меню. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarmenubutton.h  
  
##  <a name="cmfctoolbarmenubutton"></a>CMFCToolBarMenuButton::CMFCToolBarMenuButton  
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
 Существующий `CMFCToolBarMenuButton` объект копируется это `CMFCToolBarMenuButton` объекта.  
  
 [in] `uiID`  
 Идентификатор команды для выполнения при нажатии кнопки. или ( `UINT`) -1 для кнопки меню, который напрямую не выполняет команду.  
  
 [in] `hMenu`  
 Дескриптор для меню; или `NULL` Если нет кнопки меню.  
  
 [in] `iImage`  
 Индекс изображения для кнопки. или -1, если эта кнопка не имеет значка или использует значок для команды, заданной параметром `uiID`. Индекс является одинаковым для каждого `CMFCToolBarImages` объекта в приложении.  
  
 [in] `lpszText`  
 Текст кнопки панели инструментов меню.  
  
 [in] `bUserButton`  
 `TRUE`Если кнопка отображает изображение, определяемых пользователем; `FALSE` Если стандартным образом, связанного с командой, заданные с помощью кнопки отобразить `uiID`.  
  
### <a name="remarks"></a>Примечания  
 Если `uiID` является допустимым ИД команды, кнопка выполняет команды, когда пользователь нажимает кнопку. Если `hMenu` является дескриптором допустимым меню, кнопки предоставляет раскрывающееся меню, когда он отображается в меню находится в панели инструментов или подменю. Если оба `uiID` и `hMenu` являются допустимыми, кнопка будет Разворачивающаяся кнопка с часть, которая будет выполнять команды, когда пользователь щелкает и часть с стрелка вниз, которая будет раскрывающегося меню при щелчке на нем. Однако если `hMenu` является допустимым, и пользователь не сможет нажмите кнопку, чтобы выполнить команду при вставке в меню кнопки.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCToolBarMenuButton` класса. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#9](../../mfc/reference/codesnippet/cpp/cmfctoolbarmenubutton-class_2.cpp)]  
  
##  <a name="comparewith"></a>CMFCToolBarMenuButton::CompareWith  

  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `other`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="copyfrom"></a>CMFCToolBarMenuButton::CopyFrom  

  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="createfrommenu"></a>CMFCToolBarMenuButton::CreateFromMenu  
 Инициализирует меню панели инструментов из дескриптор меню Windows.  
  
```  
virtual void CreateFromMenu(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор для меню.  
  
### <a name="remarks"></a>Примечания  
 Кнопки панели инструментов меню можно отобразить подменю раскрывающегося списка.  
  
 Платформа вызывает этот метод для инициализации команды в подменю из меню.  
  
##  <a name="createmenu"></a>CMFCToolBarMenuButton::CreateMenu  
 Создание меню, которое состоит из команд в меню панели инструментов. Возвращает дескриптор для меню.  
  
```  
virtual HMENU CreateMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект дескриптор меню, если успех. `NULL`Если список команд, связанных с кнопкой панели инструментов меню является пустым.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, чтобы настроить способ создания меню.  
  
##  <a name="createpopupmenu"></a>CMFCToolBarMenuButton::CreatePopupMenu  
 Создает `CMFCPopupMenu` объекта для отображения меню панели инструментов.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMFCPopupMenu` объекта, который отображает раскрывающееся меню, связанное с кнопкой панели инструментов меню.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для подготовки Отображение раскрывающегося меню, связанное с кнопкой.  
  
 Реализация по умолчанию просто создает и возвращает новый `CMFCPopupMenu` объекта. Переопределите этот метод, если вы хотите использовать производным типом [CMFCPopupMenu класса](cmfcpopupmenu-class.md) или выполнить дополнительную инициализацию.  
  
##  <a name="drawdocumenticon"></a>CMFCToolBarMenuButton::DrawDocumentIcon  
 Рисует кнопку меню значок документа.  
  
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
 Дескриптор значка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод принимает значок документа и отображает его на кнопке меню в области, указанной в центре `rectImage`.  
  
##  <a name="enablequickcustomize"></a>CMFCToolBarMenuButton::EnableQuickCustomize  

  
```  
void EnableQuickCustomize();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasbutton"></a>CMFCToolBarMenuButton::HasButton  

  
```  
virtual BOOL HasButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="havehotborder"></a>CMFCToolBarMenuButton::HaveHotBorder  

  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isborder"></a>CMFCToolBarMenuButton::IsBorder  

  
```  
virtual BOOL IsBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isclickedonmenu"></a>CMFCToolBarMenuButton::IsClickedOnMenu  

  
```  
BOOL IsClickedOnMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isquickmode"></a>CMFCToolBarMenuButton::IsQuickMode  

  
```  
BOOL IsQuickMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcommands"></a>CMFCToolBarMenuButton::GetCommands  
 Предоставляет доступ только для чтения список команд в меню панели инструментов.  
  
```  
const CObList& GetCommands() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константную ссылку [класс CObList](../../mfc/reference/coblist-class.md) объект, который содержит коллекцию [CMFCToolBarButton класс](../../mfc/reference/cmfctoolbarbutton-class.md) объектов.  
  
### <a name="remarks"></a>Примечания  
 Кнопки панели инструментов меню можно открыть вложенное меню. Можно указать список команд в подменю в конструкторе или в [CMFCToolBarMenuButton::CreateFromMenu](#createfrommenu) как дескриптор меню ( `HMENU`). Меню преобразуется в список объектов, которые являются производными от [класса CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) и хранится во внутренней `CObList` объекта. Этот список доступен путем вызова данного метода.  
  
##  <a name="getimagerect"></a>CMFCToolBarMenuButton::GetImageRect  
 Возвращает ограничивающий прямоугольник для изображения на кнопке.  
  
```  
void GetImageRect(CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectImage`  
 Ссылку на `CRect` объекта, получающая координаты ограничивающего прямоугольника изображения.  
  
##  <a name="getpaletterows"></a>CMFCToolBarMenuButton::GetPaletteRows  
 Возвращает количество строк в раскрывающемся меню, когда меню в режиме палитры.  
  
```  
int GetPaletteRows() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество строк в палитре.  
  
### <a name="remarks"></a>Примечания  
 Если кнопки меню устанавливается режим палитру, пункты меню будут показаны в несколько столбцов с ограниченного количества строк. Этот метод вызывается для получения номера строк. Можно включить или отключить режим палитры и укажите количество строк с помощью [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="getpopupmenu"></a>CMFCToolBarMenuButton::GetPopupMenu  
 Возвращает указатель на [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) , представляющий раскрывающееся меню кнопки.  
  
```  
CMFCPopupMenu* GetPopupMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) объекта, который был создан при платформа перетащенной подменю из меню кнопки панели инструментов. `NULL` Если подменю не отображается.  
  
### <a name="remarks"></a>Примечания  
 При отображении раскрывающегося меню кнопки панели инструментов меню кнопки создает [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) объект для представления меню. Этот метод вызывается для получения указателя на `CMFCPopupMenu` объекта. Не следует хранить возвращаемого указателя, так как он является временным и становится недействительным, когда пользователь закрывает раскрывающееся меню.  
  
##  <a name="isdroppeddown"></a>CMFCToolBarMenuButton::IsDroppedDown  
 Указывает, в настоящее время отображение всплывающего меню.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в меню кнопки панели инструментов отображается его подменю; в противном случае `FALSE`.  
  
##  <a name="isemptymenuallowed"></a>CMFCToolBarMenuButton::IsEmptyMenuAllowed  
 Указывает, отображаются ли элементы меню пустой подменю.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа открывается подменю из пункта меню выбранного даже в том случае, если подменю является пустой; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь пытается открыть подменю из пункта меню выбранного. Если подменю является пустым и `IsEmptyMenuAllowed` возвращает `FALSE`, не будут открываться подменю.  
  
 Реализация по умолчанию возвращает значение `FALSE`. Переопределите этот метод для настройки этого поведения.  
  
##  <a name="isexclusive"></a>CMFCToolBarMenuButton::IsExclusive  
 Указывает, является ли кнопка в монопольном режиме.  
  
```  
virtual BOOL IsExclusive() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки, работающий в монопольном режиме; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При открытии всплывающего меню для кнопки и затем перемещает указатель мыши на другую кнопку панели инструментов или меню, закрывает всплывающего меню, если кнопка находится в монопольном режиме.  
  
 Реализация по умолчанию всегда возвращает значение `FALSE`. Переопределите этот метод в производном классе, если вы хотите включить в монопольном режиме.  
  
##  <a name="ismenupalettemode"></a>CMFCToolBarMenuButton::IsMenuPaletteMode  
 Определяет, является ли раскрывающееся меню в режиме палитры.  
  
```  
BOOL IsMenuPaletteMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включен режим палитры, в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если кнопки меню устанавливается режим палитру, пункты меню отображаются в нескольких столбцах с ограниченного количества строк. Этот метод вызывается для получения номера строк. Можно включить или отключить режим палитры путем вызова [CMFCToolBarMenuButton::SetMenuPaletteMode](#setmenupalettemode).  
  
##  <a name="istearoffmenu"></a>CMFCToolBarMenuButton::IsTearOffMenu  
 Указывает, имеет ли раскрывающееся меню с перемещаемой панелью.  
  
```  
virtual BOOL IsTearOffMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопки панели инструментов меню с перемещаемой панелью; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для включения функции перемещения и задания перемещаемое штрих-код, вызовите [CMFCToolBarMenuButton::SetTearOff](#settearoff).  
  
##  <a name="m_balwayscallownerdraw"></a>CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw  
 Указывает, является ли платформа всегда вызывает [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) при рисовании кнопки.  
  
```  
static BOOL m_bAlwaysCallOwnerDraw;  
```  
  
### <a name="remarks"></a>Примечания  
 Если значение этой переменной-члена `TRUE`, кнопки всегда вызывает [CFrameWndEx::OnDrawMenuImage](../../mfc/reference/cframewndex-class.md#ondrawmenuimage) метод для отображения изображения на кнопке. Когда `m_bAlwaysCallOwnerDraw` — `FALSE`, самой кнопки выводит изображение, если изображение является стандартным. В противном случае он вызывает `OnDrawMenuImage`.  
  
##  <a name="onaftercreatepopupmenu"></a>CMFCToolBarMenuButton::OnAfterCreatePopupMenu  

  
```  
virtual void OnAfterCreatePopupMenu();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onbeforedrag"></a>CMFCToolBarMenuButton::OnBeforeDrag  

  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncalculatesize"></a>CMFCToolBarMenuButton::OnCalculateSize  

  
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
  
##  <a name="oncancelmode"></a>CMFCToolBarMenuButton::OnCancelMode  

  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarMenuButton::OnChangeParentWnd  

  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onclick"></a>CMFCToolBarMenuButton::OnClick  

  
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
  
##  <a name="onclickmenuitem"></a>CMFCToolBarMenuButton::OnClickMenuItem  
 Вызывается платформой, когда пользователь выбирает элемент в раскрывающемся меню.  
  
```  
virtual BOOL OnClickMenuItem();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `FALSE`Если платформа должны продолжать обработку элементов; меню по умолчанию в противном случае `TRUE`. Реализация по умолчанию всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь выбирает пункт меню, платформа выполняет команду, которая связана с данным элементом.  
  
 Чтобы настроить обработку элементов меню, переопределите `OnClickMenuItem` в классе, производном от `CMFCToolBarMenuButton` класса. Необходимо также переопределить [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) и замените кнопок меню, которые требуют специальной обработки экземплярами производного класса.  
  
##  <a name="oncontexthelp"></a>CMFCToolBarMenuButton::OnContextHelp  

  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>CMFCToolBarMenuButton::OnDraw  

  
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
  
##  <a name="ondrawoncustomizelist"></a>CMFCToolBarMenuButton::OnDrawOnCustomizeList  

  
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
  
##  <a name="openpopupmenu"></a>CMFCToolBarMenuButton::OpenPopupMenu  
 Вызывается платформой, когда пользователь открывает меню раскрывающегося меню кнопки панели инструментов.  
  
```  
virtual BOOL OpenPopupMenu(CWnd* pWnd=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Задает окно, которое получает раскрывающееся меню команд. Это может быть `NULL` только в том случае, если кнопки панели инструментов меню родительского окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Когда [класса CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) объект был создан и открыт успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой, когда пользователь открывает раскрывающееся меню с панели инструментов меню.  
  
##  <a name="resetimagetodefault"></a>CMFCToolBarMenuButton::ResetImageToDefault  

  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="savebarstate"></a>CMFCToolBarMenuButton::SaveBarState  

  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при создании кнопки панели инструментов в результате выполнения операции перетаскивания и вставки. Этот метод вызывает метод [CMFCPopupMenu::SaveState](../../mfc/reference/cmfcpopupmenu-class.md#savestate) метод верхнего уровня всплывающего меню, кнопки родительского из контекстного меню, чтобы заново создать его меню.  
  
##  <a name="serialize"></a>CMFCToolBarMenuButton::Serialize  

  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setaccdata"></a>CMFCToolBarMenuButton::SetACCData  
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
  
##  <a name="setmenuonly"></a>CMFCToolBarMenuButton::SetMenuOnly  
 Указывает, выводится ли кнопку как кнопку меню или разворачивающуюся кнопку после идентификатор допустимые команды и подменю.  
  
```  
void SetMenuOnly(BOOL bMenuOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMenuOnly`  
 `TRUE`для отображения кнопки меню эту кнопку, когда она имеет идентификатор допустимые команды и подменю `FALSE` для отображения Разворачивающаяся кнопка эту кнопку, когда она имеет идентификатор допустимые команды и подменю.  
  
### <a name="remarks"></a>Примечания  
 Как правило если кнопке панели инструментов меню подменю и идентификатор команды, меню вероятно разворачивающейся кнопки, который содержит основной кнопки и прикрепленное кнопка со стрелкой вниз. Если вызвать этот метод и `bMenuOnly` — `TRUE`, кнопки вместо кажется одного меню кнопки со стрелкой вниз на кнопке. Когда пользователь щелкает стрелку в каждом из режимов, подменю откроется, и когда пользователь щелкает часть не стрелку кнопки в режиме платформа выполняет команду.  
  
##  <a name="setmenupalettemode"></a>CMFCToolBarMenuButton::SetMenuPaletteMode  
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
 В режиме палитры все пункты меню отображаются как палитра по нескольким столбцам. Укажите количество строк с помощью `nPaletteRows`.  
  
##  <a name="setmessagewnd"></a>CMFCToolBarMenuButton::SetMessageWnd  

  
```  
void SetMessageWnd(CWnd* pWndMessage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndMessage`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setradio"></a>CMFCToolBarMenuButton::SetRadio  
 Задает кнопку меню панели инструментов для отображения значок стиль кнопки переключателя при его выборе.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>Примечания  
 При рисовании кнопки меню во проверки он вызывает [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck) для рисования значком. По умолчанию `OnDrawMenuCheck` запросов, что текущий Диспетчер визуальных рисует флажок стиля метки кнопки меню. После вызова этого метода текущий диспетчер визуального представления вместо рисует флажок стиль кнопки переключатель кнопки меню. Это изменение нельзя отменить.  
  
 При вызове этого метода и кнопки меню отображается в настоящий момент, будет обновлена.  
  
##  <a name="settearoff"></a>CMFCToolBarMenuButton::SetTearOff  
 Указывает идентификатор перемещаемой панелью для раскрывающегося меню.  
  
```  
virtual void SetTearOff(UINT uiBarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiBarID`  
 Указывает новый перемещаемое столбец идентификатора.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для указания идентификатора для перемещаемой панелью, которая создается, когда пользователь перетаскивает кнопки меню из строки меню. Если `uiBarID` имеет значение 0, пользователь не может создать кнопки меню.  
  
 Вызовите [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) для включения функции перемещаемое меню в приложении.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)