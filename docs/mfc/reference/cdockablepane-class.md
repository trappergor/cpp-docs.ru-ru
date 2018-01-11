---
title: "Класс CDockablePane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CDockablePane [MFC], CDockablePane
- CDockablePane [MFC], AttachToTabWnd
- CDockablePane [MFC], CalcFixedLayout
- CDockablePane [MFC], CanAcceptMiniFrame
- CDockablePane [MFC], CanAcceptPane
- CDockablePane [MFC], CanAutoHide
- CDockablePane [MFC], CanBeAttached
- CDockablePane [MFC], ConvertToTabbedDocument
- CDockablePane [MFC], CopyState
- CDockablePane [MFC], Create
- CDockablePane [MFC], CreateDefaultPaneDivider
- CDockablePane [MFC], CreateEx
- CDockablePane [MFC], CreateTabbedPane
- CDockablePane [MFC], DockPaneContainer
- CDockablePane [MFC], DockPaneStandard
- CDockablePane [MFC], DockToRecentPos
- CDockablePane [MFC], DockToWindow
- CDockablePane [MFC], EnableAutohideAll
- CDockablePane [MFC], EnableGripper
- CDockablePane [MFC], GetAHRestoredRect
- CDockablePane [MFC], GetAHSlideMode
- CDockablePane [MFC], GetCaptionHeight
- CDockablePane [MFC], GetDefaultPaneDivider
- CDockablePane [MFC], GetDockingStatus
- CDockablePane [MFC], GetDragSensitivity
- CDockablePane [MFC], GetLastPercentInPaneContainer
- CDockablePane [MFC], GetTabArea
- CDockablePane [MFC], GetTabbedPaneRTC
- CDockablePane [MFC], HasAutoHideMode
- CDockablePane [MFC], HitTest
- CDockablePane [MFC], IsAutohideAllEnabled
- CDockablePane [MFC], IsAutoHideMode
- CDockablePane [MFC], IsDocked
- CDockablePane [MFC], IsHideInAutoHideMode
- CDockablePane [MFC], IsInFloatingMultiPaneFrameWnd
- CDockablePane [MFC], IsResizable
- CDockablePane [MFC], IsTabLocationBottom
- CDockablePane [MFC], IsTracked
- CDockablePane [MFC], IsVisible
- CDockablePane [MFC], OnAfterChangeParent
- CDockablePane [MFC], OnAfterDockFromMiniFrame
- CDockablePane [MFC], OnBeforeChangeParent
- CDockablePane [MFC], OnBeforeFloat
- CDockablePane [MFC], RemoveFromDefaultPaneDividier
- CDockablePane [MFC], ReplacePane
- CDockablePane [MFC], RestoreDefaultPaneDivider
- CDockablePane [MFC], SetAutoHideMode
- CDockablePane [MFC], SetAutoHideParents
- CDockablePane [MFC], SetLastPercentInPaneContainer
- CDockablePane [MFC], SetRestoredDefaultPaneDivider
- CDockablePane [MFC], SetTabbedPaneRTC
- CDockablePane [MFC], ShowPane
- CDockablePane [MFC], Slide
- CDockablePane [MFC], ToggleAutoHide
- CDockablePane [MFC], UndockPane
- CDockablePane [MFC], CheckAutoHideCondition
- CDockablePane [MFC], CheckStopSlideCondition
- CDockablePane [MFC], DrawCaption
- CDockablePane [MFC], OnPressButtons
- CDockablePane [MFC], OnSlide
- CDockablePane [MFC], m_bDisableAnimation
- CDockablePane [MFC], m_bHideInAutoHideMode
- CDockablePane [MFC], m_nSlideSteps
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb32fc827c576830def3901389d400450b79f5ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdockablepane-class"></a>CDockablePane Class
Реализует область, которую можно закрепить на сайте закрепления или включить в область с вкладками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|Создает и инициализирует объект `CDockablePane`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|Присоединяет области в другую область. При этом создается область с вкладками.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Возвращает размер прямоугольника области.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Определяет ли указанный мини-рамки можно прикреплять к области.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|Определяет закреплением другой области для текущей области.|  
|[CDockablePane::CanAutoHide](#canautohide)|Определяет, поддерживает ли области режим автоматического скрытия. (Переопределяет [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|Определяет закреплением текущей области в другую область.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует одного или нескольких закрепляемых областей в документы с вкладками MDI.|  
|[CDockablePane::CopyState](#copystate)|Копирует состояние закрепляемую панель.|  
|[CDockablePane::Create](#create)|Создает элемент управления Windows и прикрепляет его к `CDockablePane` объекта.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Создает разделитель по умолчанию для области, как она закреплена область окна.|  
|[CDockablePane::CreateEx](#createex)|Создает элемент управления Windows и прикрепляет его к `CDockablePane` объекта.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Создает область с вкладками в текущей области.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Закрепляет контейнер области.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Закрепляет область с помощью структуры (standard) закрепления.|  
|`CDockablePane::DockToFrameWindow`|Используется внутренним образом. Чтобы закрепить в области, используйте [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) или [CDockablePane::DockToWindow](#docktowindow).|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Закрепляет область его сохраненную последних позицию закрепления.|  
|[CDockablePane::DockToWindow](#docktowindow)|Закрепляет одну область закрепления в другую область закрепления.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Включает или отключает режим автоматического скрытия для этой области вместе с другими областями в контейнере.|  
|[CDockablePane::EnableGripper](#enablegripper)|Отображение или скрытие заголовка (захвата).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Задает положение области, при отображении в режиме автоматического скрытия.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Извлекает режим автоматического скрытия слайдов для области.|  
|`CDockablePane::GetAutoHideButton`|Используется внутренним образом.|  
|`CDockablePane::GetAutoHideToolBar`|Используется внутренним образом.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Возвращает высоту текущего заголовка.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Возвращает разделитель по умолчанию для области контейнера.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Определяет возможность закрепления панели в зависимости от расположения предоставленного указателя.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Возвращает чувствительности закрепляемой области перетаскивания.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Извлекает процент пространства, который занимает область в пределах своего контейнера.|  
|[CDockablePane::GetTabArea](#gettabarea)|Извлекает область вкладки области.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Возвращает сведения о классе среды выполнения о окна с вкладками, созданный при закрепляет другой области для текущей области.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Указывает, является ли закрепляемой области можно переключить в режим автоматического скрытия.|  
|[CDockablePane::HitTest](#hittest)|Задает определенное место в области, когда пользователь нажимает кнопку мыши.|  
|`CDockablePane::IsAccessibilityCompatible`|Используется внутренним образом.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Указывает, можно ли поместить области закрепления и другими областями в контейнере в режиме автоматического скрытия.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Определяет, является ли область в режиме автоматического скрытия.|  
|`CDockablePane::IsChangeState`|Используется внутренним образом.|  
|[CDockablePane::IsDocked](#isdocked)|Определяет, закреплена ли текущей области.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Определяет поведение область, в которой находится в режиме автоматического скрытия при его показано (или скрыт) путем вызова `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма несколькими областями.|  
|[CDockablePane::IsResizable](#isresizable)|Указывает, является ли область с раскрывающимися списками.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Указывает, расположены ли вкладки в верхней или нижней части области.|  
|[CDockablePane::IsTracked](#istracked)|Указывает ли панель перетаскивается пользователем.|  
|[CDockablePane::IsVisible](#isvisible)|Определяет, видима ли текущей области.|  
|[CDockablePane::LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|Используется внутренним образом.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Вызывается платформой при изменении родительской области. (Переопределяет [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Вызывается платформой при закрепляет плавающей закрепляемую панель в окне фрейма.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается платформой при родительской области. (Переопределяет [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Вызывается платформой, когда область о к float. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|Платформа вызывает этот метод при вне дока областью.|  
|[CDockablePane::ReplacePane](#replacepane)|Заменяет области указанной области.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Этот метод вызывается платформой при десериализации для восстановления разделитель области по умолчанию область.|  
|`CDockablePane::SaveState`|Используется внутренним образом.|  
|`CDockablePane::Serialize`|Сериализует области. (Переопределяет `CBasePane::Serialize`.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Переключение области закрепления между видимым и режима автоматического скрытия.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Задает кнопки автоматического скрытия и автоматическое скрытие панели инструментов области.|  
|`CDockablePane::SetDefaultPaneDivider`|Используется внутренним образом.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Задает процент пространства, который занимает область в пределах своего контейнера.|  
|`CDockablePane::SetResizeMode`|Используется внутренним образом.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Задает разделитель области восстановленной по умолчанию.|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|Задает сведения о классе среды выполнения для окна с вкладками, которое создается, когда две области закрепления друг с другом.|  
|[CDockablePane::ShowPane](#showpane)|Показывает или скрывает панель.|  
|[CDockablePane::Slide](#slide)|Показывает или скрывает панель со скользящим анимации, который отображает только в том случае, если панель находится в режиме автоматического скрытия.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Переключает режим автоматического скрытия. (Переопределяет [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|Открепляется области из контейнера плавающего окна или фрейма главного окна.|  
|`CDockablePane::UnSetAutoHideMode`|Используется внутренним образом. Чтобы задать режим автоматического скрытия, используйте [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|Определяет, является ли скрытым закрепляемой области (в режиме автоматического скрытия).|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Определяет, когда автоматического скрытия закрепляемой области следует остановить со скользящим.|  
|[CDockablePane::DrawCaption](#drawcaption)|Рисует закрепления панели заголовка (захвата).|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|Вызывается, когда пользователь нажимает кнопки заголовка, отличный от `AFX_HTCLOSE` и `AFX_HTMAXBUTTON` кнопки.|  
|[CDockablePane::OnSlide](#onslide)|Вызывается платформой для отрисовки эффект скольжения автоматического скрытия при отображении и скрытии панели.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Указывает, отключен ли анимация автоматического скрытия закрепляемую панель.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Если определяет поведение окна области находится в режиме автоматического скрытия.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Указывает скорость анимации области, при отображении и скрытии в режиме автоматического скрытия.|  
  
## <a name="remarks"></a>Примечания  
 `CDockablePane`реализует следующие возможности:  
  
-   Закрепление панели в окне главного фрейма.  
  
-   Панель переключения в режим автоматического скрытия.  
  
-   Присоединение область для окна с вкладками.  
  
-   Плавающая область в плавающего окна.  
  
-   Закрепляемая область на другую панель, которая располагается в плавающего окна.  
  
-   Изменение размеров в области.  
  
-   Загрузка и сохранение состояния для закрепления панели.  
  
    > [!NOTE]
    >  Сведения о состоянии сохраняется в реестре Windows.  
  
-   Создание области с заголовком или без него. Заголовок может быть текстовую метку и заполнить цвет градиента.  
  
-   Перетаскивание в области при просмотре содержимого области  
  
-   При отображении прямоугольника перетаскивания при перемещении в области.  
  
 Для использования закрепляемую область в приложении, вашей панели создайте класс, производный от `CDockablePane` класса. Либо внедрить производного объекта в объект фрейма главного окна или в объект window, управляющий экземпляр своей области. Затем вызовите [CDockablePane::Create](#create) метода или [CDockablePane::CreateEx](#createex) метод при обработке `WM_CREATE` сообщение в окне главного фрейма. Наконец, Настройка области объекта путем вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane), или [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Ниже приведены рекомендации применяются к `CDockablePane` объектов:  
  
-   При вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) указатель на окно с вкладками для две области не с вкладками, фиксируемыми, будут возвращены в `ppTabbedControlBar` параметра. Можно продолжить добавление вкладок в окне с вкладками с помощью этого параметра.  
  
-   Тип области с вкладками, созданный [CDockablePane::AttachToTabWnd](#attachtotabwnd) определяется `CDockablePane` объекта в `pTabControlBarAttachTo` параметра. Можно вызвать [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) Чтобы задать вид области с вкладками, `CDockablePane` будет создан. Тип по умолчанию определяется `dwTabbedStyle` из [CDockablePane::Create](#create) при первом создании `CDockablePane`. Если `dwTabbedStyle` — AFX_CBRS_OUTLOOK_TABS, значение по умолчанию — [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md); Если `dwTabbedStyle` имеет значение по умолчанию — AFX_CBRS_REGULAR_TABS [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md).  
  
-   Если вы хотите закрепить один закрепляемую панель в другую, вызовите [CDockablePane::DockToWindow](#docktowindow) метод. Исходные области должно быть закреплено где-то перед вызовом этого метода.  
  
-   Переменная-член [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) элементы управления как закрепляемых областей поведение автоматически скрыть режиме при вызове [CDockablePane::ShowPane](#showpane). Если имеет значение этой переменной-члена `TRUE`, будут скрыты закрепляемых областей и их кнопки автоматического скрытия. В противном случае они будут слайда и выхода из системы.  
  
-   Анимация автоматического скрытия можно отключить, установив [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) переменную-член со `TRUE`.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способы настройки `CDockablePane` с использованием различных методов `CDockablePane` класса. В примере показано, как включить автоматического скрытия всех компонентов для закрепляемую панель, подпись или значок захвата, включить режим автоматического скрытия, отображение области и анимировать область, в которой находится в режиме автоматического скрытия. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
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
 Присоединяет текущую область в целевой области, создание области с вкладками.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pTabControlBarAttachTo`  
 Указывает целевой области, которая подключает текущую область. В целевой области должен быть закрепляемую панель.  
  
 [in] `dockMethod`  
 Задает метод закрепления.  
  
 [in] `bSetActive`  
 `TRUE`Чтобы активировать панель с вкладками после операции присоединения; в противном случае `FALSE`.  
  
 [выходной] `ppTabbedControlBar`  
 Содержит панель с вкладками, полученный в результате операции присоединения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущую область, если это не области с вкладками; в противном случае указатель на панель с вкладками, полученный в результате операции присоединения. Возвращает значение `NULL` Если текущей области не может быть присоединена или если возникает ошибка.  
  
### <a name="remarks"></a>Примечания  
 Когда один закрепляемую панель присоединяет к другой области, с помощью этого метода, происходит следующее.  
  
1.  Проверки инфраструктуры ли целевой области `pTabControlBarAttachTo` является обычной закрепления панели или если он является производным от [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).  
  
2.  Если панель целевой области с вкладками, среда добавит текущую область его в виде вкладки.  
  
3.  Если в целевой области регулярных закрепляемой области, платформа создает области с вкладками.  
  
    -   Платформа вызывает `pTabControlBarAttachTo->CreateTabbedPane`. Зависит от стиля новой области с вкладками `m_pTabbedControlBarRTC` член. По умолчанию, этот член класса среды выполнения имеет значение [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Если передать `AFX_CBRS_OUTLOOK_TABS` стиля как `dwTabbedStyle` параметр [CDockablePane::Create](#create) , объект класса среды выполнения задан метод класса среды выполнения [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Этот элемент можно изменить в любое время изменить стиль новой области.  
  
    -   Когда этот метод создает области с вкладками, платформа заменяет указатель `pTabControlBarAttachTo` (если области закрепленными или с плавающей запятой в multi плавающего окна) с указателем на новой области с вкладками.  
  
    -   Среда добавит `pTabControlBarAttachTo` на панель с вкладками, как первой позицией табуляции. Затем среда добавит текущую область как второй вкладки.  
  
4.  Если текущую область является производным от `CBaseTabbedPane`, все его вкладки перемещаются `pTabControlBarAttachTo` и уничтожается текущей области. Таким образом следует соблюдать осторожность при вызове этого метода, так как указатель на текущую область недопустима при возврате метода.  
  
 При присоединении одной области в другую при построении макет закрепления, задайте `dockMethod` для `DM_SHOW`.  
  
 Первая область должны закрепляться перед присоединением к нему другой области.  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 Возвращает размер прямоугольника области.  
  
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
 Объект `CSize` , содержащий размер прямоугольника области.  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 Определяет ли указанный мини-рамки можно прикреплять к области.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMiniFrame`  
 Указатель на `CPaneFrameWnd` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pMiniFrame` можно закрепить на панели; в противном случае — `FALSE`.  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 Определяет закреплением другой области для текущей области.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указывает область для прикрепления к текущей области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанной панели можно прикреплять к этой панели; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой перед панель прикрепляется к текущей области.  
  
 Переопределите эту функцию в производном классе, чтобы включить или отключить закрепление в определенной области.  
  
 По умолчанию этот метод возвращает `TRUE` при любом `pBar` или его родительский элемент находится типа `CDockablePane`.  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 Определяет ли области можно автоматического скрытия.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может автоматического скрытия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `CDockablePane::CanAutoHide`Возвращает `FALSE` ни в одном из следующих ситуаций:  
  
-   Область не имеет родителя.  
  
-   В диспетчере закрепления не допускает панелей для автоматического скрытия.  
  
-   Области не может быть закреплен.  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 Определяет закреплением текущей области в другую область.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель можно закрепить на другую панель или окно главного фрейма; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод всегда возвращает `TRUE`. Переопределите этот метод в производном классе, чтобы включить или отключить закрепление без вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 Создает и инициализирует [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта закрепляемую панель вызвать [CDockablePane::Create](#create) или [CDockablePane::CreateEx](#createex) для его создания.  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 Преобразует одного или нескольких закрепляемых областей в документы с вкладками MDI.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActiveTabOnly`  
 При преобразовании `CTabbedPane`, укажите `TRUE` для преобразования только активной вкладки. Укажите `FALSE` для преобразования всех вкладок на панели.  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 Определяет, скрыт ли закрепляемой области (также известный как режим автоматического скрытия).  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если скрыть условия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует таймер для периодической проверки, следует ли скрывать автоматически скрывать закрепляемую панель. Метод возвращает `TRUE` при области не активен, области не изменяется в размере и указатель мыши по области не.  
  
 Если предыдущие условия выполняются, платформа вызывает [CDockablePane::Slide](#slide) скрыть область.  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 Определяет, когда автоматическое скрытие закрепляемой области следует остановить со скользящим.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDirection`  
 `TRUE`Если область является видимым. `FALSE` скрытые области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`если соблюдено условие остановки. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Когда закрепляемую панель устанавливается режим автоматического скрытия, платформа использует скользящий эффекты для отображения или скрытия панели. Эта функция вызывается платформой при скользящий области. `CheckStopSlideCondition`Возвращает `TRUE` при полностью отображается область или если он полностью скрыт.  
  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательские автоматическое скрытие эффекты.  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 Копирует состояние закрепляемую панель.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOrgBar`  
 Указатель на закрепляемую панель.  
  
### <a name="remarks"></a>Примечания  
 `CDockablePane::CopyState`Копирует состояние `pOrgBar` в текущей области путем вызова следующих методов:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Создает элемент управления Windows и прикрепляет его к [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
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
 Задает размер и положение окна в клиентские координаты `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`для создания области с заголовком; в противном случае `FALSE`.  
  
 [in] `nID`  
 Указывает идентификатор дочернего окна. Это значение должно быть уникальным, если требуется сохранить состояние закрепления для этой области закрепления.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна.  
  
 [in] `dwTabbedStyle`  
 Указывает стиль окна с вкладками, которое создается, когда пользователь перетаскивает область в заголовке данной панели с вкладками.  
  
 [in] `dwControlBarStyle`  
 Задает стиль дополнительные атрибуты.  
  
 [in] [out]`pContext`  
 Указывает контекст создания окна.  
  
 [in] `lpszWindowName`  
 Задает имя окна.  
  
 [in] `sizeDefault`  
 Указывает размер окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель успешно создан; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Создает область Windows и прикрепляет его к `CDockablePane` объекта.  
  
 Если `dwStyle` имеет стиль окна `CBRS_FLOAT_MULTI` флаг плавающего окна можно число с плавающей запятой с другими областями плавающего окна. По умолчанию закрепляемых панелей можно только с плавающей запятой по отдельности.  
  
 Если `dwTabbedStyle` параметр имеет `AFX_CBRS_OUTLOOK_TABS` флаг указан области создает области с вкладками стиле Outlook, при присоединении к этой панели с помощью другой области [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод. По умолчанию закрепляемых областей создавать регулярные вкладки типа [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 Создает разделитель по умолчанию для области, как она закреплена область окна.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает сторону главного фрейма, к которому подключено области. Если `dwAlignment` содержит `CBRS_ALIGN_LEFT` или `CBRS_ALIGN_RIGHT` флаг, этот метод создает вертикальной ( `CPaneDivider::SS_VERT`) разделитель; в противном случае этот метод создает горизонтальной ( `CPaneDivider::SS_HORZ`) разделителя.  
  
 [in] `pParent`  
 Указатель родительского фрейма.  
  
 [in] `pSliderRTC`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает указатель на только что созданный разделитель или `NULL` при сбое создания разделителя.  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment`может иметь любое из следующих значений.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Область прикрепляется к верхней части клиентской области окна фрейма.|  
|`CBRS_ALIGN_BOTTOM`|Область прикрепляется к нижней части клиентской области окна фрейма.|  
|`CBRS_ALIGN_LEFT`|Панель закрепляется левого края клиентской области окна фрейма.|  
|`CBRS_ALIGN_RIGHT`|Область прикрепляется к правой части клиентской области окна фрейма.|  
  
##  <a name="createex"></a>CDockablePane::CreateEx  
 Создает элемент управления Windows и прикрепляет его к [CDockablePane](../../mfc/reference/cdockablepane-class.md) объекта.  
  
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
 Задает атрибуты расширенный стиль для нового окна.  
  
 [in] `lpszCaption`  
 Задает имя окна.  
  
 [in] [out]`pParentWnd`  
 Указывает родительского окна.  
  
 [in] `rect`  
 Задает размер и положение окна в клиентские координаты `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`для создания области с заголовком; в противном случае `FALSE`.  
  
 [in] `nID`  
 Указывает идентификатор дочернего окна. Это значение должно быть уникальным, если требуется сохранить состояние стыковки для этой области закрепления.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна.  
  
 [in] `dwTabbedStyle`  
 Указывает стиль окна с вкладками, которое создается, когда пользователь перетаскивает область в заголовке данной панели с вкладками.  
  
 [in] `dwControlBarStyle`  
 Указывает стиль дополнительные атрибуты.  
  
 [in] [out]`pContext`  
 Указывает контекст создания окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель успешно создан; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Создает область Windows и прикрепляет его к `CDockablePane` объекта.  
  
 Если `dwStyle` имеет стиль окна `CBRS_FLOAT_MULTI` флаг плавающего окна можно число с плавающей запятой с другими областями плавающего окна. По умолчанию закрепляемых панелей можно только с плавающей запятой по отдельности.  
  
 Если `dwTabbedStyle` параметр имеет `AFX_CBRS_OUTLOOK_TABS` флаг указан области создает области с вкладками стиле Outlook, при присоединении к этой панели с помощью другой области [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод. По умолчанию закрепляемых областей создавать регулярные вкладки типа [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 Создает область с вкладками в текущей области.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая область с вкладками или `NULL` при сбое операции создания.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при создании области с вкладками для замены в этой области. Дополнительные сведения см. в разделе [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
 Переопределение этого метода в производном классе, чтобы настроить как вкладки создаются и инициализируются.  
  
 Области с вкладками создается согласно информация о классе среды выполнения хранятся в `m_pTabbedControlBarRTC` член, который инициализируется [CDockablePane::CreateEx](#createex) метод.  
  
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
 Ссылка на диспетчер контейнеров для контейнера, который будет закреплен.  
  
 [in] `dwAlignment`  
 `DWORD`задающий части панели, к которому подключено контейнера.  
  
 [in] `dockMethod`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если контейнер был успешно прикреплять к области. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment`может иметь любое из следующих значений.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Контейнер прикрепляется к верхней части области.|  
|`CBRS_ALIGN_BOTTOM`|Контейнер прикрепляется к нижней части области.|  
|`CBRS_ALIGN_LEFT`|Контейнер закрепляется на левой панели.|  
|`CBRS_ALIGN_RIGHT`|Контейнер прикрепляется к правому краю области.|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 Закрепляет область с помощью структуры (standard) закрепления.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bWasDocked`  
 При возвращении метода содержит это значение `TRUE` Если области успешно закрепленной; в противном случае, он содержит `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если область была закреплена окно с вкладками или окно с вкладками был создан в результате закрепления, этот метод возвращает указатель в окно с вкладками. Если панель была в противном случае успешно закреплены, этот метод возвращает `this` указателя. Если не удалось закрепления, этот метод возвращает `NULL`.  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 Закрепляет область его сохраненную позицию закрепления.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область успешно закреплена; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Закрепляемых областей хранения последние сведения о закреплении в [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) объекта.  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 Закрепляет одну область закрепления в другую область закрепления.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pTargetWindow`  
 Указывает закрепляемую панель закрепление этой панели.  
  
 [in] `dwAlignment`  
 Указывает способ выравнивания закрепления панели. Возможно, один из CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM или CBRS_ALIGN_ANY. (Определяется в файле afxres.h).  
  
 [in] `lpRect`  
 Указывает закрепления прямоугольник для области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область была закреплена успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод, чтобы закрепить одной области в другую область с выравниванием, определяемым значением `dwAlignment`.  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 Рисует заголовок закрепляемой области (также называемый захвата).  
  
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
 Платформа вызывает этот метод для отображения заголовка закрепляемую панель.  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид заголовка.  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 Включает или отключает режим автоматического скрытия для этой панели, а также для других областей в контейнере.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить автоматическое скрытие всех возможностей закрепляемую панель; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если пользователь удерживает `Ctrl` ключ и нажмет кнопку, кнопку закрепления для переключения в режим автоматического скрытия, все остальные области, в том же контейнере область также переключаются на режим автоматического скрытия.  
  
 Вызов этого метода с `bEnable` значение `FALSE` для отключения этой функции для конкретной области.  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 Отображение или скрытие заголовка (также называемые захвата).  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для включения заголовка; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если платформа создает закрепляемых областей, они не имеют **WS_STYLE** даже в том случае, если задан стиль окна. Это означает, что панель заголовка неклиентской области, которые управляются инфраструктурой, но эта область отличается от стандартного заголовка окна.  
  
 Можно отобразить или скрыть заголовок в любое время. Платформа скрывает заголовок при добавлении области в виде вкладки окна с вкладками, или когда область перемещается в плавающем окне.  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 Задает положение панели в режиме автоматического скрытия.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CRect` , содержащий положение области, когда она находится в режиме автоматического скрытия.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 Возвращает режим автоматического скрытия слайдов для области.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `UINT` , указывающий режим автоматического скрытия слайдов для области. Возвращаемое значение может быть либо `AFX_AHSM_MOVE` или `AFX_AHSM_STRETCH`, но реализация использует только `AFX_AHSM_MOVE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 Возвращает высоту в пикселях текущего заголовка.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Высота заголовка равно 0, если заголовок был скрыт [CDockablePane::EnableGripper](#enablegripper) метода, или если области не имеет заголовка.  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 Возвращает разделитель по умолчанию для области контейнера.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Является допустимым [CPaneDivider](../../mfc/reference/cpanedivider-class.md) объекта, если закрепляемую панель прикрепляется к окну основного фрейма или `NULL` закрепляемую панель не закреплен ли он является перемещаемой.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о панели разделителей см. в разделе [CPaneDivider класса](../../mfc/reference/cpanedivider-class.md).  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 Определяет возможность закрепления панели в зависимости от расположения предоставленного указателя.  
  
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
|`CS_NOTHING`|Указатель находится не на сайте закрепления. Платформа не Закрепить панель.|  
|`CS_DOCK_IMMEDIATELY`|Указатель мыши находится на сайте закрепления в режиме интерпретации (использует области `DT_IMMEDIATE` режим закрепления). Платформа закрепляет область немедленно.|  
|`CS_DELAY_DOCK`|Указатель находится на сайте закрепления другой области закрепления или края главного фрейма. Платформа закрепляет область с задержкой. Дополнительные сведения об этом задержки см.|  
|`CS_DELAY_DOCK_TO_TAB`|Указатель мыши находится на сайте закрепления, вызывающее области быть закреплено в окно с вкладками. Это происходит, когда указатель мыши находится над заголовок другой закрепляемой области или области вкладок области с вкладками.|  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для обработки закрепления плавающей панели.  
  
 Плавающие панели инструментов и закрепляемых панелей, использующих `DT_IMMEDIATE` закрепления режим, платформа задерживает dock команду, чтобы включить пользователя перед закреплением происходит переместите окна из клиентской области родительского фрейма. Длительность задержки измеряется в миллисекундах и управляется [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) элемент данных... Значение по умолчанию [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) — 200. Это поведение эмулирует закрепления элемента [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007.  
  
 Для отложенной закрепление состояния ( `CS_DELAY_DOCK` и `CS_DELAY_DOCK_TO_TAB`), платформа не выполняет закрепления, пока пользователь отпускает кнопку мыши. Если используется панель `DT_STANDARD` закрепления режим, платформа отображает прямоугольник в проецируемых место закрепления. Если используется панель `DT_SMART` закрепления режим, платформа отображает интеллектуальных маркеров закрепления и прозрачных прямоугольников в проецируемых место закрепления. Чтобы указать режим закрепления для своей области, вызовите [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) метод. Дополнительные сведения о смарт-закрепления см. в разделе [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 Возвращает чувствительности закрепляемой области перетаскивания.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий ширину и высоту в пикселях прямоугольника с центром в точке перетаскивания. Не запущена операция перетаскивания, пока указатель мыши перемещается за пределами этого прямоугольника.  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 Получает процент пространства, которое занимает область в его контейнере ( [CPaneContainer класса](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `int` , Указывающее процент пространства, занимаемого области в его контейнера.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется, когда контейнер изменяет его макет.  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 Извлекает область вкладки области.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectTabAreaTop`  
 `GetTabArea`Если находятся в верхней части области вкладки, заполняет область вкладки этой переменной. Если вкладки расположены в нижней части панели, этой переменной заполняется пустой прямоугольник.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea`Если находятся в нижней части области вкладки, заполняет область вкладки этой переменной. Если в верхней части области вкладки, этой переменной заполняется пустой прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется только в классах, которые являются производными от `CDockablePane` и вкладок. Дополнительные сведения см. в разделе [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) и [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 Возвращает сведения о классе среды выполнения о окна с вкладками, созданный при закрепляет другой области для текущей области.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сведения о классе среды выполнения для закрепляемую панель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения сведений о классе среды выполнения для панели с вкладками, которые создаются динамически. Это может произойти, когда пользователь перетаскивает одну панель к заголовку другой области или при вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод для программного создания области с вкладками из двух закрепляемых областей.  
  
 Можно задать сведения о классе среды выполнения путем вызова [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) метод.  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 Указывает, является ли закрепляемой области можно переключить режим автоматического скрытия.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель можно переключить режим автоматического скрытия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы отключить режим автоматического скрытия для конкретных закрепляемую панель.  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 Указывает расположение панели, когда пользователь нажимает кнопку мыши.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает точки для проверки.  
  
 [in] `bDetectCaption`  
 `TRUE`Если `HTCAPTION` должны быть возвращены, если точка находится на панели заголовка; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
- `HTNOWHERE`Если `point` не находится в закрепляемую панель.  
  
- `HTCLIENT`Если `point` находится в клиентской области закрепляемую панель.  
  
- `HTCAPTION`Если `point` находится в области заголовка закрепляемую панель.  
  
- `AFX_HTCLOSE`Если `point` является "Закрыть".  
  
- `HTMAXBUTTON`Если `point` на кнопку закрепления.  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 Указывает, является ли области закрепления и другими областями в контейнере можно переключить режим автоматического скрытия.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель, а все остальные области в контейнере, можно переключить режим автоматического скрытия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Пользователь включает режим автоматического скрытия, нажав кнопку закрепления ПИН-код, удерживая при этом **Ctrl** ключ  
  
 Чтобы включить или отключить это поведение, вызовите [CDockablePane::EnableAutohideAll](#enableautohideall) метод.  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 Определяет, является ли область в режим автоматического скрытия.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель находится в режим автоматического скрытия; в противном случае `FALSE`.  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 Определяет, закреплена ли текущей области.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель не принадлежит плавающего окна, или его с плавающей запятой плавающего окна с другой областью. `FALSE`Если область является потомком плавающего окна, а не принадлежащие к плавающего окна области.  
  
### <a name="remarks"></a>Примечания  
 Чтобы определить, закреплена ли области основную область окна, вызовите [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Если метод возвращает указатель отличное от NULL, области закрепляется на фрейма главного окна.  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 Определяет поведение область, в которой находится в режим автоматического скрытия, если она видима (или скрыта) путем вызова [CDockablePane::ShowPane](#showpane).  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель должен быть скрыт в режим автоматического скрытия; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если режим автоматического скрытия закрепляемую панель, он ведет себя по-разному при вызове `ShowPane` скрытие или отображение панели. Это поведение управляется статический член [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Если данный элемент является `TRUE`, закрепляемую панель и его связанные автоматическое скрытие панели инструментов или кнопка autohide скрыто или показано при вызове `ShowPane`. В противном случае активируется или деактивируется закрепляемую панель и его связанные автоматическое скрытие панели инструментов или кнопка autohide отображается всегда.  
  
 Переопределите этот метод в производном классе, чтобы изменить поведение по умолчанию для отдельных областей.  
  
 По умолчанию для объекта `m_bHideInAutoHideMode` установлено значение `FALSE`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 Указывает, является ли область в окне фрейма несколькими областями ( [CMultiPaneFrameWnd класса](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в окне фрейма несколькими областями. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 Указывает, является ли область с раскрывающимися списками.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель можно изменять; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию закрепляемых областей с раскрывающимися списками. Чтобы предотвратить изменение размера, переопределите этот метод в производном классе и возвращают `FALSE`. Обратите внимание, что `FALSE` приводит значение к сбоя `ASSERT` в [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Используйте [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) вместо этого, чтобы закрепить панель внутри родительского фрейма.  
  
 Не может областей, которые невозможно изменить размер число с плавающей запятой, ни в режим автоматического скрытия и всегда находятся на внешней границе родительского фрейма.  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 Указывает, расположены ли вкладки в верхней или нижней части области.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если вкладки расположены в нижней части области. `FALSE` Если вкладок в верхней части области.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 Определяет, перемещается ли панель пользователем.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если перемещается области; в противном случае `FALSE`.  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 Определяет, видима ли текущей области.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если закрепляемую панель видима. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, будет ли видна закрепляемую панель. Этот метод можно использовать вместо вызова метода [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) или тестирование `WS_VISIBLE` стиля. Зависит от состояния возвращаемый видимости, включен или отключен режим автоматического скрытия и значение [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) свойство.  
  
 Если в режим автоматического скрытия закрепляемую панель и `IsHideInAutoHideMode` возвращает `FALSE` всегда имеет состояние видимости `FALSE`.  
  
 Если в режим автоматического скрытия закрепляемую панель и `IsHideInAutoHideMode` возвращает `TRUE` состояние видимости зависит от состояния видимости связанные автоматическое скрытие панели инструментов.  
  
 Если закрепляемую панель не режим автоматического скрытия, состояние видимости определяется [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) метод.  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 Указывает, отключено ли автоматическое скрытие анимация закрепляемую панель.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 Определяет поведение панели, если панель находится в режим автоматического скрытия.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение влияет на все области закрепления в приложении.  
  
 Если значение этого элемента `TRUE`, закрепляемых областей являются скрыто или показано с их связанных автоматическое скрытие панелей инструментов и кнопки, при вызове [CDockablePane::ShowPane](#showpane).  
  
 Если значение этого элемента `FALSE`, закрепляемых областей активируется или деактивируется при вызове [CDockablePane::ShowPane](#showpane).  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 Указывает скорость анимации области, когда он находится в режим автоматического скрытия.  
  
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
 Вызывается платформой при закрепляет плавающей закрепляемую панель в окне фрейма.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод не выполняет никаких действий.  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 Этот метод вызывается платформой перед изменением родительской области.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndNewParent`  
 Указатель на новый родительского окна.  
  
 [in] `bDelay`  
 `BOOL`который указывает, требуется ли отложить повторное вычисление макете закрепления, если панель закреплена. Дополнительные сведения см. в разделе [CDockablePane::UndockPane](#undockpane).  
  
### <a name="remarks"></a>Примечания  
 Если панель закреплена и новый родительский объект не допускает закрепления, этот метод открепляется области.  
  
 Если области преобразуется в документ с вкладками, этот метод сохраняет последние закрепленного положения. Платформа использует последние положение закрепления восстановить положение области, когда она преобразуется обратно в состоянии.  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 Платформа вызывает этот метод раньше областью переходов состояния с плавающей запятой.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectFloat`  
 Задает положение и размер области, когда она находится в состоянии с плавающей запятой.  
  
 [in] `dockMethod`  
 Задает метод закрепления. В разделе [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) список возможных значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть перемещается; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда область о к float. Если вы хотите выполнить обработку перед смещает области, можно переопределить этот метод в производном классе.  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 Вызывается, когда пользователь нажимает кнопки заголовка, отличный от `AFX_HTCLOSE` и `AFX_HTMAXBUTTON` кнопки.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nHit`  
 Этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Если добавить кнопку к заголовку закрепляемую панель, переопределите этот метод для получения уведомлений, когда пользователь нажимает кнопку.  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 Вызывается платформой для анимации области, когда он находится в режим автоматического скрытия.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSlideOut`  
 `TRUE`Чтобы отобразить область; `FALSE` скрыть область.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательские автоматическое скрытие эффекты.  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 Платформа вызывает этот метод при вне дока областью.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает разделитель по умолчанию `NULL` и удаляет область из его контейнера.  
  
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
 Указатель на закрепляемую панель.  
  
 [in] `dockMethod`  
 Не используется.  
  
 [in] `bRegisterWithFrame`  
 Если `TRUE`, новая область зарегистрирован в диспетчере закрепления родительского элемента области старого. Новая область вставляется по индексу старые панели в списке панелей, поддерживаемое в диспетчере закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если замена выполнена успешно; в противном случае `FALSE`.  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 При десериализации областью платформа вызывает этот метод, чтобы восстановить разделитель области по умолчанию.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>Примечания  
 Разделитель области по умолчанию восстановленной заменяет разделитель текущей области по умолчанию, если он существует.  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 Переключение области закрепления между видимым и режим автоматического скрытия.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMode`  
 `TRUE`Чтобы включить режим автоматического скрытия; `FALSE` Включение обычный режим закрепления.  
  
 [in] `dwAlignment`  
 Задает выравнивание панели автоматически скрывать, чтобы создать.  
  
 [in] [out]`pCurrAutoHideBar`  
 Указатель на панель инструментов автоматически скрывать текущего. Может быть `NULL`.  
  
 [in] `bUseTimer`  
 Указывает, следует ли использовать автоматическое скрытие эффекта при переключении области режим автоматического скрытия или скрыть область немедленно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Автоматическое скрытие инструментов, который был создан в результате переключения в режим автоматического скрытия или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда пользователь нажимает кнопку ПИН-код для закрепляемую панель или переключиться на режим автоматического скрытия в обычный режим закрепления.  
  
 Этот метод используется для переключения закрепляемую панель режим автоматического скрытия программными средствами. Области должно быть закреплено основную область окна ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) должен возвращать допустимый указатель на [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 Задает кнопки автоматического скрытия и автоматическое скрытие панели инструментов области.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pToolBar`  
 Указатель на панель инструментов автоматического скрытия.  
  
 [in] `pBtn`  
 Указатель на кнопку автоматического скрытия.  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 Задает процент пространства, которое занимает область в его контейнера.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `n`  
 `int` , Указывающее процент пространства, занимаемого области в его контейнера.  
  
### <a name="remarks"></a>Примечания  
 Платформа регулирует области, чтобы использовать новое значение при пересчете макета.  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 Задает разделитель области восстановленной по умолчанию.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hRestoredSlider`  
 Дескриптор области разделитель ("ползунок").  
  
### <a name="remarks"></a>Примечания  
 Разделитель области восстановленной по умолчанию получается при десериализации области. Дополнительные сведения см. в разделе [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).  
  
##  <a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 Задает сведения о классе среды выполнения для окна с вкладками, которое создается, когда две области закрепления друг с другом.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTC`  
 Сведения о классе среды выполнения для области с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы задать сведения о классе среды выполнения для панели с вкладками, которые создаются динамически. Это может произойти, когда пользователь перетаскивает одну панель к заголовку другой области или при вызове метода [CDockablePane::AttachToTabWnd](#attachtotabwnd) метод для программного создания области с вкладками из двух закрепляемых областей.  
  
 Класс среды выполнения по умолчанию установлено в соответствии с `dwTabbedStyle` параметр [CDockablePane::Create](#create) и [CDockablePane::CreateEx](#createex). Чтобы настроить новый панели с вкладками, класс производный от одного из следующих классов:  
  
- [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [Класс CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
- [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Затем этот метод с указателем его сведения о классе среды выполнения.  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 Показывает или скрывает панель.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 `TRUE`Чтобы отобразить область; `FALSE` скрыть область.  
  
 [in] `bDelay`  
 `TRUE`Чтобы отложить подгонки макета закрепления; `FALSE` для настройки макета закрепления немедленно.  
  
 [in] `bActivate`  
 `TRUE`Чтобы активировать область при отображении; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вместо [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) при отображении или скрытии закрепляемых областей.  
  
##  <a name="slide"></a>CDockablePane::Slide  
 Анимирует область, в которой находится в режим автоматического скрытия.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSlideOut`  
 `TRUE`Чтобы отобразить область; `FALSE` скрыть область.  
  
 [in] `bUseTimer`  
 `TRUE`Чтобы отобразить или скрыть панель с эффектом автоматически скрывать; `FALSE` для отображения или скрытия панели немедленно.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы анимировать область, в которой находится в режим автоматического скрытия.  
  
 Этот метод использует `CDockablePane::m_nSlideDefaultTimeOut` значения для определения времени ожидания для эффект скольжения. Значение по умолчанию для времени ожидания-1. Если настраивать алгоритм автоматически скрывать измените этот элемент, чтобы изменить время ожидания.  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 Переключает область между всегда видны и режима автоматического скрытия.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переключает режим автоматического скрытия области путем вызова [CDockablePane::SetAutoHideMode](#setautohidemode).  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 Открепляется области из контейнера плавающего окна или фрейма главного окна.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDelay`  
 `TRUE`Чтобы отложить вычисление макет закрепления; `FALSE` немедленно пересчитать макет закрепления.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы отменить закрепление панели, от фрейма главного окна или из контейнера multi плавающего окна (панель открывается как плавающее окно в одном плавающего окна с другими областями).  
  
 Необходимо отменить закрепление панели перед выполнением любой внешней операции, не выполняемые классом [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Например необходимо отменить закрепление панели, переместите его программными средствами из одного расположения в другое.  
  
 Платформа автоматически открепляется панелей до их удаления.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)
