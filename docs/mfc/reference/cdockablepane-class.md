---
title: "Класс CDockablePane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane class
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
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
ms.openlocfilehash: dea1f1ce66c0e9bedbe83109ab62055a4af2ebce
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepane-class"></a>CDockablePane Class
Реализует область, которую можно закрепить на сайте закрепления или включить в область с вкладками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|Создает и инициализирует объект `CDockablePane`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|Присоединяет области в другую область. При этом создается область с вкладками.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Возвращает размер области прямоугольника.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Определяет ли указанный мини-кадр можно прикреплять к области.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|Определяет ли другая область можно прикрепить к текущей области.|  
|[CDockablePane::CanAutoHide](#canautohide)|Определяет, поддерживает ли области режима автоматического скрытия. (Переопределяет [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|Определяет, может ли закрепляться текущей области в другую область.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует один или несколько закрепляемых областей документы с вкладками MDI.|  
|[CDockablePane::CopyState](#copystate)|Копирует состояние закрепляемой области.|  
|[CDockablePane::Create](#create)|Создает элемент управления Windows и присоединяет его к `CDockablePane` объекта.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Создает разделитель по умолчанию для области, как она закреплена фрейме окна.|  
|[CDockablePane::CreateEx](#createex)|Создает элемент управления Windows и присоединяет его к `CDockablePane` объекта.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Создает область с вкладками в текущей области.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Закрепляет контейнер области.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Закрепляет область с помощью структуры (standard) закрепления.|  
|`CDockablePane::DockToFrameWindow`|Для внутреннего использования. Чтобы закрепить в области, используйте [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) или [CDockablePane::DockToWindow](#docktowindow).|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Закрепляет область его хранимых последнюю позицию закрепления.|  
|[CDockablePane::DockToWindow](#docktowindow)|Закрепляет один закрепляемой области в другую область закрепления.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Включает или отключает режим автоматического скрытия для этой панели, а также других областей в контейнере.|  
|[CDockablePane::EnableGripper](#enablegripper)|Отображение или скрытие заголовка (захвата).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Определяет положение области при отображении в режиме автоматического скрытия.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Получает режим автоматического Скрыть слайд для области.|  
|`CDockablePane::GetAutoHideButton`|Для внутреннего использования.|  
|`CDockablePane::GetAutoHideToolBar`|Для внутреннего использования.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Возвращает высоту текущего заголовка.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Возвращает разделитель области по умолчанию для области контейнера.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Определяет возможность закрепить область на основе предоставленного указателя размещения.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Возвращает чувствительности перетащите закрепляемой области.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Возвращает процент пространства, занимаемого область в пределах контейнера.|  
|[CDockablePane::GetTabArea](#gettabarea)|Получает область вкладки для области.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Возвращает сведения класса среды выполнения о окна с вкладками, созданный в другой области закрепляет текущей области.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Указывает, можно ли переключить в режим автоматического скрытия области закрепления.|  
|[CDockablePane::HitTest](#hittest)|Указывает конкретное расположение в область, когда пользователь нажимает кнопку мыши.|  
|`CDockablePane::IsAccessibilityCompatible`|Для внутреннего использования.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Указывает, могут быть помещены закрепляемой области и все остальные области в контейнере в режиме автоматического скрытия.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Определяет, является ли область в режиме автоматического скрытия.|  
|`CDockablePane::IsChangeState`|Для внутреннего использования.|  
|[CDockablePane::IsDocked](#isdocked)|Определяет, закреплен ли текущей области.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Определяет поведение панели, которая находится в режиме автоматического скрытия, если он показан (или скрыт) путем вызова `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма с несколькими областями.|  
|[CDockablePane::IsResizable](#isresizable)|Указывает, является ли изменяться размеры области.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Указывает, находятся ли вкладок в верхней или нижней части панели.|  
|[CDockablePane::IsTracked](#istracked)|Указывает ли область перетаскиваемого пользователем.|  
|[CDockablePane::IsVisible](#isvisible)|Определяет, видима ли текущей области.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|Для внутреннего использования.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Вызывается инфраструктурой при изменении родительской области. (Переопределяет [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Вызывается инфраструктурой при закрепляет плавающей панели закрепления в окне фрейма.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается инфраструктурой при родительской области. (Переопределяет [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Вызывается инфраструктурой при область о число с плавающей запятой. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|Платформа вызывает этот метод, когда вне дока область.|  
|[CDockablePane::ReplacePane](#replacepane)|Заменяет области указанной области.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Платформа вызывает этот метод при десериализации для восстановления разделитель области по умолчанию область.|  
|`CDockablePane::SaveState`|Для внутреннего использования.|  
|`CDockablePane::Serialize`|Сериализует области. (Переопределяет `CBasePane::Serialize`.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Скрывает панель закрепления видимым и режим автоматического скрытия.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Задает кнопка автоматического скрытия и автоматического скрытия панели инструментов для панели.|  
|`CDockablePane::SetDefaultPaneDivider`|Для внутреннего использования.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Задает процент пространства, занимаемого область в пределах контейнера.|  
|`CDockablePane::SetResizeMode`|Для внутреннего использования.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Задает разделитель панели восстановленной по умолчанию.|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|Задает сведения о классе среды выполнения для окна с вкладками, которое создается, когда две области закрепления вместе.|  
|[CDockablePane::ShowPane](#showpane)|Отображение или скрытие панели.|  
|[CDockablePane::Slide](#slide)|Отображение или скрытие области с скользящий анимации, которая отображает только в том случае, если панель находится в режиме автоматического скрытия.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Переключение режима автоматического скрытия. (Переопределяет [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|Открепляется панели от фрейма главного окна или окна области контейнера.|  
|`CDockablePane::UnSetAutoHideMode`|Для внутреннего использования. Чтобы задать режим автоматического скрытия, используйте [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|Определяет, является ли скрытым закрепляемой области (в режиме автоматического скрытия).|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Определяет, когда области закрепления, автоскрытия следует остановить извлечение.|  
|[CDockablePane::DrawCaption](#drawcaption)|Рисует закрепления панели заголовка (захвата).|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|Вызывается, когда пользователь нажимает кнопки заголовка, отличного от `AFX_HTCLOSE` и `AFX_HTMAXBUTTON` кнопки.|  
|[CDockablePane::OnSlide](#onslide)|Вызывается платформой для подготовки к просмотру эффект скольжения автоматического скрытия при отображении и скрытии панели.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Указывает, отключен ли анимация автоматического скрытия закрепляемой области.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Определяет поведение панели, если панель находится в режиме автоматического скрытия.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Указывает скорость анимации области при ее отображены или скрыты в режиме автоматического скрытия.|  
  
## <a name="remarks"></a>Примечания  
 `CDockablePane`обеспечивает следующие функции:  
  
-   Закрепляемая область для фрейма главного окна.  
  
-   Переключение режима автоматического скрытия панели.  
  
-   Присоединение область окна с вкладками.  
  
-   Плавающая панель в плавающем окне.  
  
-   Закрепляемая область на другую панель, которая располагается в плавающем окне.  
  
-   Изменение размеров панели.  
  
-   Загрузка и сохранение состояния для области закрепления.  
  
    > [!NOTE]
    >  Сведения о состоянии сохраняется в реестре Windows.  
  
-   Создание области с заголовком или без него. Текст метки могут иметь заголовок и его можно заполнить цветом градиента.  
  
-   Перетаскивание в области при просмотре содержимого области  
  
-   В области перетаскивания при отображении перетащите прямоугольник.  
  
 Чтобы использовать закрепляемой области в приложении, сформируйте класс области из `CDockablePane` класса. Либо внедрить производного объекта в объект фрейма главного окна или в объект window, управляющий экземпляр области. Затем вызовите [CDockablePane::Create](#create) метода или [CDockablePane::CreateEx](#createex) при обработке метод `WM_CREATE` сообщение в окне главного фрейма. Наконец, Настройка области объекта путем вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane), или [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Ниже приведены рекомендации применяются к `CDockablePane` объектов:  
  
-   При вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) два не с вкладками, закрепляемой области, будет возвращен указатель в окно с вкладками в `ppTabbedControlBar` параметр. Добавление вкладок окна с вкладками, с помощью этого параметра можно продолжать.  
  
-   Вид с вкладками панели, созданный [CDockablePane::AttachToTabWnd](#attachtotabwnd) определяется `CDockablePane` объекта в `pTabControlBarAttachTo` параметр. Можно вызвать [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) Чтобы задать вид панели с вкладками, `CDockablePane` создаст. Тип по умолчанию определяется `dwTabbedStyle` из [CDockablePane::Create](#create) при первом создании `CDockablePane`. Если `dwTabbedStyle` является типом по умолчанию является AFX_CBRS_OUTLOOK_TABS [класса CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md); Если `dwTabbedStyle` является типом по умолчанию является AFX_CBRS_REGULAR_TABS [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md).  
  
-   Если нужно закрепить закрепляемой области в другую, вызвать [CDockablePane::DockToWindow](#docktowindow) метод. Исходные области должно быть закреплено где-нибудь перед вызовом этого метода.  
  
-   Переменная-член [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) элементы управления как ведут себя закрепляемых областей в автоматическое скрытие режим при вызове [CDockablePane::ShowPane](#showpane). Если значение переменной-члена `TRUE`, закрепляемых областей и их автоматического скрытия кнопки будут скрыты. В противном случае — они будут слайдов и уменьшения.  
  
-   Анимация автоматического скрытия можно отключить, установив [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) переменной-члена `TRUE`.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить `CDockablePane` объектов с помощью различных методов в `CDockablePane` класса. В примере показано включение автоматического скрытия все функции для закрепляемой области, включите заголовок или захвата, включить режим автоматического скрытия отображения области и анимировать область, в которой находится в режиме автоматического скрытия. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#27;](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#28;](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 Присоединяет текущей области к целевой области, создание область с вкладками.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pTabControlBarAttachTo`  
 Указывает целевой области, которая подключает текущую область. Целевой области должен быть закрепляемой области.  
  
 [in] `dockMethod`  
 Задает метод закрепления.  
  
 [in] `bSetActive`  
 `TRUE`для активации области с вкладками после операции присоединения; в противном случае — `FALSE`.  
  
 [выходной] `ppTabbedControlBar`  
 Содержит область с вкладками, полученный в результате операции присоединения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущую область, если это не область с вкладками; в противном случае указатель на область с вкладками, полученный в результате операции присоединения. Возвращаемое значение является `NULL` Если текущей области не может быть присоединена или если возникает ошибка.  
  
### <a name="remarks"></a>Примечания  
 При присоединении закрепляемой области на другую панель, с помощью этого метода, происходит следующее.  
  
1.  Проверки инфраструктуры ли целевой области `pTabControlBarAttachTo` обычный закрепление области или если он является производным от [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).  
  
2.  Если целевой области область с вкладками, платформа добавляет текущую область его в виде вкладки.  
  
3.  Если целевой области регулярных закрепляемой области, платформа создает область с вкладками.  
  
    -   Платформа вызывает функцию `pTabControlBarAttachTo->CreateTabbedPane`. Стиль новой области с вкладками зависит от `m_pTabbedControlBarRTC` член. По умолчанию этот член задан класс среды выполнения [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Если передать `AFX_CBRS_OUTLOOK_TABS` стиля как `dwTabbedStyle` параметр [CDockablePane::Create](#create) , объект класса среды выполнения задан метод класса среды выполнения [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Этот элемент можно изменить в любое время изменить стиль новой области.  
  
    -   Когда этот метод создает область с вкладками, платформа заменяет указатель `pTabControlBarAttachTo` (если области закрепленными или плавающими в нескольких плавающем окне) с указателем на новую область с вкладками.  
  
    -   Добавляет платформу `pTabControlBarAttachTo` панель с вкладками, на первой вкладке. Платформа добавляет текущую область вторую вкладку.  
  
4.  Если текущей области является производным от `CBaseTabbedPane`, все ее вкладки перемещаются `pTabControlBarAttachTo` и удалении текущей области. Таким образом Будьте внимательны при вызове этого метода, поскольку указатель текущей области может быть недействителен, если метод возвращает.  
  
 При присоединении одной области в другую при построении макета закрепления, задайте `dockMethod` в `DM_SHOW`.  
  
 Следует закрепить первой области, прежде чем присоединить другой области.  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 Возвращает размер области прямоугольника.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 Не используется.  
  
 [in] `bHorz`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` , содержащий размер области прямоугольника.  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 Определяет ли указанный мини-кадр можно прикреплять к области.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMiniFrame`  
 Указатель на `CPaneFrameWnd` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pMiniFrame` может быть закрепленным в области, в противном случае — `FALSE`.  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 Определяет ли другая область можно прикрепить к текущей области.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указывает области для прикрепления к текущей области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если можно закрепить области, указанной в этой области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод перед закрепленной панели для текущей области.  
  
 Переопределите эту функцию в производном классе, чтобы включить или отключить для конкретной области закрепления.  
  
 По умолчанию этот метод возвращает `TRUE` Если либо `pBar` или родительского типа `CDockablePane`.  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 Определяет ли области можно автоматического скрытия.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области можно автоматического скрытия; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `CDockablePane::CanAutoHide`Возвращает `FALSE` в любой из следующих ситуаций:  
  
-   Область не имеет родителя.  
  
-   Закрепления manager не допускает автоматическое скрытие панелей.  
  
-   Области не закреплен.  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 Определяет, может ли закрепляться текущей области в другую область.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепляемая панель можно закрепить в другую область или фрейма главного окна. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`. Переопределите этот метод в производном классе, чтобы включить или отключить закрепление без вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 Создает и инициализирует [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта закрепляемой области, вызовите [CDockablePane::Create](#create) или [CDockablePane::CreateEx](#createex) для его создания.  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 Преобразует один или несколько закрепляемых областей документы с вкладками MDI.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActiveTabOnly`  
 При преобразовании `CTabbedPane`, укажите `TRUE` для преобразования только на активную вкладку. Укажите `FALSE` для преобразования всех вкладок на панели.  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 Определяет, является ли скрытым закрепляемой области (также известный как режим Автоскрытие).  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если скрыть условия; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Она используется таймер для периодической проверки, следует ли скрывать Автоскрытие закрепляемой области. Метод возвращает `TRUE` при области не активен, панели не изменяется и указатель мыши по области не.  
  
 Если все предыдущие условия выполняются, платформа вызывает [CDockablePane::Slide](#slide) Чтобы скрыть область.  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 Определяет, когда области закрепления, автоскрытия следует остановить извлечение.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDirection`  
 `TRUE`Если область является видимой; `FALSE` Если скрыты панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если выполняется условие остановки; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 При Закрепляемая панель будет переведена в режим автоскрытия, платформа использует скользящий эффекты для отображения или скрытия панели. Платформа вызывает эту функцию, когда скользящий области. `CheckStopSlideCondition`Возвращает `TRUE` при полностью видимой области, или если он полностью скрыт.  
  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательские Автоскрытие эффекты.  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 Копирует состояние закрепляемой области.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOrgBar`  
 Указатель закрепляемой области.  
  
### <a name="remarks"></a>Примечания  
 `CDockablePane::CopyState`Копирует состояние `pOrgBar` в текущей области путем вызова следующих методов:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Создает элемент управления Windows и присоединяет его к [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCaption`  
 Задает имя окна.  
  
 [in] [out]`pParentWnd`  
 Указывает родительского окна.  
  
 [in] `rect`  
 Задает размер и положение окна в координатах клиента из `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`Создание области с помощью заголовка; в противном случае — `FALSE`.  
  
 [in] `nID`  
 Указывает идентификатор дочернего окна. Это значение должно быть уникальным, если вы хотите сохранить состояние стыковки для этой области закрепления.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна.  
  
 [in] `dwTabbedStyle`  
 Указывает стиль окна с вкладками, которое создается, когда пользователь перетаскивает область в заголовке панели с вкладками.  
  
 [in] `dwControlBarStyle`  
 Задает стиль дополнительные атрибуты.  
  
 [in] [out]`pContext`  
 Указывает контекст создания окна.  
  
 [in] `lpszWindowName`  
 Задает имя окна.  
  
 [in] `sizeDefault`  
 Указывает размер окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Закрепляемая область успешно создан; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Область Windows создает и присоединяет его к `CDockablePane` объекта.  
  
 Если `dwStyle` имеет стиль окна `CBRS_FLOAT_MULTI` флаг плавающем окне могут отображаться с другими областями в плавающем окне. По умолчанию закрепляемые панели только перемещаться по отдельности.  
  
 Если `dwTabbedStyle` параметр имеет `AFX_CBRS_OUTLOOK_TABS` флаг указан области создает области с вкладками стиле Outlook при присоединении к этой области с помощью другой области [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод. По умолчанию закрепляемых областей создавать регулярные вкладки типа [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 Создает разделитель по умолчанию для области, как она закреплена фрейме окна.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Указывает части главного фрейма, к которому прикреплено области. Если `dwAlignment` содержит `CBRS_ALIGN_LEFT` или `CBRS_ALIGN_RIGHT` флаг, этот метод создает вертикальный ( `CPaneDivider::SS_VERT`) разделитель; в противном случае, этот метод создает горизонтальной ( `CPaneDivider::SS_HORZ`) разделителя.  
  
 [in] `pParent`  
 Указатель родительского фрейма.  
  
 [in] `pSliderRTC`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает указатель на только что созданный разделитель или `NULL` при сбое создания разделитель.  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment`может быть одним из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Панель закреплена в верхнюю часть клиентской области окна фрейма.|  
|`CBRS_ALIGN_BOTTOM`|Панель закреплена в нижнюю часть клиентской области окна фрейма.|  
|`CBRS_ALIGN_LEFT`|Панель закреплена левого края клиентской области окна фрейма.|  
|`CBRS_ALIGN_RIGHT`|Панель закреплена правую часть клиентской области окна фрейма.|  
  
##  <a name="createex"></a>CDockablePane::CreateEx  
 Создает элемент управления Windows и присоединяет его к [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyleEx`  
 Задает атрибуты расширенного стиля для нового окна.  
  
 [in] `lpszCaption`  
 Задает имя окна.  
  
 [in] [out]`pParentWnd`  
 Указывает родительского окна.  
  
 [in] `rect`  
 Задает размер и положение окна в координатах клиента из `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`Создание области с помощью заголовка; в противном случае — `FALSE`.  
  
 [in] `nID`  
 Указывает идентификатор дочернего окна. Это значение должно быть уникальным, если вы хотите сохранить состояние стыковки для этой области закрепления.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна.  
  
 [in] `dwTabbedStyle`  
 Указывает стиль окна с вкладками, которое создается, когда пользователь перетаскивает область в заголовке панели с вкладками.  
  
 [in] `dwControlBarStyle`  
 Указывает стиль дополнительные атрибуты.  
  
 [in] [out]`pContext`  
 Указывает контекст создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Закрепляемая область успешно создан; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Область Windows создает и присоединяет его к `CDockablePane` объекта.  
  
 Если `dwStyle` имеет стиль окна `CBRS_FLOAT_MULTI` флаг плавающем окне могут отображаться с другими областями в плавающем окне. По умолчанию закрепляемые панели только перемещаться по отдельности.  
  
 Если `dwTabbedStyle` параметр имеет `AFX_CBRS_OUTLOOK_TABS` флаг указан области создает области с вкладками стиле Outlook при присоединении к этой области с помощью другой области [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод. По умолчанию закрепляемых областей создавать регулярные вкладки типа [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 Создает область с вкладками в текущей области.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая область с вкладками, или `NULL` , если не удалось выполнить операцию создания.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при создании область с вкладками для замены в этой области. Дополнительные сведения см. в разделе [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
 Переопределение этого метода в производном классе, чтобы настроить как вкладки создаются и инициализируются.  
  
 Области с вкладками создается в соответствии с классом среды выполнения, хранящихся в `m_pTabbedControlBarRTC` член, который инициализируется с [CDockablePane::CreateEx](#createex) метод.  
  
##  <a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 Закрепляет контейнер области.  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `barContainerManager`  
 Ссылка на диспетчер контейнеров контейнера, которому будет присоединен.  
  
 [in] `dwAlignment`  
 `DWORD`задающий части панели, к которому прикреплено контейнера.  
  
 [in] `dockMethod`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если контейнер был успешно прикреплено к области. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment`может быть одним из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Контейнер закрепляется в верхней части панели.|  
|`CBRS_ALIGN_BOTTOM`|Контейнер закрепляется в нижней части области.|  
|`CBRS_ALIGN_LEFT`|Контейнер закреплена слева от области.|  
|`CBRS_ALIGN_RIGHT`|Контейнер закреплена справа от области.|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 Закрепляет область с помощью структуры (standard) закрепления.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bWasDocked`  
 При возвращении метода содержит это значение `TRUE` Если области успешно закрепленной; в противном случае, он содержит `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если область была закрепить окно с вкладками или окна с вкладками был создан в результате закрепления, этот метод возвращает указатель в окно с вкладками. Если панель была в противном случае успешно закреплен, этот метод возвращает `this` указателя. Если не удалось закрепления, этот метод возвращает `NULL`.  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 Закрепляет область его сохраненную позицию закрепления.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель закреплена успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Закрепляемых областей хранения последние сведения о закреплении в [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) объекта.  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 Закрепляет один закрепляемой области в другую область закрепления.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pTargetWindow`  
 Указывает закрепляемой области закрепление этой панели.  
  
 [in] `dwAlignment`  
 Задает выравнивание закрепления панели. Возможно, один из CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM или CBRS_ALIGN_ANY. (Определено в файле afxres.h).  
  
 [in] `lpRect`  
 Указывает прямоугольник закрепления панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были закреплены успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для закрепления одной области в другую область с выравниванием, определяемым значением `dwAlignment`.  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 Рисует заголовка закрепляемой области (также называемый захвата).  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Представляет контекст устройства, используемого для рисования.  
  
 [in] `rectCaption`  
 Указывает ограничивающий прямоугольник заголовка панели.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для отображения заголовка закрепляемой области.  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид заголовка.  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 Включает или отключает режим Автоскрытие для этой области, а также для других областей в контейнере.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить автоматическое скрытие всех компонентов для закрепляемой области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если пользователь удерживает `Ctrl` ключа и щелкает кнопку ПИН-код, чтобы перейти в область в режиме Автоскрытие всех других областей, в том же контейнере также переключаются в режим автоскрытия.  
  
 Этот метод вызывается со `bEnable` значение `FALSE` для отключения этой функции для определенной области.  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 Отображение или скрытие заголовка (также называемые захвата).  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для включения заголовка; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда платформа создает закрепляемых областей, они не имеют **WS_STYLE** даже в том случае, если указанный стиль окна. Это означает, что панель заголовка неклиентской области, которое управляется средой, но в этой области отличается от стандартного заголовка окна.  
  
 Можно отобразить или скрыть заголовок в любое время. Платформа framework скрывает заголовок при добавлении области в виде вкладки окна с вкладками или область перемещается в плавающем окне.  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 Указывает положение панели в режиме автоматического скрытия.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий позицию для области, когда она находится в режиме автоматического скрытия.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 Получает режим слайдов автоматического скрытия панели.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `UINT` , указывающий режим слайдов автоматического скрытия панели. Возвращаемое значение может быть либо `AFX_AHSM_MOVE` или `AFX_AHSM_STRETCH`, но реализация использует только `AFX_AHSM_MOVE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 Возвращает высоту в пикселях текущего заголовка.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Высота заголовка равен 0, если заголовок был скрыт с [CDockablePane::EnableGripper](#enablegripper) метода, или если области не имеет заголовка.  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 Возвращает разделитель области по умолчанию для области контейнера.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Является допустимым [CPaneDivider](../../mfc/reference/cpanedivider-class.md) объекта, если закреплены закрепляемой области фрейма главного окна или `NULL` Если Закрепляемая область не закреплена или если он является перемещаемой.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о панели разделителей в разделе [CPaneDivider класса](../../mfc/reference/cpanedivider-class.md).  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 Определяет возможность закрепить область на основе предоставленного указателя размещения.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pt`  
 Положение указателя в координатах экрана.  
  
 [in] `nSensitivity`  
 Расстояние в пикселях от границы прямоугольника указатель должен находиться на Включение закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений состояния:  
  
|Значение `AFX_CS_STATUS`|Значение|  
|---------------------------|-------------|  
|`CS_NOTHING`|Указатель не наведен сайта закрепления. Платформа не закрепление области.|  
|`CS_DOCK_IMMEDIATELY`|Указатель мыши находится на сайте закрепления в режиме интерпретации (использует области `DT_IMMEDIATE` закрепления режим). Платформа закрепляет область немедленно.|  
|`CS_DELAY_DOCK`|Указатель находится над другой закрепляемую область или край фрейма главного сайта закрепления. Платформа закрепляет область с задержкой. Дополнительные сведения об этой задержки см.|  
|`CS_DELAY_DOCK_TO_TAB`|Указатель мыши находится на сайте закрепления, вызывающая панели для закрепления в окно с вкладками. Это происходит, когда указатель мыши находится над заголовком другой закрепляемой области или области вкладок область с вкладками.|  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для обработки закрепление плавающей панели.  
  
 Плавающие панели инструментов или закрепляемые панели, использующие `DT_IMMEDIATE` закрепление режиме, платформа задерживает dock команду, чтобы дать пользователю возможность перемещать окно вне клиентской области родительского фрейма перед закреплением происходит. Длительность задержки измеряется в миллисекундах и контролируется [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) элемент данных... Значение по умолчанию [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) — 200. Это поведение эмулирует закрепления элемента [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007.  
  
 Для отложенной закрепление состояния ( `CS_DELAY_DOCK` и `CS_DELAY_DOCK_TO_TAB`), платформа не выполняет закрепления, пока пользователь отпускает кнопку мыши. Если используется область `DT_STANDARD` закрепление режиме, платформа отображает прямоугольник предполагаемое место закрепления. Если используется область `DT_SMART` закрепление режиме, платформа отображает интеллектуальные маркеры стыковки и прозрачных прямоугольников в предполагаемое место закрепления. Чтобы указать режим закрепления свою собственную панель, вызовите [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) метод. Дополнительные сведения о смарт-закрепления см. в разделе [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 Возвращает чувствительности перетащите закрепляемой области.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий ширину и высоту в пикселях прямоугольника с центром в точке перетаскивания. Операции перетаскивания не начинается, пока указатель мыши перемещается за границы этого прямоугольника.  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 Возвращает процент пространства, которое занимает область в своем контейнере ( [CPaneContainer класса](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `int` , Указывающее процент пространства, занимающий области его контейнера.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется, когда контейнер корректирует его макет.  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 Получает область вкладки для области.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectTabAreaTop`  
 `GetTabArea`Если вкладки в верхней части области заполняет область вкладки этой переменной. Если вкладки в нижней части области этой переменной заполняется пустой прямоугольник.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea`Если вкладки в нижней части области заполняет область вкладки этой переменной. Если вкладки в верхней части области этой переменной заполняется пустой прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется только в классах, которые являются производными от `CDockablePane` и вкладки. Дополнительные сведения см. в разделе [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) и [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 Возвращает сведения класса среды выполнения о окна с вкладками, созданный в другой области закрепляет текущей области.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Информация о классе среды выполнения для закрепляемой панели.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения сведений класса среды выполнения для вкладки, которые создаются динамически. Это может произойти, когда пользователь перетаскивает одной области к заголовку другой области или при вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод для программного создания область с вкладками из двух закрепляемых областей.  
  
 Можно задать сведения о классе среды выполнения путем вызова [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) метод.  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 Указывает, может быть переключено закрепляемой области, автоматически скрывать режим.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемой области можно переключить в режим автоскрытия. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы отключить Автоскрытие режим для конкретных закрепляемой области.  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 Указывает расположение панели, когда пользователь нажимает кнопку мыши.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Задает точку для тестирования.  
  
 [in] `bDetectCaption`  
 `TRUE`Если `HTCAPTION` должны быть возвращены, если точка находится на панели заголовка; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
- `HTNOWHERE`Если `point` не закрепляемой панели.  
  
- `HTCLIENT`Если `point` находится в клиентской области закрепляемой области.  
  
- `HTCAPTION`Если `point` находится в области заголовка закрепляемой области.  
  
- `AFX_HTCLOSE`Если `point` является "Закрыть".  
  
- `HTMAXBUTTON`Если `point` на кнопку закрепления.  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 Указывает ли закрепляемой области и все остальные области, в контейнере можно переключить режим автоскрытия.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемой области, а все остальные области в контейнере, можно переключить в режим автоскрытия. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Пользователь включает Автоскрытие режим, нажав кнопку закрепления ПИН-код, удерживая **Ctrl** ключ  
  
 Чтобы включить или отключить это поведение, вызовите [CDockablePane::EnableAutohideAll](#enableautohideall) метод.  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 Определяет, является ли область в режиме Автоскрытие.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Закрепляемая панель находится в режиме Автоскрытие; в противном случае — `FALSE`.  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 Определяет, закреплен ли текущей области.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемой области не принадлежит окно области или если он располагается в плавающем окне с другой панелью. `FALSE`Если область является потомком окно области, и нет других областях, принадлежащих плавающем окне.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить, присоединен ли области главного окна фрейма, вызовите [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Если метод возвращает указатель отличных от NULL, панель закреплена на фрейма главного окна.  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 Определяет поведение панели, которая находится в режиме автоматически скрывать, если он показан (или скрыт) путем вызова [CDockablePane::ShowPane](#showpane).  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемой области должен быть скрыт в режиме Автоскрытие; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда в режиме Автоскрытие закрепляемой области, он ведет себя по-разному при вызове `ShowPane` скрытие или отображение панели. Это поведение управляется статический член [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Этот член является `TRUE`, закрепляемой области и его связанных автоматическое скрытие панели инструментов или Кнопка автоскрытия скрыто или показано при вызове `ShowPane`. В противном случае — закрепляемой области, активируется или деактивируется и его связанных автоматическое скрытие панели инструментов или Кнопка автоскрытия всегда является видимым.  
  
 Переопределите этот метод в производном классе, чтобы изменить поведение по умолчанию для отдельных панелей.  
  
 По умолчанию для объекта `m_bHideInAutoHideMode` установлено значение `FALSE`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 Указывает, является ли область в окне фрейма несколькими областями ( [CMultiPaneFrameWnd класса](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в окне фрейма несколькими областями. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 Указывает, является ли изменяться размеры области.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель можно изменять; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию закрепляемых областей являются изменяемыми размерами. Чтобы предотвратить изменение размеров, переопределите этот метод в производном классе и вернуть `FALSE`. Обратите внимание, что `FALSE` значение ведет к неудачной `ASSERT` в [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Используйте [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) вместо закрепление области внутри родительского фрейма.  
  
 Не может областей, которые невозможно изменить размеры число с плавающей запятой, ни в режим автоматического скрытия и всегда находятся на внешней границе родительского фрейма.  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 Указывает, находятся ли вкладок в верхней или нижней части панели.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладки в нижней части области; `FALSE` Если вкладки в верхней части области.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 Указывает, перемещается ли область пользователем.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`При перемещении области; в противном случае — `FALSE`.  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 Определяет, видима ли текущей области.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Закрепляемая область является видимым; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, будет ли видна Закрепляемая панель. Этот метод можно использовать вместо вызова метода [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) или тестирования для `WS_VISIBLE` стиля. Состояние видимости возвращаемый зависит от включен или отключен режим автоскрытия и значение [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) свойство.  
  
 Если Закрепляемая панель находится в режиме Автоскрытие и `IsHideInAutoHideMode` возвращает `FALSE` всегда имеет состояние видимости `FALSE`.  
  
 Если Закрепляемая панель находится в режиме Автоскрытие и `IsHideInAutoHideMode` возвращает `TRUE` состояние видимости зависит от состояния видимости панели инструментов связанных Автоскрытие.  
  
 Если закрепляемой области не находится в режиме Автоскрытие, состояние видимости определяется [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) метод.  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 Указывает, отключено ли автоматическое скрытие анимации закрепляемой области.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 Определяет поведение панели, когда область находится в режиме Автоскрытие.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение влияет на все области закрепления в приложении.  
  
 Если установить этот компонент равным `TRUE`, скрытых или показаны с помощью их связанные автоматическое скрытие панелей инструментов и кнопок, при вызове закрепляемых областей [CDockablePane::ShowPane](#showpane).  
  
 Если установить этот компонент равным `FALSE`, закрепляемых областей активируется или деактивируется при вызове [CDockablePane::ShowPane](#showpane).  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 Указывает скорость анимации области, когда она находится в режиме Автоскрытие.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы быстрее эффект анимации Уменьшите это значение. Медленнее эффект анимации Увеличьте это значение.  
  
##  <a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndOldParent`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 Вызывается инфраструктурой при закрепляет плавающей панели закрепления в окне фрейма.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий.  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 Платформа вызывает этот метод, перед изменением родительской области.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndNewParent`  
 Указатель на новый родительского окна.  
  
 [in] `bDelay`  
 `BOOL`указывающее, требуется ли отложить повторное вычисление макета закрепления, если панель закреплена. Дополнительные сведения см. в разделе [CDockablePane::UndockPane](#undockpane).  
  
### <a name="remarks"></a>Примечания  
 Если новый родитель не стыковки закрепленной панели, этот метод открепляется области.  
  
 Если области преобразуется в документ с вкладками, этот метод сохраняет его последней позиции закрепления. Платформа использует последнюю позицию закрепления восстановить положение панели, если она преобразуется обратно в закрепленном состоянии.  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 Платформа вызывает этот метод перед панелью переходов в плавающем состоянии.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectFloat`  
 Указывает положение и размер области, когда он находится в плавающем состоянии.  
  
 [in] `dockMethod`  
 Задает метод закрепления. В разделе [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) список возможных значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если можно перемещать области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при посвящен область с плавающей запятой. Можно переопределить этот метод в производном классе, если вы хотите выполнить обработку перед смещает области.  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 Вызывается, когда пользователь нажимает кнопки заголовка, отличного от `AFX_HTCLOSE` и `AFX_HTMAXBUTTON` кнопки.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHit`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Если добавить пользовательскую кнопку к заголовку закрепляемой области, переопределите этот метод для получения уведомлений, когда пользователь нажимает кнопку.  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 Вызывается платформой для анимации области, когда она находится в режиме Автоскрытие.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSlideOut`  
 `TRUE`для отображения области; `FALSE` скрыть области.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательские Автоскрытие эффекты.  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 Платформа вызывает этот метод, когда вне дока область.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает разделитель области по умолчанию `NULL` и удаляет области из контейнера.  
  
##  <a name="replacepane"></a>CDockablePane::ReplacePane  
 Заменяет области указанной области.  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBarToReplaceWith`  
 Указатель закрепляемой области.  
  
 [in] `dockMethod`  
 Не используется.  
  
 [in] `bRegisterWithFrame`  
 Если `TRUE`, новая область является зарегистрированной в диспетчере закрепления родительского элемента области старого. Новая область будет вставлен в индекс старый область в список областей, поддерживаемый диспетчером, закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если замена выполнена успешно; в противном случае — `FALSE`.  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 При десериализации область платформа вызывает этот метод, чтобы восстановить разделитель области по умолчанию.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>Примечания  
 Разделитель области по умолчанию восстановленный заменяет разделитель текущей области по умолчанию, если он существует.  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 Скрывает панель закрепления видимым и режим автоскрытия.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMode`  
 `TRUE`Чтобы включить автоматическое скрытие режим; `FALSE` Включение обычный режим закрепления.  
  
 [in] `dwAlignment`  
 Задает выравнивание панели автоматически скрывать, чтобы создать.  
  
 [in] [out]`pCurrAutoHideBar`  
 Указатель на текущий Автоскрытие инструментов. Может быть `NULL`.  
  
 [in] `bUseTimer`  
 Указывает, следует ли использовать влияет автоскрытия при переключении панели в режим автоскрытия или скрыть область немедленно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Автоскрытие инструментов, который был создан в результате переключения в режим автоскрытия или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь нажимает кнопку ПИН-код для закрепляемой области для переключения в режим автоскрытия или обычный режим закрепления.  
  
 Этот метод переключиться Автоскрытие режим закрепляемой области программным образом. Необходимо закрепить области фрейма главного окна ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) должен возвращать допустимый указатель на [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 Задает кнопка автоматического скрытия и автоматического скрытия панели инструментов для панели.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pToolBar`  
 Указатель на панель инструментов автоматического скрытия.  
  
 [in] `pBtn`  
 Указатель кнопка автоматического скрытия.  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 Задает процент пространства, которое занимает область в своем контейнере.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 `int` , Указывающее процент пространства, занимающий области его контейнера.  
  
### <a name="remarks"></a>Примечания  
 Платформа корректирует области, чтобы использовать новое значение при пересчете макета.  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 Задает разделитель панели восстановленной по умолчанию.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hRestoredSlider`  
 Дескриптор области разделитель (ползунка).  
  
### <a name="remarks"></a>Примечания  
 Разделитель области по умолчанию восстановленный получается при десериализации области. Дополнительные сведения см. в разделе [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).  
  
##  <a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 Задает сведения о классе среды выполнения для окна с вкладками, которое создается, когда две области закрепления вместе.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTC`  
 Информация о классе среды выполнения для области с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сведения класса среды выполнения для вкладки, которые создаются динамически. Это может произойти, когда пользователь перетаскивает одной области к заголовку другой области или при вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод для программного создания область с вкладками из двух закрепляемых областей.  
  
 Класс среды выполнения по умолчанию имеет значение согласно `dwTabbedStyle` параметр [CDockablePane::Create](#create) и [CDockablePane::CreateEx](#createex). Для настройки новой вкладки, класс производный от одного из следующих классов:  
  
- [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [Класс CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
- [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Затем этот метод с помощью указателя на его сведения класса среды выполнения.  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 Отображение или скрытие панели.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 `TRUE`для отображения области; `FALSE` скрыть области.  
  
 [in] `bDelay`  
 `TRUE`Чтобы отложить Настройка макета закрепления; `FALSE` сразу настроить макет закрепления.  
  
 [in] `bActivate`  
 `TRUE`для активации области при отображении; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вместо [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) при отображении или скрытии закрепляемых областей.  
  
##  <a name="slide"></a>CDockablePane::Slide  
 Анимирует область, в которой находится в режиме Автоскрытие.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSlideOut`  
 `TRUE`для отображения области; `FALSE` скрыть области.  
  
 [in] `bUseTimer`  
 `TRUE`Отображение или скрытие области с эффектом Автоскрытие; `FALSE` Отображение или скрытие области немедленно.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы анимировать область, в которой находится в режиме Автоскрытие.  
  
 Этот метод использует `CDockablePane::m_nSlideDefaultTimeOut` значение, чтобы определить время ожидания для эффект скольжения. Значение по умолчанию для времени ожидания — 1. Если настроить алгоритм Автоскрытие измените этот элемент, чтобы изменить время ожидания.  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 Переключение панели между всегда видны и режим автоматического скрытия.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переключает режим автоматического скрытия области путем вызова [CDockablePane::SetAutoHideMode](#setautohidemode).  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 Открепляется панели от фрейма главного окна или окна области контейнера.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDelay`  
 `TRUE`Задержка вычисления макета закрепления; `FALSE` немедленно пересчитать макета закрепления.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы отменить закрепление панели, от фрейма главного окна или из контейнера окна области multi (область, в которой располагается в одной области окна с другими областями).  
  
 Необходимо отменить закрепление области перед выполнением любой внешней операции, не выполненных [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Например необходимо отменить закрепление панели для перемещения его программно из одного расположения в другое.  
  
 Платформа автоматически открепляется панелей до их удаления.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)

