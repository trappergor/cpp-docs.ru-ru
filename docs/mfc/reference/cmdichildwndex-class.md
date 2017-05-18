---
title: "Класс CMDIChildWndEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWndEx class
- ActivateFrame method
- PreTranslateMessage method
- GetThisClass method
- CreateObject method
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 016de8fdade75376f9f081539c0f160a6502bc37
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwndex-class"></a>Класс CMDIChildWndEx
`CMDIChildWndEx` Класс предоставляет функциональные возможности Windows дочернего окна многодокументного интерфейса (MDI). Он расширяет функциональные возможности [класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md). Платформа требует этот класс, если приложение MDI использует определенные классы MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|Вызывается внутренне средой Активация верхнего уровня кадра, если приложения должен быть активирован из вкладки панели задач.|  
|`CMDIChildWndEx::AddDockSite`|Этот метод не используется и не реализован.|  
|[CMDIChildWndEx::AddPane](#addpane)|Добавляет панель.|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|Добавляет область с вкладками.|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|Настройка макета закрепления.|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Указывает среде этой дочерней MDI-формы могут отображаться на вкладках панели задач Windows 7.|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|Возвращает `TRUE` Если имя дочернего окна MDI могут отображаться в [CMFCWindowsManagerDialog класса](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) диалоговое окно. В противном случае возвращает значение `FALSE`.|  
|`CMDIChildWndEx::CreateObject`|Вызывается платформой для создания динамического экземпляра данного типа класса.|  
|[CMDIChildWndEx::DockPane](#dockpane)|Закрепляет область.|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|Закрепляет одну область слева от другой области.|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|Включает автоматическое скрытие режим для области при они закрепляются в указанной границы окна.|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|Включает закрепление дочернего окна в главном фрейме.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|Включает или отключает автоматический выбор часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|Возвращает имя документа, отображаемое в дочернего окна MDI.|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|Вызывается платформой для получения значок дочернего окна MDI.|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|Вызывается платформой для получения текста для дочернего окна MDI.|  
|[CMDIChildWndEx::GetPane](#getpane)|Находит панели с помощью идентификатора указанного элемента управления.|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|Возвращает указатель на внедренные закрепляемой области, который был преобразован в документ с вкладками.|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|Возвращает вкладку окна прокси фактической регистрации с вкладки панели задач Windows 7.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Вызывается платформой, когда необходимо получить дочернего окна (обычно окно представления или разделитель) отображается эскиз вкладки панели задач Windows 7.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|Вызывается платформой, когда следует выбрать часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.|  
|`CMDIChildWndEx::GetThisClass`|Вызывается средой для получения указателя [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Вызывается платформой для получения всплывающей подсказки для кнопки панели инструментов.|  
|[CMDIChildWndEx::InsertPane](#insertpane)|Регистрация указанной области закрепления диспетчером.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|Делает недействительной значками растровое представление дочерней MDI-формы.|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайта закрепления.|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|Возвращает `TRUE` Если документ, который отображается в дочернем окне только для чтения. В противном случае возвращает значение `FALSE`.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|Возвращает значение TRUE, если успешно зарегистрирован дочерней формы MDI с вкладками панели задач Windows 7.|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|Возвращает `TRUE` наличие закрепляемой области дочернего окна MDI. В противном случае возвращает значение `FALSE`.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Указывает, может ли дочерней MDI-формы отображаются на вкладках панели задач Windows 7.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|Указывает, включен ли автоматический выбор часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Сочетание флагов, которое передается платформой метод SetTaskbarTabProperties, когда вкладка (дочерней MDI-формы) регистрируется с вкладки панели задач Windows 7. Комбинация по умолчанию является STPF_USEAPPTHUMBNAILWHENACTIVE | STPF_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|Вызывается платформой, когда необходимо получить растровое изображение для интерактивный просмотр дочерней MDI-формы.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|Вызывается платформой, когда необходимо получить точечный рисунок значками эскиза дочерней MDI-формы.|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|Вызывается платформой для перемещения окна области.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|Вызывается платформой, когда пользователь нажимает кнопку Закрыть эскизом вкладки панели задач...|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|Вызывается платформой для включения и выключения режима предварительного просмотра.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|Вызывается инфраструктурой при эскиз вкладки панели задач необходимо обработать сообщение WM_ACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|Вызывается инфраструктурой при эскиз вкладки панели задач необходимо обработать сообщение WM_MOUSEACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Вызывается платформой, когда это необходимо растянуть растровое изображение для Windows 7 панель задач вкладку эскиз дочерней MDI-формы.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Вызывается платформой для обновления название рамки. (Переопределяет `CMDIChildWnd::OnUpdateFrameTitle`.)|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|Возвращает область, содержащую заданной точки.|  
|`CMDIChildWndEx::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для перевода оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|Повторно вычисляет макет окна.|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Регистрирует дочерней формы MDI с вкладками панели задач Windows 7.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Удаление панели из диспетчера закрепления.|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|Активирует соответствующие вкладки панели задач Windows 7.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Вставляет дочерней MDI-формы до указанного окна на вкладках панели задач Windows 7.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Задает свойства для вкладки панели задач Windows 7.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|Вызывается внутренне средой для задания прямоугольник отсечения для выбора часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Удаляет дочерней MDI-формы из вкладки панели задач Windows 7.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Обновляет вкладки значок на панели задач Windows 7.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы воспользоваться преимуществами расширенных функций закрепления в приложениях MDI, создайте производный класс дочернего окна MDI приложения из `CMDIChildWndEx` вместо [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример является производным от класса `CMDIChildWndEx`. В этом фрагменте кода поступают из [образце VisualStudioDemo: приложения MFC для Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#3;](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>CMDIChildWndEx::AddPane  
 Добавляет панель.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на область.  
  
 [in] `bTail`  
 `TRUE`для добавления в конец списка областей области для закрепления manager; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области успешно зарегистрирован с диспетчером, закрепления; в противном случае — `FALSE`.  
  
##  <a name="addtabbedpane"></a>CMDIChildWndEx::AddTabbedPane  
 Добавляет область с вкладками.  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на область.  
  
##  <a name="adjustdockinglayout"></a>CMDIChildWndEx::AdjustDockingLayout  
 Настройка макета закрепления.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hdwp`  
 Дескриптор структуру позиции отложенное окна.  
  
##  <a name="canshowonmditabs"></a>CMDIChildWndEx::CanShowOnMDITabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="canshowonwindowslist"></a>CMDIChildWndEx::CanShowOnWindowsList  
 Задает отображение имя дочернего окна MDI в [CMFCWindowsManagerDialog класса](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) диалоговое окно.  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в окне могут отображаться **Windows** диалоговое окно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе и вернуть `FALSE` Если окно не будет отображаться в **Windows** диалоговое окно. Эта функция вызывается из `CMFCWindowsManagerDialog`.  
  
##  <a name="dockpane"></a>CMDIChildWndEx::DockPane  
 Закрепляет область.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область.  
  
 [in] `nDockBarID`  
 Идентификатор области.  
  
 [in] `lpRect`  
 Указатель на прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 `lpRect` Параметр не используется.  
  
##  <a name="dockpaneleftof"></a>CMDIChildWndEx::DockPaneLeftOf  
 Закрепляет одну область слева от другой области.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указатель на панели, чтобы закрепить.  
  
 `pLeftOf`  
 Указатель для области, которая служит в качестве контрольной точки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения `FALSE` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод принимает области, определяемой `pBar` и размещает его в левой области, определяемой `pLeftOf`.  
  
 Этот метод вызывается, когда нужно закрепить несколько областей в заранее определенному порядку.  
  
##  <a name="enableautohidepanes"></a>CMDIChildWndEx::EnableAutoHidePanes  
 Включает автоматическое скрытие режим для области при они закрепляются в указанной границы окна.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
 Задает стороны фрейма главного окна, в которой включено. Используйте один или несколько из следующих флагов.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
##  <a name="enabledocking"></a>CMDIChildWndEx::EnableDocking  
 Включает закрепление дочернего окна в главном фрейме.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
 Задает выравнивание закрепления для включения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для закрепления выравнивание для главного фрейма. Вы можете передать сочетание флагов CBRS_ALIGN_ (Дополнительные сведения см. в разделе [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
##  <a name="getdockingmanager"></a>CMDIChildWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdocumentname"></a>CMDIChildWndEx::GetDocumentName  
 Возвращает имя документа, отображаемое в дочернего окна MDI.  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащую имя документа.  
  
### <a name="remarks"></a>Примечания  
 Документ является отображение дочернего окна MDI. Как правило в окне отображаются данные, загруженные из или сохранить в файл. Таким образом имя документа является имя файла. Реализация по умолчанию `GetDocumentName` возвращает строки, полученной из `CDocument::GetPathName`.  
  
 При отображении окна документа, которая не загружается из файла Переопределите этот метод в производном классе и возвращают идентификатор уникального документа.  
  
 `GetDocumentName`Вызывается инфраструктурой при сохранении состояния всех открытых документов. Возвращаемая строка записывается в реестр.  
  
 Когда платформа позднее восстанавливает состояние, имя документа считывается из реестра и передается [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow). Переопределите этот метод в [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-производный класс и создать или открыть документ с таким именем и прочесть файл с таким именем. Если документ не основан на файле, создайте на основе идентификатора документа сам документ. Это следует делать вышеперечисленных действий только в том случае, если вы собираетесь сохранить и восстановить документы.  
  
### <a name="example"></a>Пример  
 В следующем примере иллюстрируется использование метода `GetDocumentName`. В этом фрагменте кода поступают из [образце VisualStudioDemo: приложения MFC для Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&17;](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>CMDIChildWndEx::GetFrameIcon  
 Вызывается платформой для получения значок дочернего окна MDI.  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна значок.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, чтобы определить, какой значок для отображения на вкладке MDI, содержащий дочернем фрейме окна интерфейса MDI.  
  
 По умолчанию этот метод возвращает значок окна. Переопределение `GetFrameIcon` в `CMDIChildWndEx`-производного класса, чтобы настроить это поведение.  
  
##  <a name="getframetext"></a>CMDIChildWndEx::GetFrameText  
 Вызывается платформой для получения текста для дочернего окна MDI.  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая текст окна фрейма.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, чтобы определить, какой текст для отображения на вкладке MDI, содержащий дочернем фрейме окна интерфейса MDI.  
  
 По умолчанию этот метод возвращает текст окна. Переопределение `GetFrameText` в `CMDIChildWndEx`-производного класса, чтобы настроить это поведение.  
  
##  <a name="getpane"></a>CMDIChildWndEx::GetPane  
 Находит панели с помощью идентификатора указанного элемента управления.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 Идентификатор элемента управления панели для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на область Если найдено, в противном случае `NULL`.  
  
##  <a name="getrelatedtabgroup"></a>CMDIChildWndEx::GetRelatedTabGroup  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettabbedpane"></a>CMDIChildWndEx::GetTabbedPane  
 Возвращает указатель на закрепляемой области, который является частью группы MDI с вкладками документов.  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на закрепляемой области, который является частью группы MDI с вкладками документов.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::GetToolbarButtonToolTipText  
 Вызывается платформой для получения всплывающей подсказки для кнопки панели инструментов.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если для отображения всплывающей подсказки. Реализация по умолчанию возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется отображать пользовательские всплывающие подсказки для кнопки панели инструментов.  
  
##  <a name="insertpane"></a>CMDIChildWndEx::InsertPane  
 Регистрация указанной области закрепления диспетчером.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на область для вставки.  
  
 [in] `pTarget`  
 Указатель на соседней панели.  
  
 [in] `bAfter`  
 Если `TRUE`, `pControlBar` вставляется после `pTarget`. Если `FALSE`, `pControlBar` вставляется перед `pTarget`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно, `FALSE` в противном случае.  
  
##  <a name="ispointneardocksite"></a>CMDIChildWndEx::IsPointNearDockSite  
 Определяет, является ли указанная точка рядом с сайта закрепления.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указанная точка.  
  
 [in] `dwBarAlignment`  
 Задает край приближается к точке. Возможные значения: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, и`CBRS_ALIGN_BOTTOM`  
  
 [in] `bOuterEdge`  
 `TRUE`Если точка находится рядом с внешней границы сайта закрепления; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если точка находится рядом с сайта закрепления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Точка расположено сайта закрепления, когда он находится в пределах чувствительности, установите в диспетчере закрепления. По умолчанию учет — 15 точек.  
  
##  <a name="isreadonly"></a>CMDIChildWndEx::IsReadOnly  
 Указывает, является ли документ, который отображается в дочернем окне только для чтения.  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если документ доступен только для чтения; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для предотвращения сохранения документов только для чтения.  
  
### <a name="example"></a>Пример  
 В следующем примере показано переопределение `IsReadOnly` метод. В этом фрагменте кода поступают из [образце VisualStudioDemo: приложения MFC для Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#2;](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>CMDIChildWndEx::IsTabbedPane  
 Указывает, содержит ли дочернего окна MDI закрепляемой области.  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если дочернего окна MDI содержит закрепляемой области, который был преобразован в документ с вкладками. в противном случае `FALSE`.  
  
##  <a name="onmoveminiframe"></a>CMDIChildWndEx::OnMoveMiniFrame  
 Вызывается платформой для перемещения окна области.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrame`  
 Указатель окна области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод завершается успешно `FALSE`.  
  
##  <a name="onsetpreviewmode"></a>CMDIChildWndEx::OnSetPreviewMode  
 Вызывается платформой для включения и выключения режима предварительного просмотра.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPreview`  
 Если `TRUE`, режим предварительного просмотра. Если `FALSE`, выход из режима предварительного просмотра.  
  
 [in] `pState`  
 Указатель на структуру состояния предварительного просмотра.  
  
##  <a name="onupdateframetitle"></a>CMDIChildWndEx::OnUpdateFrameTitle  
 Вызывается платформой для обновления название рамки.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAddToTitle`  
 Если `TRUE`, добавьте к заголовку имя документа.  
  
##  <a name="panefrompoint"></a>CMDIChildWndEx::PaneFromPoint  
 Возвращает область, содержащую заданной точки.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает точку в координатах экрана, для проверки.  
  
 [in] `nSensitivity`  
 Увеличьте область поиска, этот объем. Область удовлетворяет условиям поиска, если заданная точка находится в области повышения.  
  
 [in] `bExactBar`  
 `TRUE`Чтобы игнорировать `nSensitivity` параметр; в противном случае — `FALSE`.  
  
 [in] `pRTCBarType`  
 Если это не `NULL`, метод выполняет поиск только областей указанного типа.  
  
 [in] `dwAlignment`  
 Если область находится в указанном месте, этот параметр содержит боковой панели, ближайшей к заданной точке. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CBasePane`-производный объект, содержащий определенный момент или `NULL` Если области не был найден.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, содержит ли область указанную точку в соответствии с указанным условиям, такие как класс среды выполнения и видимость.  
  
 Если функция возвращает и область найден, `dwAlignment` содержит выравнивание заданной точке. Например, если точка находится ближайший к верхней части области `dwAlignment` равен `CBRS_ALIGN_TOP`.  
  
##  <a name="recalclayout"></a>CMDIChildWndEx::RecalcLayout  
 Повторно вычисляет макет окна.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNotify`  
 Если `TRUE`, активный элемент в месте окна получает уведомление об изменении макета.  
  
##  <a name="removepanefromdockmanager"></a>CMDIChildWndEx::RemovePaneFromDockManager  
 Удаление панели из диспетчера закрепления.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на область для удаления.  
  
 [in] `bDestroy`  
 Если `TRUE`, уничтожается области удален.  
  
 [in] `bAdjustLayout`  
 Если `TRUE`, настроить макет закрепления немедленно.  
  
 [in] `bAutoHide`  
 Если `TRUE`, макет закрепления относится к списку автоматическое скрытие панелей. Если `FALSE`, макет закрепления связан список регулярных панелей.  
  
 [in] `pBarReplacement`  
 Указатель на область, которая заменит область удален.  
  
##  <a name="setrelatedtabgroup"></a>CMDIChildWndEx::SetRelatedTabGroup  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `p`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="showpane"></a>CMDIChildWndEx::ShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="updatetaskbartabicon"></a>CMDIChildWndEx::UpdateTaskbarTabIcon  
 Обновляет вкладки значок на панели задач Windows 7.  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 Дескриптор значка для отображения на вкладке панель задач Windows 7.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="unregistertaskbartab"></a>CMDIChildWndEx::UnregisterTaskbarTab  
 Удаляет дочерней MDI-формы из вкладки панели задач Windows 7.  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bCheckRegisteredMDIChildCount`  
 Указывает, должна ли эта функция число дочерние формы MDI, зарегистрированные с вкладками MDI. Если это число равно 0, эта функция удаляет прямоугольник отсечения из эскиза панели задач приложения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 Вызывается платформой для задания прямоугольник отсечения для выбора часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Указывает новый прямоугольник отсечения. Если прямоугольник равен NULL или пуст, удаляется обрезки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbartabproperties"></a>CMDIChildWndEx::SetTaskbarTabProperties  
 Задает свойства для вкладки панели задач Windows 7.  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Сочетание значений STPFLAG. Дополнительные сведения см. в разделе [ITaskbarList4::SetTabProperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbartaborder"></a>CMDIChildWndEx::SetTaskbarTabOrder  
 Вставляет дочерней MDI-формы до указанного окна на вкладках панели задач Windows 7.  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndBefore`  
 Указатель дочернего окна MDI эскиза которого вставляется слева. Это окно уже должны быть зарегистрированы с помощью `RegisterTaskbarTab`. Если это значение равно `NULL`, эскиз нового добавляется в конец списка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbartabactive"></a>CMDIChildWndEx::SetTaskbarTabActive  
 Активирует соответствующие вкладки панели задач Windows 7.  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="registertaskbartab"></a>CMDIChildWndEx::RegisterTaskbarTab  
 Регистрирует дочерней MDI-формы вкладки панели задач Windows 7.  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndBefore`  
 Указатель дочернего окна MDI эскиза которого вставляется слева. Это окно уже должны быть зарегистрированы с помощью `RegisterTaskbarTab`. Если это значение равно `NULL`, эскиз нового добавляется в конец списка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 Вызывается платформой, когда это необходимо растянуть растровое изображение для Windows 7 панель задач вкладку эскиз дочерней MDI-формы.  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `hBmpDst`  
 Дескриптор точечного рисунка назначения.  
  
 `rectDst`  
 Указывает прямоугольник назначения.  
  
 `hBmpSrc`  
 Дескриптор исходный точечный рисунок.  
  
 `rectSrc`  
 Указывает размер исходного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Requirementher или ему ему ему ему ему ему ему **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 Вызывается инфраструктурой при эскиз вкладки панели задач должен обработать сообщение WM_MOUSEACTIVATE.  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>Параметры  
 `pDesktopWnd`  
 Задает указатель верхнего уровня родительского окна активации окна. Указатель может быть временной и не будут сохранены.  
  
 `nHitTest`  
 Код города проверки нажатия. Попадания является тест, который определяет расположение курсора.  
  
 `message`  
 Указывает номер сообщения мыши.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию активирует связанных дочернего фрейма MDI.  
  
##  <a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 Вызывается инфраструктурой при эскиз вкладки панели задач должен обработать сообщение WM_ACTIVATE.  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Параметры  
 `nState`  
 Указывает, является ли `CWnd` активируется или деактивируется.  
  
 `pWndOther`  
 Указатель на `CWnd` активируется или деактивируется. Указатель может быть `NULL`, и оно может быть временной.  
  
 `bMinimized`  
 Задает свернутое состояние `CWnd` активируется или деактивируется. Значение `TRUE` показывает окно свернуто.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию активирует связанных дочернего фрейма MDI.  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 Вызывается платформой, когда пользователь нажимает кнопку Закрыть на вкладке эскиза на панели задач.  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconicThumbnail  
 Вызывается платформой, когда необходимо получить растровое изображение для значками эскиз дочерней MDI-формы.  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Ширина растрового изображения требуется.  
  
 `nHeight`  
 Высота растрового изображения требуется.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 Вызывается платформой, когда необходимо получить растровое изображение для интерактивный просмотр дочерней MDI-формы.  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>Параметры  
 `bIsMDIChildActive`  
 Этот параметр является `TRUE` при запросе точечного рисунка для дочерней MDI-формы, которой в данный момент активная и главного окна не сворачивается. В этом случае обработки по умолчанию создание моментального снимка главного окна.  
  
 `ptLocation`  
 Указывает местоположение точечный рисунок в main (верхний уровень) клиентских координат окна. Эта точка должны предоставляться вызываемой стороной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При обработке, возвращает дескриптор точечного рисунка допустимых 32 bpp, в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе и возвращать допустимое 32 bpp растровое изображение для интерактивный просмотр дочерней MDI-формы. Этот метод вызывается только в том случае, когда дочерней MDI-формы отображаются на вкладках панели задач Windows 7. Если возвращается `NULL`, MFC вызывает обработчики по умолчанию и получает точечные рисунки с помощью `PrintClient` или `PrintWindow`.  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 Сочетание флагов, который передается платформой для `SetTaskbarTabProperties` метод, когда вкладка (дочерней MDI-формы) регистрируется с вкладки панели задач Windows 7.  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Примечания  
 Комбинация по умолчанию является STPF_USEAPPTHUMBNAILWHENACTIVE | STPF_USEAPPPEEKWHENACTIVE.  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 Указывает, включен ли автоматический выбор часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если автоматический выбор часть клиентской области окна для отображения; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Указывает, может ли дочерней MDI-формы отображаются на вкладках панели задач Windows 7.  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если дочерней MDI-формы могут отображаться на вкладки панели задач Windows 7; `FALSE` Если дочерней MDI-формы могут не отображаться на вкладки панели задач Windows 7.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 Возвращает `TRUE` Если дочерней MDI-формы успешно зарегистрирован вкладки панели задач Windows 7.  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если зарегистрировано дочерней MDI-формы с вкладки панели задач Windows 7; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::InvalidateIconicBitmaps  
 Делает недействительной значками растровое представление дочерней MDI-формы.  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `FALSE` если отключена поддержка панели задач Windows 7 или дочерней MDI-формы не зарегистрирована вкладки панели задач Windows 7; в противном случае возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Должен вызываться при изменении содержимого в реальном времени или размер дочерней MDI-формы.  
  
##  <a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 Вызывается платформой, когда следует выбрать часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Прямоугольник в координатах windows. Этот прямоугольник сопоставляется с клиентской области окна верхнего уровня. Прямоугольника должно быть пустым, чтобы очистить прямоугольник отсечения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbarPreviewWnd  
 Вызывается платформой, когда необходимо получить дочернего окна (обычно окно представления или разделитель) отображается эскиз вкладки панели задач Windows 7.  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должен возвращать допустимый указатель на `CWnd` , просмотр которого должны отображаться на вкладки панели задач Windows 7, связанные с этой дочерней MDI-формы. Реализация по умолчанию возвращает дочернее окно из этой дочерней MDI-формы с Идентификатором элемента управления AFX_IDW_PANE_FIRST (которое обычно является `CView`-производного класса).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettabproxywnd"></a>CMDIChildWndEx::GetTabProxyWnd  
 Возвращает окно прокси вкладки, зарегистрированные с помощью вкладки панели задач Windows 7.  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMDITabProxyWnd` объект, который зарегистрирован с вкладки панели задач Windows 7.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 Включает или отключает автоматический выбор часть клиентской области окна, чтобы отобразить в виде эскиза этого окна на панели задач.  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, следует ли включить ( `TRUE`), или отключить ( `FALSE`) автоматический выбор часть клиентской области окна для отображения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="canshowontaskbartabs"></a>CMDIChildWndEx::CanShowOnTaskBarTabs  
 Указывает среде этой дочерней MDI-формы могут отображаться на вкладках панели задач Windows 7.  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если содержимое дочерней MDI-формы могут отображаться на эскизы панели задач Windows 7.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе и возвращают `FALSE` отключить отображение этой дочерней MDI-формы на вкладках панели задач Windows 7.  
  
##  <a name="activatetoplevelframe"></a>CMDIChildWndEx::ActivateTopLevelFrame  
 Вызывается платформой для активации окна верхнего уровня при активации приложения из вкладки панели задач.  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd-класс](../../mfc/reference/cmdichildwnd-class.md)   
 [Класс CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)

