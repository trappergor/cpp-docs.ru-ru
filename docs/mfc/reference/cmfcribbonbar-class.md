---
title: "Класс CMFCRibbonBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonBar class
ms.assetid: a65d06fa-1a28-4cc0-8971-bc9d7c9198fe
caps.latest.revision: 41
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
ms.openlocfilehash: 48a7fbeb72257776d132785c985221b0e8148d72
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbar-class"></a>Класс CMFCRibbonBar
Класс `CMFCRibbonBar` реализует панель ленты. Аналогичная реализация использовалась в Office 2007.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonBar::CMFCRibbonBar`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonBar::ActivateContextCategory](#activatecontextcategory)|Активирует уже видимую категорию контекста.|  
|[CMFCRibbonBar::AddCategory](#addcategory)|Добавляет на ленту новую категорию.|  
|[CMFCRibbonBar::AddContextCategory](#addcontextcategory)|Добавляет категорию контекста.|  
|[CMFCRibbonBar::AddMainCategory](#addmaincategory)|Добавляет новую основную категорию ленты.|  
|[CMFCRibbonBar::AddPrintPreviewCategory](#addprintpreviewcategory)||  
|[CMFCRibbonBar::AddQATOnlyCategory](#addqatonlycategory)||  
|[CMFCRibbonBar::AddToTabs](#addtotabs)|Добавляет элемент ленты справа от панели ленты.|  
|[CMFCRibbonBar::CreateEx](#createex)|Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCRibbonBar::Create](#create)|Создает элемент управления панели ленты и прикрепляет его к панели ленты.|  
|[CMFCRibbonBar::DeactivateKeyboardFocus](#deactivatekeyboardfocus)||  
|[CMFCRibbonBar::DrawMenuImage](#drawmenuimage)||  
|[CMFCRibbonBar::DWMCompositionChanged](#dwmcompositionchanged)||  
|[CMFCRibbonBar::EnableKeyTips](#enablekeytips)|Включает или отключает всплывающие подсказки для элемента управления ленты.|  
|[CMFCRibbonBar::EnablePrintPreview](#enableprintpreview)|Включить **предварительный** вкладки.|  
|[CMFCRibbonBar::EnableToolTips](#enabletooltips)|Включает или отключает всплывающие подсказки и описания на панели ленты.|  
|[CMFCRibbonBar::FindByData](#findbydata)|Поиск элемента ленты по указанным пользователем данным.|  
|[CMFCRibbonBar::FindByID](#findbyid)|Находит элемент ленты по указанному идентификатору команды.|  
|[CMFCRibbonBar::FindCategoryIndexByData](#findcategoryindexbydata)|Находит индекс категории ленты, содержащей определенные пользователем данные.|  
|[CMFCRibbonBar::ForceRecalcLayout](#forcerecalclayout)||  
|[CMFCRibbonBar::GetActiveCategory](#getactivecategory)|Возвращает указатель на активную категорию.|  
|[CMFCRibbonBar::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка. (Переопределяет [CBasePane::GetCaptionHeight](../../mfc/reference/cbasepane-class.md#getcaptionheight).)|  
|[CMFCRibbonBar::GetCategory](#getcategory)|Возвращает указатель на категорию, расположенную по указанному индексу.|  
|[CMFCRibbonBar::GetCategoryCount](#getcategorycount)|Возвращает число категорий ленты на панели ленты.|  
|[CMFCRibbonBar::GetCategoryHeight](#getcategoryheight)||  
|[CMFCRibbonBar::GetCategoryIndex](#getcategoryindex)|Возвращает индекс категории ленты.|  
|[CMFCRibbonBar::GetContextName](#getcontextname)|Извлекает имя заголовка категории контекста, указанного с помощью идентификатора.|  
|[CMFCRibbonBar::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonBar::GetElementsByID](#getelementsbyid)|Возвращает массив, содержащий указатели на все элементы ленты с указанными идентификаторами.|  
|[CMFCRibbonBar::GetApplicationButton](#getapplicationbutton)|Возвращает указатель на кнопку ленты.|  
|[CMFCRibbonBar::GetFocused](#getfocused)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonBar::GetHideFlags](#gethideflags)||  
|[CMFCRibbonBar::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonBar::GetKeyboardNavigationLevel](#getkeyboardnavigationlevel)||  
|[CMFCRibbonBar::GetKeyboardNavLevelCurrent](#getkeyboardnavlevelcurrent)||  
|[CMFCRibbonBar::GetKeyboardNavLevelParent](#getkeyboardnavlevelparent)||  
|[CMFCRibbonBar::GetMainCategory](#getmaincategory)|Возвращает указатель на выбранную категорию ленты.|  
|[CMFCRibbonBar::GetQATCommandsLocation](#getqatcommandslocation)||  
|[CMFCRibbonBar::GetQATDroppedDown](#getqatdroppeddown)||  
|[CMFCRibbonBar::GetQuickAccessCommands](#getquickaccesscommands)|Заполняет список идентификаторами команд всех элементов, отображающихся на панели быстрого доступа.|  
|[CMFCRibbonBar::GetQuickAccessToolbarLocation](#getquickaccesstoolbarlocation)||  
|[CMFCRibbonBar::GetTabTrancateRatio](#gettabtrancateratio)||  
|[CMFCRibbonBar::GetTooltipFixedWidthLargeImage](#gettooltipfixedwidthlargeimage)||  
|[CMFCRibbonBar::GetTooltipFixedWidthRegular](#gettooltipfixedwidthregular)||  
|[CMFCRibbonBar::GetVisibleCategoryCount](#getvisiblecategorycount)||  
|[CMFCRibbonBar::HideAllContextCategories](#hideallcontextcategories)|Скрывает все видимые и активные категории.|  
|[CMFCRibbonBar::HideKeyTips](#hidekeytips)||  
|[CMFCRibbonBar::HitTest](#hittest)|Находит указатель на элемент ленты, расположенный в указанной точке клиентских координат панели ленты.|  
|[CMFCRibbonBar::IsKeyTipEnabled](#iskeytipenabled)|Определяет, включены ли ключевые подсказки.|  
|[CMFCRibbonBar::IsMainRibbonBar](#ismainribbonbar)||  
|[CMFCRibbonBar::IsPrintPreviewEnabled](#isprintpreviewenabled)|Определяет, является ли **предварительный** вкладка активна.|  
|[CMFCRibbonBar::IsQATEmpty](#isqatempty)||  
|[CMFCRibbonBar::IsQuickAccessToolbarOnTop](#isquickaccesstoolbarontop)|Определяет, находится ли панель быстрого доступа над панелью ленты.|  
|[CMFCRibbonBar::IsReplaceFrameCaption](#isreplaceframecaption)|Определяет, заменяет панель ленты заголовок главного фрейма или добавляется под ним.|  
|[CMFCRibbonBar::IsShowGroupBorder](#isshowgroupborder)||  
|[CMFCRibbonBar::IsToolTipDescrEnabled](#istooltipdescrenabled)|Определяет, включены ли всплывающие описания.|  
|[CMFCRibbonBar::IsToolTipEnabled](#istooltipenabled)|Определяет, включены ли всплывающие подсказки для ленты.|  
|[CMFCRibbonBar::IsTransparentCaption](#istransparentcaption)||  
|[CMFCRibbonBar::IsWindows7Look](#iswindows7look)|Указывает, оформлена ли лента в стиле Windows 7 (небольшая прямоугольная кнопка приложения).|  
|[CMFCRibbonBar::LoadFromResource](#loadfromresource)|Перегружен. Загружает панель ленты из ресурсов приложения.|  
|[CMFCRibbonBar::OnClickButton](#onclickbutton)||  
|[CMFCRibbonBar::OnEditContextMenu](#oneditcontextmenu)||  
|[CMFCRibbonBar::OnRTLChanged](#onrtlchanged)|(Переопределяет `CPane::OnRTLChanged`.)|  
|[CMFCRibbonBar::OnSetAccData](#onsetaccdata)|(Переопределяет [CBasePane::OnSetAccData](../../mfc/reference/cbasepane-class.md#onsetaccdata).)|  
|[CMFCRibbonBar::OnShowRibbonContextMenu](#onshowribboncontextmenu)||  
|[CMFCRibbonBar::OnShowRibbonQATMenu](#onshowribbonqatmenu)||  
|[CMFCRibbonBar::OnSysKeyDown](#onsyskeydown)||  
|[CMFCRibbonBar::OnSysKeyUp](#onsyskeyup)||  
|[CMFCRibbonBar::PopTooltip](#poptooltip)||  
|[CMFCRibbonBar::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `CBasePane::PreTranslateMessage`.)|  
|[CMFCRibbonBar::RecalcLayout](#recalclayout)|(Переопределяет [CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CMFCRibbonBar::RemoveAllCategories](#removeallcategories)|Удаляет все категории с панели ленты.|  
|[CMFCRibbonBar::RemoveAllFromTabs](#removeallfromtabs)|Удаляет все элементы ленты из области вкладки.|  
|[CMFCRibbonBar::RemoveCategory](#removecategory)|Удаляет категорию ленты, расположенную по указанному индексу.|  
|[CMFCRibbonBar::SaveToXMLBuffer](#savetoxmlbuffer)|Сохраняет панель ленты в буфер.|  
|[CMFCRibbonBar::SaveToXMLFile](#savetoxmlfile)|Сохраняет панель ленты в файл XML.|  
|[CMFCRibbonBar::SetActiveCategory](#setactivecategory)|Назначает указанной категории ленты активное состояние.|  
|[CMFCRibbonBar::SetActiveMDIChild](#setactivemdichild)||  
|[CMFCRibbonBar::SetElementKeys](#setelementkeys)|Задает указанные ключевые подсказки для всех элементов ленты, которые имеют указанный идентификатор команды.|  
|[CMFCRibbonBar::SetApplicationButton](#setapplicationbutton)|Помещает на панель ленты кнопку приложения.|  
|[CMFCRibbonBar::SetKeyboardNavigationLevel](#setkeyboardnavigationlevel)||  
|[CMFCRibbonBar::SetMaximizeMode](#setmaximizemode)||  
|[CMFCRibbonBar::SetQuickAccessCommands](#setquickaccesscommands)|Добавляет один или несколько элементов ленты на панель быстрого доступа.|  
|[CMFCRibbonBar::SetQuickAccessDefaultState](#setquickaccessdefaultstate)|Задает состояние панели быстрого доступа по умолчанию.|  
|[CMFCRibbonBar::SetQuickAccessToolbarOnTop](#setquickaccesstoolbarontop)|Помещает панель быстрого доступа над панелью ленты или под ней.|  
|[CMFCRibbonBar::SetTooltipFixedWidth](#settooltipfixedwidth)||  
|[CMFCRibbonBar::SetWindows7Look](#setwindows7look)|Включает или отключает оформление ленты в стиле Windows 7 (небольшая прямоугольная кнопка приложения).|  
|[CMFCRibbonBar::ShowCategory](#showcategory)|Отображает или скрывает указанную категорию ленты.|  
|[CMFCRibbonBar::ShowContextCategories](#showcontextcategories)|Показывает или скрывает категории контекста с указанным идентификатором.|  
|[CMFCRibbonBar::ShowKeyTips](#showkeytips)||  
|[CMFCRibbonBar::ToggleMimimizeState](#togglemimimizestate)|Переключает панель ленты между свернутым и развернутым состояниями.|  
|[CMFCRibbonBar::TranslateChar](#translatechar)||  
  
## <a name="remarks"></a>Примечания  
 Корпорация Майкрософт представила ленту (Office Fluent Ribbon) вместе с выпуском Microsoft Office 2007. Панель ленты — это не просто новый элемент управления. Она представляет собой новый подход к пользовательскому интерфейсу. Лента — это панель с вкладками, которые называются категориями. Каждая категория делится на группы, содержащие различные элементы управления и кнопки команд.  
  
 Элементы, отображающиеся на панели ленты, разворачиваются и сворачиваются, чтобы оптимально задействовать доступное пространство. Например, если в группе ленты становится недостаточно места для отображения всех необходимых элементов, она превращается в кнопку, элементы которой показываются во всплывающем меню. Лента ведет себя как статическая (неперемещаемая) панель элементов управления, которую можно закрепить в верхней части фрейма.  
  
 С помощью класса `CMFCRibbonStatusBar` вы можете реализовать строку состояния, аналогичную используемой в Office 2007. Категория ленты содержит (и отображает) группы [ленте панелей](../../mfc/reference/cmfcribbonpanel-class.md). Каждая панель ленты содержит один или несколько элементов ленты, которые являются производными от [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Сведения о том, как добавить ленту в существующее приложение MFC в разделе [Пошаговое руководство: обновление приложения MFC Scribble](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonbar.h  
  
##  <a name="a-nameactivatecontextcategorya--cmfcribbonbaractivatecontextcategory"></a><a name="activatecontextcategory"></a>CMFCRibbonBar::ActivateContextCategory  
 Активирует уже видимую категорию контекста.  
  
```  
BOOL ActivateContextCategory(UINT uiContextID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiContextID`  
 Идентификатор категории контекста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория контекста с `uiContextID` найден и активации; в противном случае `FALSE`.  
  
##  <a name="a-nameaddcategorya--cmfcribbonbaraddcategory"></a><a name="addcategory"></a>CMFCRibbonBar::AddCategory  
 Создает и инициализирует новую категорию ленты для ленты.  
  
```  
CMFCRibbonCategory* AddCategory(
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage= CSize(16,
    16),  
    CSize sizeLargeImage= CSize(32,
    32),  
    int nInsertAt = -1,  
    CRuntimeClass* pRTI= NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя категории ленты.  
  
 [in] `uiSmallImagesResID`  
 Идентификатор ресурса небольшое изображение списка для категории ленты.  
  
 [in] `uiLargeImagesResID`  
 Идентификатор ресурса список больших изображений для категории ленты.  
  
 [in] `sizeSmallImage`  
 Задает размер изображений небольшого размера для категории ленты.  
  
 [in] `sizeLargeImage`  
 Указывает размер больших изображений для категории ленты.  
  
 [in] `nInsertAt`  
 Отсчитываемый от нуля индекс расположения категории.  
  
 [in] `pRTI`  
 Указатель на [CMFCRibbonCategory класса](../../mfc/reference/cmfcribboncategory-class.md) класс времени выполнения для динамического создания категория ленты во время выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новую категорию ленты, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если `pRTI` параметр не `NULL`, новая категория ленты создается динамически с помощью класса во время выполнения.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddCategory` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#5;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_1.cpp)]  
  
##  <a name="a-nameaddcontextcategorya--cmfcribbonbaraddcontextcategory"></a><a name="addcontextcategory"></a>CMFCRibbonBar::AddContextCategory  
 Создает и инициализирует новых категорий содержимого ленты.  
  
```  
CMFCRibbonCategory* AddContextCategory(
    LPCTSTR lpszName,  
    LPCTSTR lpszContextName,  
    UINT uiContextID,  
    AFX_RibbonCategoryColor clrContext,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32),  
    CRuntimeClass* pRTI = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя категории.  
  
 [in] `lpszContextName`  
 Имя категории заголовка контекста.  
  
 [in] `uiContextID`  
 Идентификатор контекста.  
  
 [in] `clrContext`  
 Цвет заголовка категории контекста.  
  
 [in] `uiSmallImagesResID`  
 Идентификатор ресурса категории контекста небольшое изображение.  
  
 [in] `uiLargeImagesResID`  
 Идентификатор ресурса большое изображение категории контекста.  
  
 [in] `sizeSmallImage`  
 Размер небольшое изображение.  
  
 [in] `sizeLargeImage`  
 Размер большого изображения.  
  
 [in] `pRTI`  
 Указатель на класс среды выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный категории или `NULL` Если `CreateObject` метод `pRTI` не удается создать указанную категорию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для добавления категории контекста. Контекст категорий являются особым типом категории, которой могут быть отображены или скрыты во время выполнения, в зависимости от текущего контекста приложения. Например при выборе объекта, можно отображать специальные вкладки с помощью контекста категории, которые позволяют изменить выбранный объект.  
  
 Цвет категории контекста может принимать одно из следующих значений:  
  
-   AFX_CategoryColor_None  
  
-   AFX_CategoryColor_Red  
  
-   AFX_CategoryColor_Orange  
  
-   AFX_CategoryColor_Yellow  
  
-   AFX_CategoryColor_Green  
  
-   AFX_CategoryColor_Blue  
  
-   AFX_CategoryColor_Indigo  
  
-   AFX_CategoryColor_Violet  
  
##  <a name="a-nameaddmaincategorya--cmfcribbonbaraddmaincategory"></a><a name="addmaincategory"></a>CMFCRibbonBar::AddMainCategory  
 Создает новую категорию основной ленты для ленты.  
  
```  
CMFCRibbonMainPanel* AddMainCategory(
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    UINT uiLargeImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16),  
    CSize sizeLargeImage = CSize(32,
    32));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя категории основных ленты.  
  
 [in] `uiSmallImagesResID`  
 Идентификатор ресурса для небольших изображений.  
  
 [in] `uiLargeImagesResID`  
 Идентификатор ресурса для больших изображений.  
  
 [in] `sizeSmallImage`  
 Размер изображений небольшого размера.  
  
 [in] `sizeLargeImage`  
 Размер больших изображений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новой категории основных ленты, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если основной ленты категория уже существует, она удаляется.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddMainCategory` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#4;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_2.cpp)]  
  
##  <a name="a-nameaddprintpreviewcategorya--cmfcribbonbaraddprintpreviewcategory"></a><a name="addprintpreviewcategory"></a>CMFCRibbonBar::AddPrintPreviewCategory  
 Создает категорию предварительного просмотра на ленте.  
  
```  
CMFCRibbonCategory* AddPrintPreviewCategory();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новую категорию ленты, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает категорией ленты и элементы управления, которые необходимы для предварительного просмотра печати.  
  
##  <a name="a-nameaddqatonlycategorya--cmfcribbonbaraddqatonlycategory"></a><a name="addqatonlycategory"></a>CMFCRibbonBar::AddQATOnlyCategory  
 Создает категорию ленте панели инструментов быстрого доступа.  
  
```  
CMFCRibbonCategory* AddQATOnlyCategory(
    LPCTSTR lpszName,  
    UINT uiSmallImagesResID,  
    CSize sizeSmallImage = CSize(16,
    16));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszName`  
 Имя категории.  
  
 [in] `uiSmallImagesResID`  
 Идентификатор ресурса для списка изображений для категории.  
  
 [in] `sizeSmallImage`  
 Размер изображения для элементов ленты в категории.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новой категории, если метод был выполнен успешно; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Категория ленты инструментов быстрого доступа используется только в диалоговом окне настройки панели инструментов быстрого доступа.  
  
##  <a name="a-nameaddtotabsa--cmfcribbonbaraddtotabs"></a><a name="addtotabs"></a>CMFCRibbonBar::AddToTabs  
 Добавляет элемент ленты в указанной строке вкладки ленты.  
  
```  
void AddToTabs(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель на элемент ленты.  
  
### <a name="remarks"></a>Примечания  
 Элемент ленты располагается перед любой кнопки системы.  
  
##  <a name="a-namecmfcribbonbara--cmfcribbonbarcmfcribbonbar"></a><a name="cmfcribbonbar"></a>CMFCRibbonBar::CMFCRibbonBar  
 Создает и инициализирует [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) объекта.  
  
```  
CMFCRibbonBar(BOOL bReplaceFrameCaption = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bReplaceFrameCaption`  
 `TRUE`ленты заменить заголовок главного окна фрейма; `FALSE` найти ленту в области заголовка фрейма главного окна.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecreatea--cmfcribbonbarcreate"></a><a name="create"></a>CMFCRibbonBar::Create  
 Создает окно для ленты.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_RIBBON_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно для ленты.  
  
 [in] `dwStyle`  
 Сочетание логического стили для нового окна.  
  
 [in] `nID`  
 Идентификатор нового окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно было создано; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#1;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_3.cpp)]  
  
##  <a name="a-namecreateexa--cmfcribbonbarcreateex"></a><a name="createex"></a>CMFCRibbonBar::CreateEx  
 Создает окно для ленты.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_RIBBON_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно для ленты.  
  
 [in] `dwCtrlStyle`  
 Этот параметр не используется.  
  
 [in] `dwStyle`  
 Сочетание логического стили для нового окна.  
  
 [in] `nID`  
 Идентификатор нового окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно было создано; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedeactivatekeyboardfocusa--cmfcribbonbardeactivatekeyboardfocus"></a><a name="deactivatekeyboardfocus"></a>CMFCRibbonBar::DeactivateKeyboardFocus  
 Закрывает все значение свойства keytip элементы управления на ленте.  
  
```  
void DeactivateKeyboardFocus(BOOL bSetFocus = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSetFocus`  
 `TRUE`Чтобы установить фокус родительского окна ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawmenuimagea--cmfcribbonbardrawmenuimage"></a><a name="drawmenuimage"></a>CMFCRibbonBar::DrawMenuImage  
 Рисует изображение для кнопки меню.  
  
```  
BOOL DrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuItem,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для кнопки меню.  
  
 [in] `pMenuItem`  
 Указатель на кнопку панели инструментов меню.  
  
 [in] `rectImage`  
 Отображаемый прямоугольник для кнопки меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если образ был нарисован; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedwmcompositionchangeda--cmfcribbonbardwmcompositionchanged"></a><a name="dwmcompositionchanged"></a>CMFCRibbonBar::DWMCompositionChanged  
 Регулирует отображение ленты при композиции диспетчер окон рабочего стола (DWM) включен или отключен.  
  
```  
virtual void DWMCompositionChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenablekeytipsa--cmfcribbonbarenablekeytips"></a><a name="enablekeytips"></a>CMFCRibbonBar::EnableKeyTips  
 Включает или отключает функцию значение свойства keytip ленты.  
  
```  
void EnableKeyTips(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для включения функции подсказки клавиш; `FALSE` для отключения функции подсказки клавиш.  
  
### <a name="remarks"></a>Примечания  
 При включении этой функции сочетания клавиш отображаются, когда пользователь нажимает кнопку ALT или F10. Когда пользователь нажимает клавишу ALT, сочетания клавиш отображаются с 200 миллисекунд. Эта задержка позволяет сочетания клавиш для выполнения, чтобы при нажатой клавише ALT не влияет на другие сочетания, включающие клавишу ALT.  
  
##  <a name="a-nameenableprintpreviewa--cmfcribbonbarenableprintpreview"></a><a name="enableprintpreview"></a>CMFCRibbonBar::EnablePrintPreview  
 Включает или отключает **предварительный** функции.  
  
```  
void EnablePrintPreview(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить **предварительный** компонентов; `FALSE` отключение **предварительный** функции.  
  
### <a name="remarks"></a>Примечания  
 Если `bEnable` — `FALSE` и категория предварительного существует, он будет удален.  
  
 По умолчанию **предварительный** включена.  
  
##  <a name="a-nameenabletooltipsa--cmfcribbonbarenabletooltips"></a><a name="enabletooltips"></a>CMFCRibbonBar::EnableToolTips  
 Включает или отключает подсказок и описаний необязательно подсказки на ленте.  
  
```  
void EnableToolTips(
    BOOL bEnable = TRUE,  
    BOOL bEnableDescr = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить подсказки на ленте; `FALSE` отключить подсказки на ленте.  
  
 [in] `bEnableDescr`  
 `TRUE`Чтобы включить описания всплывающей подсказки на подсказку; `FALSE` для отключения описания всплывающей подсказки на подсказке.  
  
### <a name="remarks"></a>Примечания  
 `bEnable` Определяет, отображаются ли всплывающие подсказки при наведении указателя мыши на элемент ленты. `bEnableDescr` Параметр определяет, отображается ли дополнительные описательный текст с текстом всплывающей подсказки.  
  
##  <a name="a-namefindbydataa--cmfcribbonbarfindbydata"></a><a name="findbydata"></a>CMFCRibbonBar::FindByData  
 Извлекает указатель на элемент ленты, если он имеет указанные данные и видимость.  
  
```  
CMFCRibbonBaseElement* FindByData(
    DWORD_PTR dwData,  
    BOOL bVisibleOnly = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Данные, связанные с элементом ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`для поиска элементов отображается ленты. `FALSE` для поиска всех элементов ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если он имеет указанные данные и видимость; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Элемент ленты является любой элемент управления, который можно добавить на ленту, такие как кнопки на ленте или категория ленты или ползунок ленты.  
  
##  <a name="a-namefindbyida--cmfcribbonbarfindbyid"></a><a name="findbyid"></a>CMFCRibbonBar::FindByID  
 Извлекает указатель на элемент ленты, значения идентификатора и найдите указанную команду.  
  
```  
CMFCRibbonBaseElement* FindByID(
    UINT uiCmdID,  
    BOOL bVisibleOnly = TRUE,  
    BOOL bExcludeQAT = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды для элемента ленты.  
  
 [in] `bVisibleOnly`  
 `TRUE`для поиска элементов отображается ленты. `FALSE` для поиска всех элементов ленты.  
  
 [in] `bExcludeQAT`  
 `TRUE`Чтобы исключить элементы панели инструментов быстрого доступа из поиска; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, если он имеет указанную команду значения идентификатора и поиска; в противном случае — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Элемент ленты является элементом управления ribbon, который может быть добавлен на ленту, такие как кнопки на ленте или категория ленты или ползунок ленты.  
  
 В целом может быть более одного элемента ленты, который имеет тот же идентификатор команды. Если вы хотите получить ссылки на все элементы ленты, которые используют заданный идентификатор команды, [CMFCRibbonBar::GetElementsByID](#getelementsbyid) метод.  
  
##  <a name="a-namefindcategoryindexbydataa--cmfcribbonbarfindcategoryindexbydata"></a><a name="findcategoryindexbydata"></a>CMFCRibbonBar::FindCategoryIndexByData  
 Извлекает индекс категорией, которая содержит указанные данные.  
  
```  
int FindCategoryIndexByData(DWORD dwData) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwData`  
 Данные, связанные с категорией ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс категория ленты, если метод был выполнен успешно; в противном случае — значение -1.  
  
##  <a name="a-nameforcerecalclayouta--cmfcribbonbarforcerecalclayout"></a><a name="forcerecalclayout"></a>CMFCRibbonBar::ForceRecalcLayout  
 Изменение макета все элементы ленты и родительского окна и перерисовывает всего окна.  
  
```  
void ForceRecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetactivecategorya--cmfcribbonbargetactivecategory"></a><a name="getactivecategory"></a>CMFCRibbonBar::GetActiveCategory  
 Извлекает указатель на категории active ленты.  
  
```  
CMFCRibbonCategory* GetActiveCategory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на категории active ленты; или `NULL` Если категории не активен.  
  
### <a name="remarks"></a>Примечания  
 Категория — активным, если оно имеет фокус. По умолчанию активной категории является первой категории в левой части панели ленты.  
  
 Главной категорией отображается при нажатии пользователем кнопки приложения и не может быть активной категории.  
  
##  <a name="a-namegetapplicationbuttona--cmfcribbonbargetapplicationbutton"></a><a name="getapplicationbutton"></a>CMFCRibbonBar::GetApplicationButton  
 Извлекает указатель на кнопку приложения.  
  
```  
CMFCRibbonApplicationButton* GetApplicationButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на кнопку приложения; или `NULL` Если кнопка не было задано.  
  
##  <a name="a-namegetcaptionheighta--cmfcribbonbargetcaptionheight"></a><a name="getcaptionheight"></a>CMFCRibbonBar::GetCaptionHeight  
 Возвращает высоту области заголовка ленты.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях области заголовка ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetcategorya--cmfcribbonbargetcategory"></a><a name="getcategory"></a>CMFCRibbonBar::GetCategory  
 Извлекает указатель на категория ленты по указанному индексу.  
  
```  
CMFCRibbonCategory* GetCategory(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс в нее категорию в списке категорий ленты, содержащаяся в ленте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на категория ленты по указанному индексу; в противном случае — `NULL` Если `nIndex` выходят за пределы диапазона.  
  
##  <a name="a-namegetcategorycounta--cmfcribbonbargetcategorycount"></a><a name="getcategorycount"></a>CMFCRibbonBar::GetCategoryCount  
 Получает номер категории ленты на панели ленты.  
  
```  
int GetCategoryCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число категорий ленты на панели ленты.  
  
##  <a name="a-namegetcategoryheighta--cmfcribbonbargetcategoryheight"></a><a name="getcategoryheight"></a>CMFCRibbonBar::GetCategoryHeight  
 Получает высоту категории.  
  
```  
int GetCategoryHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота категории.  
  
### <a name="remarks"></a>Примечания  
 Высота категория включает высоту вкладку «Категория».  
  
##  <a name="a-namegetcategoryindexa--cmfcribbonbargetcategoryindex"></a><a name="getcategoryindex"></a>CMFCRibbonBar::GetCategoryIndex  
 Извлекает индекс ленты в указанной категории.  
  
```  
int GetCategoryIndex(CMFCRibbonCategory* pCategory) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Указатель на нее категорию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс категория ленты, определяемое `pCategory`; или значение -1, если категория ленты не найден.  
  
##  <a name="a-namegetcontextnamea--cmfcribbonbargetcontextname"></a><a name="getcontextname"></a>CMFCRibbonBar::GetContextName  
 Получает имя категории заголовка контекста, заданного идентификатором контекста  
  
```  
BOOL GetContextName(
    UINT uiContextID,  
    CString& strName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiContextID`  
 Идентификатор контекста категории ленты.  
  
 [выходной] `strName`  
 Имя категории заголовка контекста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае — `FALSE` Если `uiContextID` равно нулю или заголовок категории контекста не найден.  
  
##  <a name="a-namegetdroppeddowna--cmfcribbonbargetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonBar::GetDroppedDown  
 Извлекает элемент ленты, в настоящее время удаленной работы.  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент ленты, в настоящее время удаленной работы; или `NULL` Если ни один элемент ленты в настоящее время удаляется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetelementsbyida--cmfcribbonbargetelementsbyid"></a><a name="getelementsbyid"></a>CMFCRibbonBar::GetElementsByID  
 Извлекает массив указателей на все элементы ленты, которые имеют идентификатор конкретной команды.  
  
```  
void GetElementsByID(
    UINT uiCmdID,  
    CArray<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& arButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды элемента ленты.  
  
 [выходной] `arButtons`  
 Массив указателей на элементы ленты.  
  
### <a name="remarks"></a>Примечания  
 Несколько элементов ленты могут иметь один и тот же идентификатор команды, поскольку некоторые элементы ленты можно скопировать на панель быстрого доступа.  
  
##  <a name="a-namegethideflagsa--cmfcribbonbargethideflags"></a><a name="gethideflags"></a>CMFCRibbonBar::GetHideFlags  
 Получает флаги, указывающие, сколько ленты является видимым.  
  
```  
DWORD GetHideFlags() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги, указывающие, сколько ленты является видимым.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице перечислены возможные комбинации флагов для возвращаемого значения:  
  
 `AFX_RIBBONBAR_HIDE_ELEMENTS`  
 Панель ленты свернута по вертикали и отображаются только вкладки категории, основной кнопки и панель быстрого доступа.  
  
 `AFX_RIBBONBAR_HIDE_ALL`  
 Ширина ленты меньше, чем минимальная ширина и полностью скрыт.  
  
##  <a name="a-namegetitemidslista--cmfcribbonbargetitemidslist"></a><a name="getitemidslist"></a>CMFCRibbonBar::GetItemIDsList  
 Извлекает идентификаторы команд для указанной коллекции элементов ленты на ленте.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems,  
    BOOL bHiddenOnly = FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lstItems`  
 Список идентификаторов команд для элементов ленты, содержащиеся на панели ленты.  
  
 [in] `bHiddenOnly`  
 `TRUE`Чтобы исключить элементы ленты, которые выводятся на экран; `FALSE` для включения всех элементов ленты в ленте.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetkeyboardnavigationlevela--cmfcribbonbargetkeyboardnavigationlevel"></a><a name="getkeyboardnavigationlevel"></a>CMFCRibbonBar::GetKeyboardNavigationLevel  
 Получает текущий уровень навигации, как пользователь нажимает Ключевые подсказки, содержащихся на ленте.  
  
```  
int GetKeyboardNavigationLevel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень навигации как пользователь нажимает Ключевые подсказки, содержащихся на ленте. В следующей таблице перечислены возможные возвращаемые значения:  
  
 -1  
 Ключевые подсказки не отображаются.  
  
 0  
 Ключевые подсказки отображаются.  
  
 1  
 Пользователь нажал отображается значение свойства keytip.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetkeyboardnavlevelcurrenta--cmfcribbonbargetkeyboardnavlevelcurrent"></a><a name="getkeyboardnavlevelcurrent"></a>CMFCRibbonBar::GetKeyboardNavLevelCurrent  
 Получает текущий объект навигации клавиатуры на ленте.  
  
```  
CObject* GetKeyboardNavLevelCurrent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий объект навигации клавиатуры на ленте; в противном случае `NULL` Если ни один из объектов в настоящее время отображает ключевые подсказки.  
  
### <a name="remarks"></a>Примечания  
 Объект, который в данный момент отображает ключевые подсказки является текущий объект навигации клавиатуры.  
  
##  <a name="a-namegetkeyboardnavlevelparenta--cmfcribbonbargetkeyboardnavlevelparent"></a><a name="getkeyboardnavlevelparent"></a>CMFCRibbonBar::GetKeyboardNavLevelParent  
 Получает родительский объект навигации клавиатуры на ленте.  
  
```  
CObject* GetKeyboardNavLevelParent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Родительский объект навигации клавиатуры на ленте; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь нажимает значение свойства keytip ленты, текущий объект навигации клавиатуры становится родительский объект навигации клавиатуры.  
  
##  <a name="a-namegetmaincategorya--cmfcribbonbargetmaincategory"></a><a name="getmaincategory"></a>CMFCRibbonBar::GetMainCategory  
 Извлекает указатель на главной категорией.  
  
```  
CMFCRibbonCategory* GetMainCategory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на главной категорией.  
  
### <a name="remarks"></a>Примечания  
 Категория основной ленты содержит панель основных ленты.  
  
##  <a name="a-namegetqatcommandslocationa--cmfcribbonbargetqatcommandslocation"></a><a name="getqatcommandslocation"></a>CMFCRibbonBar::GetQATCommandsLocation  
 Возвращает прямоугольник, отображаемое в разделе команды панели инструментов быстрого доступа.  
  
```  
CRect GetQATCommandsLocation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник отображения раздела «команды» панели инструментов быстрого доступа.  
  
### <a name="remarks"></a>Примечания  
 Раздел команды отображаемый прямоугольник не включает кнопку настройки.  
  
##  <a name="a-namegetqatdroppeddowna--cmfcribbonbargetqatdroppeddown"></a><a name="getqatdroppeddown"></a>CMFCRibbonBar::GetQATDroppedDown  
 Извлекает указатель на элемент ленты, на панели инструментов быстрого доступа, которая имеет выстроены его во всплывающем меню.  
  
```  
CMFCRibbonBaseElement* GetQATDroppedDown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты на панели инструментов быстрого доступа, которая имеет выстроены его во всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetquickaccesscommandsa--cmfcribbonbargetquickaccesscommands"></a><a name="getquickaccesscommands"></a>CMFCRibbonBar::GetQuickAccessCommands  
 Получает список идентификаторов команд для элементов ленты на панель быстрого доступа.  
  
```  
void GetQuickAccessCommands(CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lstCommands`  
 Список идентификаторов команд для элементов ленты на панель быстрого доступа.  
  
### <a name="remarks"></a>Примечания  
 Список не содержит элементы ленты, которые являются разделителями управления.  
  
##  <a name="a-namegetquickaccesstoolbarlocationa--cmfcribbonbargetquickaccesstoolbarlocation"></a><a name="getquickaccesstoolbarlocation"></a>CMFCRibbonBar::GetQuickAccessToolbarLocation  
 Возвращает прямоугольник, отображения панели инструментов быстрого доступа.  
  
```  
CRect GetQuickAccessToolbarLocation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник отображения панели инструментов быстрого доступа.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabtrancateratioa--cmfcribbonbargettabtrancateratio"></a><a name="gettabtrancateratio"></a>CMFCRibbonBar::GetTabTrancateRatio  
 Получает размер в процентах снижение ширину вкладок категории.  
  
```  
int GetTabTrancateRatio() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Процент размера уменьшение ширину вкладок категории.  
  
### <a name="remarks"></a>Примечания  
 Вкладки категории уменьшаются в ширину, когда не хватает ширины на ленте.  
  
##  <a name="a-namegettooltipfixedwidthlargeimagea--cmfcribbonbargettooltipfixedwidthlargeimage"></a><a name="gettooltipfixedwidthlargeimage"></a>CMFCRibbonBar::GetTooltipFixedWidthLargeImage  
 Извлекает большого размера, ширины и подсказки для ленты.  
  
```  
int GetTooltipFixedWidthLargeImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Большой размер подсказки ширину в пикселях.  
  
### <a name="remarks"></a>Примечания  
 При большом размере ширина подсказки равно 0, зависит от ширины.  
  
##  <a name="a-namegettooltipfixedwidthregulara--cmfcribbonbargettooltipfixedwidthregular"></a><a name="gettooltipfixedwidthregular"></a>CMFCRibbonBar::GetTooltipFixedWidthRegular  
 Извлекает обычного размера, ширины и подсказки для ленты.  
  
```  
int GetTooltipFixedWidthRegular() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обычный размер подсказки ширину в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Если обычного размера, ширины и подсказки равно 0, зависит от ширины.  
  
##  <a name="a-namegetvisiblecategorycounta--cmfcribbonbargetvisiblecategorycount"></a><a name="getvisiblecategorycount"></a>CMFCRibbonBar::GetVisibleCategoryCount  
 Получает номер категории отображается на ленте.  
  
```  
int GetVisibleCategoryCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число категорий отображается на ленте.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehideallcontextcategoriesa--cmfcribbonbarhideallcontextcategories"></a><a name="hideallcontextcategories"></a>CMFCRibbonBar::HideAllContextCategories  
 Скрывает все категории контекста на ленте.  
  
```  
BOOL HideAllContextCategories();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория по крайней мере один контекст был скрыт; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если категория контекст является активным, активной категории сбрасывается до первой категории отображается в списке категорий.  
  
##  <a name="a-namehidekeytipsa--cmfcribbonbarhidekeytips"></a><a name="hidekeytips"></a>CMFCRibbonBar::HideKeyTips  
 Скрывает все ключевые подсказки на ленте.  
  
```  
void HideKeyTips();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehittesta--cmfcribbonbarhittest"></a><a name="hittest"></a>CMFCRibbonBar::HitTest  
 Извлекает указатель на расположение точки элемента ленты.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
    CPoint point,  
    BOOL bCheckActiveCategory= FALSE,  
    BOOL bCheckPanelCaption= FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Расположение точки в координатах панели ленты.  
  
 [in] `bCheckActiveCategory`  
 `TRUE`для поиска active категории; `FALSE` не следует искать активной категории.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`Проверяемый заголовок панели ленты с точки, находящейся в ней; `FALSE` не для тестирования заголовок панели ленты с точки, находящейся в ней. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент ленты, расположенный в заданной точке; в противном случае `NULL` Если точка находится не в элементе ленты.  
  
### <a name="remarks"></a>Примечания  
 Заголовок панели ленты с точки, находящейся в ней не проверены, если `bCheckActiveCategory` параметр `TRUE`.  
  
##  <a name="a-nameiskeytipenableda--cmfcribbonbariskeytipenabled"></a><a name="iskeytipenabled"></a>CMFCRibbonBar::IsKeyTipEnabled  
 Указывает, включена ли функция подсказки клавиш.  
  
```  
BOOL IsKeyTipEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена функция подсказки клавиш; в противном случае `FALSE`.  
  
##  <a name="a-nameismainribbonbara--cmfcribbonbarismainribbonbar"></a><a name="ismainribbonbar"></a>CMFCRibbonBar::IsMainRibbonBar  
 Указывает, является ли лента основной ленты.  
  
```  
virtual BOOL IsMainRibbonBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`. Переопределите этот метод, чтобы указать, является ли лента основной ленты.  
  
##  <a name="a-nameisprintpreviewenableda--cmfcribbonbarisprintpreviewenabled"></a><a name="isprintpreviewenabled"></a>CMFCRibbonBar::IsPrintPreviewEnabled  
 Указывает, является ли **предварительный** включена.  
  
```  
BOOL IsPrintPreviewEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если **предварительный** компонент включен; в противном случае `FALSE`.  
  
##  <a name="a-nameisqatemptya--cmfcribbonbarisqatempty"></a><a name="isqatempty"></a>CMFCRibbonBar::IsQATEmpty  
 Указывает, содержит кнопки панели инструментов быстрого доступа.  
  
```  
BOOL IsQATEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если команда кнопками панели инструментов быстрого доступа; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisquickaccesstoolbarontopa--cmfcribbonbarisquickaccesstoolbarontop"></a><a name="isquickaccesstoolbarontop"></a>CMFCRibbonBar::IsQuickAccessToolbarOnTop  
 Указывает, является ли панель быстрого доступа находится над или под лентой.  
  
```  
BOOL IsQuickAccessToolbarOnTop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель быстрого доступа находится на ленте; `FALSE` Если панель быстрого доступа находится в группе ленты.  
  
##  <a name="a-nameisreplaceframecaptiona--cmfcribbonbarisreplaceframecaption"></a><a name="isreplaceframecaption"></a>CMFCRibbonBar::IsReplaceFrameCaption  
 Указывает, заменяет ленты или находится в заголовке фрейма главного окна.  
  
```  
BOOL IsReplaceFrameCaption() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если лента заменяет заголовок фрейма главного окна. `FALSE` Если лента находится в заголовок фрейма главного окна.  
  
##  <a name="a-nameisshowgroupbordera--cmfcribbonbarisshowgroupborder"></a><a name="isshowgroupborder"></a>CMFCRibbonBar::IsShowGroupBorder  
 Указывает, отображать ли группы кнопок, расположенных на ленте границы группы.  
  
```  
virtual BOOL IsShowGroupBorder(CMFCRibbonButtonsGroup* pGroup) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pGroup`  
 Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `FALSE`. Переопределите этот метод для указания ли группы кнопок, расположенных на ленте отображения границы группы.  
  
##  <a name="a-nameistooltipdescrenableda--cmfcribbonbaristooltipdescrenabled"></a><a name="istooltipdescrenabled"></a>CMFCRibbonBar::IsToolTipDescrEnabled  
 Указывает, включены ли описания всплывающей подсказки.  
  
```  
BOOL IsToolTipDescrEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включены описания всплывающей подсказки. `FALSE` при отключении описания всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Подсказка описаны дополнительные описательный текст, отображаемый текст всплывающей подсказки.  
  
##  <a name="a-nameistooltipenableda--cmfcribbonbaristooltipenabled"></a><a name="istooltipenabled"></a>CMFCRibbonBar::IsToolTipEnabled  
 Указывает ли всплывающие подсказки включены или отключены для ленты.  
  
```  
BOOL IsToolTipEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если всплывающие подсказки включены. `FALSE` Если всплывающие подсказки отключены.  
  
##  <a name="a-nameistransparentcaptiona--cmfcribbonbaristransparentcaption"></a><a name="istransparentcaption"></a>CMFCRibbonBar::IsTransparentCaption  
 Указывает, задано ли отображение для цветовой схемы Windows Aero.  
  
```  
BOOL IsTransparentCaption() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если цветовой схемы Windows Aero; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonclickbuttona--cmfcribbonbaronclickbutton"></a><a name="onclickbutton"></a>CMFCRibbonBar::OnClickButton  
 Этот метод можно сохранить для обратной совместимости с существующими приложениями и не должен использоваться для разработки новых приложений.  
  
```  
virtual void OnClickButton(
    CMFCRibbonButton* pButton,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку, которая была нажата.  
  
 [in] `point`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoneditcontextmenua--cmfcribbonbaroneditcontextmenu"></a><a name="oneditcontextmenu"></a>CMFCRibbonBar::OnEditContextMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEditContextMenu(
    CMFCRibbonRichEditCtrl* pEdit,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pEdit`  
 [in] `point`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrtlchangeda--cmfcribbonbaronrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonBar::OnRTLChanged  
 Вызывается инфраструктурой при изменении направления макета.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
 `TRUE`Если макет справа налево; `FALSE` Если макет справа налево.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет макет всех элементов управления на ленте для новое направление макета.  
  
##  <a name="a-nameonsetaccdataa--cmfcribbonbaronsetaccdata"></a><a name="onsetaccdata"></a>CMFCRibbonBar::OnSetAccData  
 Этот метод является внутренним для платформы и не предназначен для вызова из пользовательского кода.  
  
```  
BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Параметры  
 длинное`lVal`  
 Индекс доступного объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если успешно; в противном случае — FALSE или S_FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonshowribboncontextmenua--cmfcribbonbaronshowribboncontextmenu"></a><a name="onshowribboncontextmenu"></a>CMFCRibbonBar::OnShowRibbonContextMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowRibbonContextMenu(
    CWnd* pWnd,  
    int x,  
    int y,  
    CMFCRibbonBaseElement* pHit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 [in] `x`  
 [in] `y`  
 [in] `pHit`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonshowribbonqatmenua--cmfcribbonbaronshowribbonqatmenu"></a><a name="onshowribbonqatmenu"></a>CMFCRibbonBar::OnShowRibbonQATMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowRibbonQATMenu(
    CWnd* pWnd,  
    int x,  
    int y,  
    CMFCRibbonBaseElement* pHit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 [in] `x`  
 [in] `y`  
 [in] `pHit`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonsyskeydowna--cmfcribbonbaronsyskeydown"></a><a name="onsyskeydown"></a>CMFCRibbonBar::OnSysKeyDown  
 Вызывается платформой, когда пользователь нажимает клавишу F10 или удерживании клавиши ALT и затем нажимает другой ключ.  
  
```  
BOOL OnSysKeyDown(
    CFrameWnd* pFrameWnd,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrameWnd`  
 Указатель фрейма главного окна родительской панели ленты.  
  
 [in] `wParam`  
 Виртуальный код клавиши.  
  
 [in] `lParam`  
 Флаги состояния клавиатуры, когда была нажата клавиша.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если событие нажатия клавиши было обработано; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonsyskeyupa--cmfcribbonbaronsyskeyup"></a><a name="onsyskeyup"></a>CMFCRibbonBar::OnSysKeyUp  
 Вызывается платформой, когда пользователь отпускает клавишу F10, клавиша ALT или ключ, который при удерживании клавиши ALT была нажата.  
  
```  
BOOL OnSysKeyUp(
    CFrameWnd* pFrameWnd,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrameWnd`  
 Указатель фрейма главного окна родительской панели ленты.  
  
 [in] `wParam`  
 Виртуальный код клавиши, выпускаемой ключа.  
  
 [in] `lParam`  
 Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если событие нажатия клавиши было обработано; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namepoptooltipa--cmfcribbonbarpoptooltip"></a><a name="poptooltip"></a>CMFCRibbonBar::PopTooltip  
 Удаляет подсказки из представления.  
  
```  
void PopTooltip();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namepretranslatemessagea--cmfcribbonbarpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCRibbonBar::PreTranslateMessage  
 Определяет, если указанное сообщение обрабатывается ленты.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
 Указатель на сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если сообщение было обработано с лентой; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namerecalclayouta--cmfcribbonbarrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonBar::RecalcLayout  
 Изменение макета всех элементов управления на ленте.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 После настройки макета обновляется отображение ленты.  
  
##  <a name="a-nameremoveallcategoriesa--cmfcribbonbarremoveallcategories"></a><a name="removeallcategories"></a>CMFCRibbonBar::RemoveAllCategories  
 Удаляет все категории ленты из ленты.  
  
```  
void RemoveAllCategories();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все категории ленты из памяти и из списка категорий.  
  
##  <a name="a-nameremoveallfromtabsa--cmfcribbonbarremoveallfromtabs"></a><a name="removeallfromtabs"></a>CMFCRibbonBar::RemoveAllFromTabs  
 Удаляет все элементы ленты из области вкладки.  
  
```  
void RemoveAllFromTabs();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию, если вы хотите удалить все элементы, добавленные в область вкладки с помощью [CMFCRibbonBar::AddToTabs](#addtotabs) метод.  
  
##  <a name="a-nameremovecategorya--cmfcribbonbarremovecategory"></a><a name="removecategory"></a>CMFCRibbonBar::RemoveCategory  
 Удаляет категорию указанного ленты из ленты.  
  
```  
BOOL RemoveCategory(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс категорию в списке категорий ленты, содержащаяся в ленте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если категория указанного ленты был удален; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категория указанного ленты удаляется из памяти и из списка категорий.  
  
##  <a name="a-namesetactivecategorya--cmfcribbonbarsetactivecategory"></a><a name="setactivecategory"></a>CMFCRibbonBar::SetActiveCategory  
 Задает в качестве активной категории ленты в указанной категории.  
  
```  
BOOL SetActiveCategory(
    CMFCRibbonCategory* pCategory,  
    BOOL bForceRestore= FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCategory`  
 Категория ленты, содержащаяся в ленте.  
  
 [in] `bForceRestore`  
 `TRUE`Чтобы повысить ленты в том случае, если он свернут; `FALSE` для отображения активной категории во всплывающем окне, если панель ленты свернута.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанная категория была активной категории; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Категория основной ленты не может быть активной категории.  
  
 Если заданная категория `pCategory` — не отображается, его невозможно задать в качестве активной категории.  
  
##  <a name="a-namesetactivemdichilda--cmfcribbonbarsetactivemdichild"></a><a name="setactivemdichild"></a>CMFCRibbonBar::SetActiveMDIChild  
 Связывает системы кнопки на ленте, которому принадлежат дочернего окна многодокументного интерфейса (MDI) для указанного дочернего окна MDI.  
  
```  
void SetActiveMDIChild(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель у дочернего окна MDI.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetapplicationbuttona--cmfcribbonbarsetapplicationbutton"></a><a name="setapplicationbutton"></a>CMFCRibbonBar::SetApplicationButton  
 Помещает на панель ленты кнопку приложения.  
  
```  
void SetApplicationButton(
    CMFCRibbonApplicationButton* pButton,  
    CSize sizeButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку ленты приложения.  
  
 [in] `sizeButton`  
 Размер кнопки ленты приложения.  
  
### <a name="remarks"></a>Примечания  
 На ленте приложения является большой со скругленными кнопку, расположенную в левом верхнем углу элемента управления ленты.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetApplicationButton` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#3;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_4.cpp)]  
  
##  <a name="a-namesetelementkeysa--cmfcribbonbarsetelementkeys"></a><a name="setelementkeys"></a>CMFCRibbonBar::SetElementKeys  
 Задает ключевые подсказки для всех элементов ленты, имеющих идентификатор указанной команды.  
  
```  
BOOL SetElementKeys(
    UINT uiCmdID,  
    LPCTSTR lpszKeys,  
    LPCTSTR lpszMenuKeys= NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Идентификатор команды элемента ленты.  
  
 [in] `lpszKeys`  
 Значение свойства keytip.  
  
 [in] `lpszMenuKeys`  
 Значение свойства keytip меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если ключевые подсказки ленты по крайней мере один элемент; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Значение свойства keytip дополнительным меню — для элементов ленты с разворачивающуюся кнопку, открывается контекстное меню.  
  
##  <a name="a-namesetkeyboardnavigationlevela--cmfcribbonbarsetkeyboardnavigationlevel"></a><a name="setkeyboardnavigationlevel"></a>CMFCRibbonBar::SetKeyboardNavigationLevel  
 Задает уровень навигации клавиатуры, как пользователь нажимает Ключевые подсказки, содержащихся на ленте.  
  
```  
void SetKeyboardNavigationLevel(
    CObject* pLevel,  
    BOOL bSetFocus = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pLevel`  
 Указатель на текущий объект навигации клавиатуры.  
  
 [in] `bSetFocus`  
 `TRUE`Чтобы установить фокус на панель ленты.  
  
### <a name="remarks"></a>Примечания  
 Ленты с помощью клавиатуры начинается, когда пользователь нажимает клавишу ALT или F10. Пользователь выбирает следующий уровень навигации, нажав клавишу значение свойства keytip на ленте. Пользователя можно вернуться на предыдущий уровень навигации, нажав клавишу ESC.  
  
##  <a name="a-namesetmaximizemodea--cmfcribbonbarsetmaximizemode"></a><a name="setmaximizemode"></a>CMFCRibbonBar::SetMaximizeMode  
 Настраивает ленту при размер окна дочернего окна многодокументного интерфейса (MDI) или выходе из развернутого состояния.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMax`  
 `TRUE`для отображения кнопки системы для дочерних MDI-окно на ленте; `FALSE` для удаления кнопки системы для дочерних MDI-окно из ленты.  
  
 [in] `pWnd`  
 Указатель фрейма главного окна ленты.  
  
### <a name="remarks"></a>Примечания  
 Ленты отображаются кнопки системы для дочернего окна MDI в строке вкладок, когда развернута дочернего окна MDI.  
  
##  <a name="a-namesetquickaccesscommandsa--cmfcribbonbarsetquickaccesscommands"></a><a name="setquickaccesscommands"></a>CMFCRibbonBar::SetQuickAccessCommands  
 Добавляет один или несколько элементов ленты на панель быстрого доступа.  
  
```  
void SetQuickAccessCommands(
    const CList<UINT,UINT>& lstCommands,  
    BOOL bRecalcLayout=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lstCommands`  
 Список команд на панель быстрого доступа.  
  
 [in] `bRecalcLayout`  
 `TRUE`Если требуется перерисовать ленте после добавления элементов ленты; `FALSE` в противном случае.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetQuickAccessCommands` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp №&8;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_5.cpp)]  
  
##  <a name="a-namesetquickaccessdefaultstatea--cmfcribbonbarsetquickaccessdefaultstate"></a><a name="setquickaccessdefaultstate"></a>CMFCRibbonBar::SetQuickAccessDefaultState  
 Задает состояние по умолчанию панель быстрого доступа.  
  
```  
void SetQuickAccessDefaultState(const CMFCRibbonQuickAccessToolBarDefaultState& state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `state`  
 Состояние по умолчанию панель инструментов быстрого доступа.  
  
### <a name="remarks"></a>Примечания  
 Состояние панели инструментов быстрого доступа содержит список команд и видимостью.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetQuickAccessDefaultState` метод `CMFCRibbonBar` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp №&9;](../../mfc/reference/codesnippet/cpp/cmfcribbonbar-class_6.cpp)]  
  
##  <a name="a-namesetquickaccesstoolbarontopa--cmfcribbonbarsetquickaccesstoolbarontop"></a><a name="setquickaccesstoolbarontop"></a>CMFCRibbonBar::SetQuickAccessToolbarOnTop  
 Позиционирует панель быстрого доступа, выше или ниже ленты.  
  
```  
void SetQuickAccessToolbarOnTop(BOOL bOnTop);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOnTop`  
 `TRUE`Чтобы разместить панель быстрого доступа над лентой; `FALSE` позицию панель быстрого доступа под лентой.  
  
##  <a name="a-namesettooltipfixedwidtha--cmfcribbonbarsettooltipfixedwidth"></a><a name="settooltipfixedwidth"></a>CMFCRibbonBar::SetTooltipFixedWidth  
 Задает регулярное и больших размеров подсказки фиксированную ширину для ленты.  
  
```  
void SetTooltipFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nWidthRegular`  
 Ширина в пикселях регулярных подсказка фиксированного размера.  
  
 [in] `nWidthLargeImage`  
 Ширина в пикселях большого фиксированного размера всплывающей подсказки.  
  
### <a name="remarks"></a>Примечания  
 Параметр 0 при указании соответствующую ширину для изменения.  
  
##  <a name="a-nameshowcategorya--cmfcribbonbarshowcategory"></a><a name="showcategory"></a>CMFCRibbonBar::ShowCategory  
 Отображает или скрывает указанную категорию ленты.  
  
```  
void ShowCategory(
    int nIndex,  
    BOOL bShow=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Индекс категория ленты.  
  
 [in] `bShow`  
 Если `TRUE`, Показать категория ленты; в противном случае — скрыть категория ленты.  
  
##  <a name="a-nameshowcontextcategoriesa--cmfcribbonbarshowcontextcategories"></a><a name="showcontextcategories"></a>CMFCRibbonBar::ShowContextCategories  
 Показывает или скрывает категории контекста с указанным идентификатором.  
  
```  
void ShowContextCategories(
    UINT uiContextID,  
    BOOL bShow=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiContextID`  
 Идентификатор категории контекста.  
  
 [in] `bShow`  
 Если `TRUE`, Показать категории с указанным идентификатором; в противном случае — скрыть категории с указанным идентификатором.  
  
##  <a name="a-nameshowkeytipsa--cmfcribbonbarshowkeytips"></a><a name="showkeytips"></a>CMFCRibbonBar::ShowKeyTips  
 На ленте показаны ключевые подсказки для каждого элемента ribbon.  
  
```  
void ShowKeyTips();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nametogglemimimizestatea--cmfcribbonbartogglemimimizestate"></a><a name="togglemimimizestate"></a>CMFCRibbonBar::ToggleMimimizeState  
 Переключает лентой между состояниями свернутом и развернутом состоянии.  
  
```  
void ToggleMimimizeState();
```  
  
### <a name="remarks"></a>Примечания  
 Опечатка в имени метода является известной проблемой.  
  
 В свернутом состоянии скрыт, элемент управления ленты и отображаются только вкладки. Когда пользователь щелкает вкладку, элемент управления на ленте отображаются в виде всплывающего окна. Окно закрывается, когда пользователь щелкает немедленно или выполняет команду.  
  
##  <a name="a-nametranslatechara--cmfcribbonbartranslatechar"></a><a name="translatechar"></a>CMFCRibbonBar::TranslateChar  
 Определяет, обрабатывается ли код символа указанного нажатие клавиши ленты.  
  
```  
virtual BOOL TranslateChar(UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
 Код знака клавиши пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если код символ был обработан элементом панели ленты; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Функция подсказки клавиш позволяет пользователям перемещаться ленты с помощью клавиатуры.  
  
##  <a name="a-namegetfocuseda--cmfcribbonbargetfocused"></a><a name="getfocused"></a>CMFCRibbonBar::GetFocused  
 Возвращает элемент, имеющий фокус ввода.  
  
```  
virtual CMFCRibbonBaseElement* GetFocused();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с фокусом ввода или `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiswindows7looka--cmfcribbonbariswindows7look"></a><a name="iswindows7look"></a>CMFCRibbonBar::IsWindows7Look  
 Указывает, имеет ли ленты поиска (небольшое приложение прямоугольная кнопка) Windows 7.  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если лента имеет Windows 7 поиска; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameloadfromresourcea--cmfcribbonbarloadfromresource"></a><a name="loadfromresource"></a>CMFCRibbonBar::LoadFromResource  
 Перегружен. Загружает панель ленты из ресурсов приложения.  
  
```  
virtual BOOL LoadFromResource(
    UINT uiXMLResID,  
    LPCTSTR lpszResType = RT_RIBBON,  
    HINSTANCE hInstance = NULL);

 
virtual BOOL LoadFromResource(
    LPCTSTR lpszXMLResID,  
    LPCTSTR lpszResType = RT_RIBBON,  
    HINSTANCE hInstance = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `uiXMLResID`  
 Указывает ресурс идентификатор XML-строку с информацией ленты.  
  
 `lpszResType`  
 Указывает тип ресурса, находящегося по адресу `uiXMLResID`.  
  
 `hInstance`  
 Дескриптор модуля, чьи исполняемый файл содержит ресурс. Если `hInstance` — `NULL`, система загружает ресурс из модуля, который был использован для создания текущего процесса.  
  
 `lpszXMLResID`  
 Указывает идентификатор ресурса (в виде строки) с лентой сведения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если загрузка прошла успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesavetoxmlbuffera--cmfcribbonbarsavetoxmlbuffer"></a><a name="savetoxmlbuffer"></a>CMFCRibbonBar::SaveToXMLBuffer  
 Сохраняет панель ленты в буфер.  
  
```  
UINT SaveToXMLBuffer(LPBYTE* ppBuffer) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppBuffer`  
 Когда эта функция возвращает, `ppBuffer` указывает на буфер, выделенный с помощью данного метода и содержит сведения о ленте в формате XML.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesavetoxmlfilea--cmfcribbonbarsavetoxmlfile"></a><a name="savetoxmlfile"></a>CMFCRibbonBar::SaveToXMLFile  
 Сохраняет XML-файла ленты.  
  
```  
BOOL SaveToXMLFile(LPCTSTR lpszFilePath) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFilePath`  
 Задает выходной файл.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetwindows7looka--cmfcribbonbarsetwindows7look"></a><a name="setwindows7look"></a>CMFCRibbonBar::SetWindows7Look  
 Включает или отключает внешний вид Windows 7 (небольшое приложение прямоугольная кнопка) для ленты.  
  
```  
void SetWindows7Look(
    BOOL bWindows7Look,  
    BOOL bRecalc = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bWindows7Look`  
 `TRUE`Задает внешний вид Windows 7; `FALSE` в противном случае.  
  
 `bRecalc`  
 `TRUE`повторно вычисляет макет ленты; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)   
 [Класс CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)   
 [Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Пошаговое руководство: Обновление приложения MFC Scribble](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)




