---
title: "Класс CMFCVisualManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCVisualManager
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManager class
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
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
ms.openlocfilehash: 7054bcd099d7e66dcbcd3e11bfef8be46b8d272d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcvisualmanager-class"></a>Класс CMFCVisualManager
Обеспечивает поддержку изменению внешнего вида приложений на глобальном уровне. Класс `CMFCVisualManager` работает совместно с классом, предоставляющим инструкции по рисованию элементов управления графического интерфейса пользователя приложения с использованием последовательного стиля. Эти другие классы называются визуальными диспетчерами и наследуются от `CMFCBaseVisualManager`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCVisualManager::CMFCVisualManager`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCVisualManager::AdjustFrames](#adjustframes)||  
|[CMFCVisualManager::AdjustToolbars](#adjusttoolbars)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](#alwayshighlight3dtabs)|Вызывается платформой для определения ли 3D вкладки всегда должен быть нарисован с помощью цвет выделения.|  
|[CMFCVisualManager::DestroyInstance](#destroyinstance)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](#dodrawheadersortarrow)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](#drawcombodropbuttonwinxp)||  
|[CMFCVisualManager::DrawPushButtonWinXP](#drawpushbuttonwinxp)||  
|[CMFCVisualManager::DrawTextOnGlass](#drawtextonglass)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](#getautohidebuttontextcolor)|Вызывается платформой для получения цвет текста для автоматического скрытия кнопки.|  
|[CMFCVisualManager::GetButtonExtraBorder](#getbuttonextraborder)|Вызывается платформой для получения размера увеличению кнопки, текущий диспетчер визуального представления для отображения кнопки.|  
|[CMFCVisualManager::GetCaptionBarTextColor](#getcaptionbartextcolor)|Вызывается платформой для получения цвет текста заголовка окна.|  
|[CMFCVisualManager::GetDockingTabsBordersSize](#getdockingtabsborderssize)|Вызывается платформой для получения размера для границы закрепленной панели с вкладками.|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](#gethighlightedmenuitemtextcolor)||  
|[CMFCVisualManager::GetInstance](#getinstance)|Возвращает указатель на `CMFCVisualManager` объект.|  
|[CMFCVisualManager::GetMDITabsBordersSize](#getmditabsborderssize)|Вызывается платформой для получения размер границы окна MDITabs.|  
|[CMFCVisualManager::GetMenuItemTextColor](#getmenuitemtextcolor)||  
|[CMFCVisualManager::GetMenuShadowDepth](#getmenushadowdepth)|Возвращает значение, определяющее ширину и высоту меню тени.|  
|[CMFCVisualManager::GetNcBtnSize](#getncbtnsize)|Вызывается платформой для определения размера кнопки системы, в зависимости от текущей диспетчер визуального представления. Система расположены кнопки в заголовке главного фрейма, сопоставляются команды **закрыть**, **свернуть**, **развернуть**, и **восстановить**.|  
|[CMFCVisualManager::GetPopupMenuBorderSize](#getpopupmenubordersize)|Вызывается платформой для получения размер границы всплывающее меню.|  
|[CMFCVisualManager::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|Вызывается платформой для получения списка свойств цвет фона.|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](#getpropertygridgrouptextcolor)|Вызывается платформой для получения списка свойств цвет текста.|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](#getribbonhyperlinktextcolor)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](#getribbonpopupbordersize)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](#getribbonquickaccesstoolbartextcolor)||  
|[CMFCVisualManager::GetRibbonSliderColors](#getribbonslidercolors)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](#getshowallmenuitemsheight)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](#getsmartdockingbaseguidecolors)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](#getsmartdockinghighlighttonecolor)||  
|[CMFCVisualManager::GetSmartDockingTheme](#getsmartdockingtheme)|Возвращает тему для отображения интеллектуальные маркеры стыковки.|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](#getstatusbarpanetextcolor)||  
|[CMFCVisualManager::GetTabFrameColors](#gettabframecolors)|Вызывается платформой для получения набора цветов для использования при отрисовке фрейма вкладки.|  
|[CMFCVisualManager::GetTabTextColor](#gettabtextcolor)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](#gettoolbarbuttontextcolor)|Вызывается платформой для получения текущего цвета текста на кнопке панели инструментов. Этот цвет различается в зависимости от текущей диспетчер визуального представления и состояние кнопки.|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](#gettoolbardisabledtextcolor)|Вызывается платформой для определения цвета текста, отображаемого на инструментов отключенных элементов.|  
|[CMFCVisualManager::GetToolbarHighlightColor](#gettoolbarhighlightcolor)||  
|[CMFCVisualManager::GetToolTipInfo](#gettooltipinfo)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|Определяет, пересекается ли автоматического скрытия кнопки.|  
|[CMFCVisualManager::IsDockingTabHasBorder](#isdockingtabhasborder)|Указывает ли текущий диспетчер визуального представления рисует границу вокруг полосы с вкладками закрепления.|  
|[CMFCVisualManager::IsEmbossDisabledImage](#isembossdisabledimage)|Указывает, следует ли Рельефная изображений отключено.|  
|[CMFCVisualManager::IsFadeInactiveImage](#isfadeinactiveimage)|Вызывается платформой для определения ли неактивных изображения на панели инструментов или меню отображаются как недоступные.|  
|[CMFCVisualManager::IsMenuFlatLook](#ismenuflatlook)|Указывает, имеют ли кнопки меню плоский вид.|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](#isofficexpstylemenus)|Определяет, реализует ли диспетчер визуального представления меню в стиле с Office XP.|  
|[CMFCVisualManager::IsOwnerDrawCaption](#isownerdrawcaption)|Определяет, реализует ли текущий диспетчер визуального представления определяемые владельцем заголовков окна фрейма.|  
|[CMFCVisualManager::IsShadowHighlightedImage](#isshadowhighlightedimage)|Указывает, имеет ли выделенное изображение тень.|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопка автоматического скрытия.|  
|[CMFCVisualManager::OnDrawBarGripper](#ondrawbargripper)|Вызывается платформой, когда он рисует границу панели элементов управления. Пользователь должен щелкнуть границу, чтобы переместить панели управления.|  
|[CMFCVisualManager::OnDrawBrowseButton](#ondrawbrowsebutton)|Вызывается инфраструктурой при отрисовке, к которой принадлежит элемент управления кнопки обзора ( [CMFCEditBrowseCtrl класса](../../mfc/reference/cmfceditbrowsectrl-class.md)).|  
|[CMFCVisualManager::OnDrawButtonBorder](#ondrawbuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопки панели инструментов.|  
|[CMFCVisualManager::OnDrawButtonSeparator](#ondrawbuttonseparator)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](#ondrawcaptionbarborder)|Вызывается инфраструктурой при отрисовке граница панели заголовка.|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](#ondrawcaptionbarbuttonborder)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](#ondrawcaptionbarinfoarea)||  
|[CMFCVisualManager::OnDrawCaptionButton](#ondrawcaptionbutton)|Вызывается инфраструктурой при отрисовке кнопки заголовка.|  
|[CMFCVisualManager::OnDrawCheckBox](#ondrawcheckbox)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](#ondrawcheckboxex)||  
|[CMFCVisualManager::OnDrawComboBorder](#ondrawcomboborder)|Вызывается инфраструктурой при отрисовке границы кнопки, поля со списком.|  
|[CMFCVisualManager::OnDrawComboDropButton](#ondrawcombodropbutton)|Вызывается инфраструктурой при отрисовке кнопки раскрывающегося поля со списком.|  
|[CMFCVisualManager::OnDrawControlBorder](#ondrawcontrolborder)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](#ondrawdefaultribbonimage)|Вызывается инфраструктурой при отрисовке изображение ленты по умолчанию.|  
|[CMFCVisualManager::OnDrawEditBorder](#ondraweditborder)|Вызывается инфраструктурой при отрисовке границы вокруг [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объекта.|  
|[CMFCVisualManager::OnDrawExpandingBox](#ondrawexpandingbox)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](#ondrawfloatingtoolbarborder)|Вызывается инфраструктурой при отрисовке границы плавающей панели инструментов. Плавающая панель инструментов — это панель, который отображается в виде окна области.|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](#ondrawheaderctrlborder)|Вызывается платформой, когда он рисует границу, которая содержит заголовок элемента управления.|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](#ondrawheaderctrlsortarrow)|Вызывается инфраструктурой при отрисовке стрелку сортировки заголовок элемента управления.|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](#ondrawmenuarrowoncustomizelist)||  
|[CMFCVisualManager::OnDrawMenuBorder](#ondrawmenuborder)|Вызывается инфраструктурой при отрисовке границы меню.|  
|[CMFCVisualManager::OnDrawMenuCheck](#ondrawmenucheck)||  
|[CMFCVisualManager::OnDrawMenuItemButton](#ondrawmenuitembutton)||  
|[CMFCVisualManager::OnDrawMenuLabel](#ondrawmenulabel)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](#ondrawmenuresizebar)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](#ondrawmenuscrollbutton)|Вызывается инфраструктурой при отрисовке меню кнопки прокрутки.|  
|[CMFCVisualManager::OnDrawMenuShadow](#ondrawmenushadow)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](#ondrawmenusystembutton)|Вызывается инфраструктурой при отрисовке системных клавиш меню **закрыть**, **свернуть**, **развернуть**, и **восстановить**.|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](#ondrawminiframeborder)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](#ondrawoutlookbarsplitter)|Вызывается инфраструктурой при отрисовке разделитель для панели Outlook. Разделителем является горизонтальной панели используются для группировки элементов управления.|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](#ondrawoutlookpagebuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопки страницы Outlook. Если область панели Outlook содержит несколько кнопок, чем может быть отображено, появляются кнопки страницы Outlook.|  
|[CMFCVisualManager::OnDrawPaneBorder](#ondrawpaneborder)|Вызывается инфраструктурой при отрисовке границы [CPane класса](../../mfc/reference/cpane-class.md).|  
|[CMFCVisualManager::OnDrawPaneCaption](#ondrawpanecaption)|Вызывается инфраструктурой при отрисовке заголовка `CPane`.|  
|[CMFCVisualManager::OnDrawPaneDivider](#ondrawpanedivider)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](#ondrawpopupwindowborder)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](#ondrawpopupwindowbuttonborder)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](#ondrawpopupwindowcaption)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](#ondrawribbonapplicationbutton)|Вызывается инфраструктурой при отрисовке **главной кнопки** на ленте.|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](#ondrawribbonbuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопки на ленте.|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](#ondrawribbonbuttonsgroup)|Вызывается инфраструктурой при отрисовке группу кнопки на ленте.|  
|[CMFCVisualManager::OnDrawRibbonCaption](#ondrawribboncaption)|Вызывается инфраструктурой при отрисовке заголовка главного фрейма, но только в том случае, если лента интегрирован с кадром.|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](#ondrawribboncaptionbutton)|Вызывается инфраструктурой при отрисовке заголовка, расположенную на ленте.|  
|[CMFCVisualManager::OnDrawRibbonCategory](#ondrawribboncategory)|Вызывается инфраструктурой при отрисовке категория ленты.|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](#ondrawribboncategorycaption)|Вызывается инфраструктурой при отрисовке заголовка категории ленты.|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](#ondrawribboncategoryscroll)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](#ondrawribboncategorytab)|Вызывается инфраструктурой при отрисовке вкладку категория ленты.|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](#ondrawribboncheckboxonlist)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](#ondrawribboncolorpalettebox)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](#ondrawribbondefaultpanebuttoncontext)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](#ondrawribbondefaultpanebutton)|Вызывается инфраструктурой при отрисовке по умолчанию кнопка панели ленты. По умолчанию кнопка появляется, если пользователь сжимает панель ленты, чтобы он был слишком мало для отображения элементов ленты. Вместо этого отображается кнопка по умолчанию и элементы ленты будут добавлены как элементы в раскрывающемся меню.|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](#ondrawribbondefaultpanebuttonindicator)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](#ondrawribbongalleryborder)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](#ondrawribbongallerybutton)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](#ondrawribbonkeytip)||  
|[CMFCVisualManager::OnDrawRibbonLabel](#ondrawribbonlabel)|Вызывается инфраструктурой при отрисовке метку ленты.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](#ondrawribbonmainpanelbuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопки на ленте, расположенный на **Main** панель. **Main** панель — панель, которая отображается, когда пользователь щелкает **кнопку Main**.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](#ondrawribbonmainpanelframe)|Вызывается инфраструктурой при отрисовке рамку вокруг **Main** панель.|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](#ondrawribbonmenucheckframe)||  
|[CMFCVisualManager::OnDrawRibbonPanel](#ondrawribbonpanel)|Вызывается инфраструктурой при отрисовке панели ленты.|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](#ondrawribbonpanelcaption)|Вызывается инфраструктурой при отрисовке заголовка панели ленты.|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](#ondrawribbonprogressbar)|Вызывается инфраструктурой при отрисовке [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) объекта.|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](#ondrawribbonquickaccesstoolbarseparator)|Вызывается инфраструктурой при отрисовке разделителя на ленте **быстрого доступа**.|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](#ondrawribbonrecentfilesframe)|Вызывается инфраструктурой при отрисовке рамку вокруг список последних файлов.|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](#ondrawribbonsliderchannel)|Вызывается инфраструктурой при отрисовке канала [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) объекта.|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](#ondrawribbonsliderthumb)|Вызывается инфраструктурой при отрисовке ползунка `CMFCRibbonSlider` объекта.|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](#ondrawribbonsliderzoombutton)|Вызывается инфраструктурой при отрисовке кнопки масштаба `CMFCRibbonSlider` объекта.|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](#ondrawribbonstatusbarpane)|Вызывается инфраструктурой при отрисовке панели строки состояния ленты.|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](#ondrawribbontabsframe)|Вызывается инфраструктурой при отрисовке рамку вокруг набора вкладок на ленте.|  
|[CMFCVisualManager::OnDrawScrollButtons](#ondrawscrollbuttons)||  
|[CMFCVisualManager::OnDrawSeparator](#ondrawseparator)|Вызывается инфраструктурой при отрисовке разделителя. Разделителя обычно используется для разделения групп значков на панели управления.|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](#ondrawshowallmenuitems)||  
|[CMFCVisualManager::OnDrawSpinButtons](#ondrawspinbuttons)|Вызывается инфраструктурой при отрисовке кнопками счетчика.|  
|[CMFCVisualManager::OnDrawSplitterBorder](#ondrawsplitterborder)|Вызывается инфраструктурой при отрисовке границы окна разделителя.|  
|[CMFCVisualManager::OnDrawSplitterBox](#ondrawsplitterbox)|Вызывается инфраструктурой при отрисовке поле перетащите разделитель для разбиения окна.|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](#ondrawstatusbarpaneborder)|Вызывается инфраструктурой при отрисовке границы для панели строки состояния.|  
|[CMFCVisualManager::OnDrawStatusBarProgress](#ondrawstatusbarprogress)|Вызывается инфраструктурой при отрисовке строки состояния индикатора хода выполнения.|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](#ondrawstatusbarsizebox)|Вызывается инфраструктурой при отрисовке поле размер строки состояния.|  
|[CMFCVisualManager::OnDrawTab](#ondrawtab)|Вызывается инфраструктурой при отрисовке [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) объекта.|  
|[CMFCVisualManager::OnDrawTabCloseButton](#ondrawtabclosebutton)|Вызывается инфраструктурой при отрисовке **закрыть** кнопку на активной вкладке.|  
|[CMFCVisualManager::OnDrawTabContent](#ondrawtabcontent)|Вызывается инфраструктурой при отрисовке внутреннюю вкладку (изображений, текстовых сообщений).|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](#ondrawtabsbuttonborder)|Вызывается инфраструктурой при отрисовке границы кнопки вкладки.|  
|[CMFCVisualManager::OnDrawTask](#ondrawtask)|Вызывается инфраструктурой при отрисовке задачи на панели задач.|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](#ondrawtasksgroupareaborder)|Вызывается инфраструктурой при рисует границу вокруг области группы на панели задач.|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](#ondrawtasksgroupcaption)|Вызывается инфраструктурой при отрисовке заголовка для группы задач в области задач.|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](#ondrawtasksgroupicon)||  
|[CMFCVisualManager::OnDrawTearOffCaption](#ondrawtearoffcaption)|Вызывается инфраструктурой при отрисовке заголовка перемещаемые перемещаемые панели.|  
|[CMFCVisualManager::OnDrawToolBoxFrame](#ondrawtoolboxframe)||  
|[CMFCVisualManager::OnEraseMDIClientArea](#onerasemdiclientarea)|Вызывается платформой, когда она удаляет клиентской области MDI.|  
|[CMFCVisualManager::OnErasePopupWindowButton](#onerasepopupwindowbutton)||  
|[CMFCVisualManager::OnEraseTabsArea](#onerasetabsarea)|Вызывается платформой, когда она удаляет область вкладки в окне вкладку.|  
|[CMFCVisualManager::OnEraseTabsButton](#onerasetabsbutton)|Вызывается платформой, когда она удаляет значок и текст кнопки вкладки.|  
|[CMFCVisualManager::OnEraseTabsFrame](#onerasetabsframe)|Вызывается платформой, когда она удаляет вкладку кадра.|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|Вызывается платформой, когда он заполняет фон кнопка автоматического скрытия.|  
|[CMFCVisualManager::OnFillBarBackground](#onfillbarbackground)|Вызывается платформой, когда он заполняет фон панели элементов управления.|  
|[CMFCVisualManager::OnFillButtonInterior](#onfillbuttoninterior)|Вызывается платформой после его заполнения фона кнопки панели инструментов.|  
|[CMFCVisualManager::OnFillCaptionBarButton](#onfillcaptionbarbutton)||  
|[CMFCVisualManager::OnFillCommandsListBackground](#onfillcommandslistbackground)|Вызывается платформой после его заполнения фона кнопки панели инструментов, к которой принадлежит список команд, который в свою очередь, является частью диалогового окна настройки.|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](#onfillheaderctrlbackground)|Вызывается платформой, когда он заполняет фон элемента управления заголовка.|  
|[CMFCVisualManager::OnFillMiniFrameCaption](#onfillminiframecaption)|Вызывается платформой, когда он заполняется заголовок окна мини-кадра.|  
|[CMFCVisualManager::OnFillOutlookBarCaption](#onfilloutlookbarcaption)|Вызывается платформой, когда он заполняет фон заголовка панели Outlook.|  
|[CMFCVisualManager::OnFillOutlookPageButton](#onfilloutlookpagebutton)|Вызывается платформой, когда он заполняет внутреннюю часть страницы кнопка Outlook.|  
|[CMFCVisualManager::OnFillPopupWindowBackground](#onfillpopupwindowbackground)|Вызывается платформой, когда он заполняет фон всплывающего окна.|  
|[CMFCVisualManager::OnFillRibbonButton](#onfillribbonbutton)|Вызывается платформой, когда он заполняет внутреннюю часть кнопки на ленте.|  
|[CMFCVisualManager::OnFillRibbonEdit](#onfillribbonedit)|Вызывается платформой, когда он заполняет внутреннюю часть элемента управления для редактирования на ленте.|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](#onfillribbonmainpanelbutton)|Вызывается платформой, когда он заполняет внутреннюю часть кнопки ленты, расположенной на **Main** панель.|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](#onfillribbonmenuframe)|Вызывается платформой, когда он заполняет рамки панель ленты главного меню.|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](#onfillribbonquickaccesstoolbarpopup)||  
|[CMFCVisualManager::OnFillSplitterBackground](#onfillsplitterbackground)|Вызывается платформой, когда он заполняет фон окна разделителя.|  
|[CMFCVisualManager::OnFillTab](#onfilltab)|Вызывается платформой, когда он заполняет фон вкладки.|  
|[CMFCVisualManager::OnFillTasksGroupInterior](#onfilltasksgroupinterior)|Вызывается платформой, когда он заполняет внутреннюю часть [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) объект [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md).|  
|[CMFCVisualManager::OnFillTasksPaneBackground](#onfilltaskspanebackground)|Вызывается платформой, когда он заполняет фон `CMFCTasksPane` элемента управления.|  
|[CMFCVisualManager::OnHighlightMenuItem](#onhighlightmenuitem)|Вызывается инфраструктурой при отрисовке выделенные меню.|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](#onhighlightrarelyusedmenuitems)|Вызывается при отрисовке выделенные framework и редко используемые меню.|  
|[CMFCVisualManager::OnNcPaint](#onncpaint)|Вызывается инфраструктурой при отрисовке неклиентской области.|  
|[CMFCVisualManager::OnSetWindowRegion](#onsetwindowregion)|Вызывается платформой, когда он задает область, содержащую фреймы и всплывающих меню.|  
|[CMFCVisualManager::OnUpdateSystemColors](#onupdatesystemcolors)|Вызывается инфраструктурой при его изменении цвета параметр системы.|  
|[CMFCVisualManager::RedrawAll](#redrawall)|Перерисовывает всех панелей элементов управления в приложении.|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](#ribboncategorycolortorgb)||  
|[CMFCVisualManager::SetDefaultManager](#setdefaultmanager)|Задает диспетчер visual по умолчанию.|  
|[CMFCVisualManager::SetEmbossDisabledImage](#setembossdisabledimage)|Включает или отключает выступающая режим для изображений отключено панели инструментов.|  
|[CMFCVisualManager::SetFadeInactiveImage](#setfadeinactiveimage)|Включает или отключает эффект освещения для неактивных изображения в меню или панели инструментов.|  
|[CMFCVisualManager::SetMenuFlatLook](#setmenuflatlook)|Задает флаг, указывающий, имеют ли кнопки меню приложений плоский вид.|  
|[CMFCVisualManager::SetMenuShadowDepth](#setmenushadowdepth)|Задает ширину и высоту меню тени.|  
|[CMFCVisualManager::SetShadowHighlightedImage](#setshadowhighlightedimage)|Задает флаг, указывающий на необходимость отображения тени при отрисовке выделенного изображения.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку `CMFCVisualManager` класс элементов управления графического интерфейса пользователя приложения, каждое приложение может иметь либо одного экземпляра `CMFCVisualManager`, или один экземпляр класса, производного от `CMFCVisualManager`. Приложение также может функционировать без `CMFCVisualManager`. Используйте статический метод `GetInstance` для получения указателя на текущий `CMFCVisualManager`-производный объект.  
  
 Чтобы изменить внешний вид приложения необходимо использовать другие классы, которые предоставляют методы для рисования всех визуальных элементов приложения. Примеры этих классов: [класс преобразованный CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md), [класс преобразованный CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md), и [преобразованный CMFCVisualManagerOffice2007 класса](../../mfc/reference/cmfcvisualmanageroffice2007-class.md). Если вы хотите изменить внешний вид приложения, передать один из этих диспетчеров визуального представления в метод `SetDefaultManager`. Пример, демонстрирующий, как приложение может имитировать внешний вид Microsoft Office 2003 см. в разделе [преобразованный CMFCVisualManagerOffice2003 класса](../../mfc/reference/cmfcvisualmanageroffice2003-class.md).  
  
 Все методы рисования являются виртуальными. Это позволяет создать пользовательский визуальный стиль для графического пользовательского интерфейса приложения. Если вы хотите создать собственные визуальный стиль, создайте класс, производный от одного из классов диспетчер визуального представления и переопределить методы рисования, которые требуется изменить.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как создать экземпляр стандартных и пользовательских `CMFCVisualManager` объектов.  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
    if (CMFCVisualManager::GetInstance () != NULL)  
 {  
    delete CMFCVisualManager::GetInstance ();

 }  
    switch (iIndex)  
 {  
    case 0:  
    CMFCVisualManager::GetInstance ();

// create the standard visual manager  
    break; 
    case 1:  
    new CMyVisualManager ();

// create the first custom visual manager  
    break; 
    case 2:  
    new CMacStyle ();
*// create the second custom visual manager  
    break; 
 }  
 *// access the manager and set it properly  
    CMFCVisualManager::GetInstance ()->SetLook2000 ();
CMFCVisualManager::GetInstance ()->RedrawAll ();

}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется извлечение значения по умолчанию `CMFCVisualManager` объекта. Этот фрагмент кода является частью [пример панели задач](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TasksPane&#1;](../../mfc/reference/codesnippet/cpp/cmfcvisualmanager-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 `CMFCVisualManager`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxvisualmanager.h  
  
##  <a name="a-nameadjustframesa--cmfcvisualmanageradjustframes"></a><a name="adjustframes"></a>CMFCVisualManager::AdjustFrames  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall AdjustFrames();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameadjusttoolbarsa--cmfcvisualmanageradjusttoolbars"></a><a name="adjusttoolbars"></a>CMFCVisualManager::AdjustToolbars  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall AdjustToolbars();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namealwayshighlight3dtabsa--cmfcvisualmanageralwayshighlight3dtabs"></a><a name="alwayshighlight3dtabs"></a>CMFCVisualManager::AlwaysHighlight3DTabs  
 Платформа вызывает этот метод для определения ли 3D вкладки всегда должны быть выделены в приложении.  
  
```  
virtual BOOL AlwaysHighlight3DTabs() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если 3D вкладки должны быть выделены.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию в производном диспетчер визуального представления и возврата `TRUE` Если 3D вкладки всегда должны быть выделены. Реализация по умолчанию этот метод возвращает `FALSE`.  
  
##  <a name="a-namecmfcvisualmanagera--cmfcvisualmanagercmfcvisualmanager"></a><a name="cmfcvisualmanager"></a>CMFCVisualManager::CMFCVisualManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCVisualManager(BOOL bTemporary = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bTemporary`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedestroyinstancea--cmfcvisualmanagerdestroyinstance"></a><a name="destroyinstance"></a>CMFCVisualManager::DestroyInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall DestroyInstance(BOOL bAutoDestroyOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoDestroyOnly`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedodrawheadersortarrowa--cmfcvisualmanagerdodrawheadersortarrow"></a><a name="dodrawheadersortarrow"></a>CMFCVisualManager::DoDrawHeaderSortArrow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void DoDrawHeaderSortArrow(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsUp,  
    BOOL bDlgCtrl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsUp`  
 [in] `bDlgCtrl`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawcomboborderwinxpa--cmfcvisualmanagerdrawcomboborderwinxp"></a><a name="drawcomboborderwinxp"></a>CMFCVisualManager::DrawComboBorderWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboBorderWinXP(CDC*,
    CRect,
    BOOL,
    BOOL,
    BOOL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
 [in] `CRect`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawcombodropbuttonwinxpa--cmfcvisualmanagerdrawcombodropbuttonwinxp"></a><a name="drawcombodropbuttonwinxp"></a>CMFCVisualManager::DrawComboDropButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawComboDropButtonWinXP(CDC*,
    CRect,
    BOOL,
    BOOL,
    BOOL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
 [in] `CRect`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawpushbuttonwinxpa--cmfcvisualmanagerdrawpushbuttonwinxp"></a><a name="drawpushbuttonwinxp"></a>CMFCVisualManager::DrawPushButtonWinXP  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawPushButtonWinXP(CDC*,
    CRect,
    CMFCButton*,
    UINT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDC*`  
 [in] `CRect`  
 [in] `CMFCButton*`  
 [in] `UINT`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namedrawtextonglassa--cmfcvisualmanagerdrawtextonglass"></a><a name="drawtextonglass"></a>CMFCVisualManager::DrawTextOnGlass  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DrawTextOnGlass(
    CDC* pDC,  
    CString strText,  
    CRect rect,  
    DWORD dwFlags,  
    int nGlowSize = 0,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `strText`  
 [in] `rect`  
 [in] `dwFlags`  
 [in] `nGlowSize`  
 [in] `clrText`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenabletoolbarbuttonfilla--cmfcvisualmanagerenabletoolbarbuttonfill"></a><a name="enabletoolbarbuttonfill"></a>CMFCVisualManager::EnableToolbarButtonFill  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableToolbarButtonFill(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetautohidebuttontextcolora--cmfcvisualmanagergetautohidebuttontextcolor"></a><a name="getautohidebuttontextcolor"></a>CMFCVisualManager::GetAutoHideButtonTextColor  
 Платформа вызывает этот метод для извлечения цвет текста кнопка автоматического скрытия.  
  
```  
virtual COLORREF GetAutoHideButtonTextColor(CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель кнопка автоматического скрытия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, определяющий цвет текста `pButton`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить цвет текста кнопки Автоскрытие в приложении. Чтобы сделать это, возвращают цвет, который требуется приложением для использования в качестве цвета текста.  
  
##  <a name="a-namegetbuttonextrabordera--cmfcvisualmanagergetbuttonextraborder"></a><a name="getbuttonextraborder"></a>CMFCVisualManager::GetButtonExtraBorder  
 Платформа вызывает этот метод при отрисовке кнопки панели инструментов.  
  
```  
virtual CSize GetButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий нужный размер границы для кнопок панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Некоторые обложки нужно расширить границы кнопки панели инструментов. Переопределите этот метод в пользовательский диспетчер визуального представления расширить границы кнопки панели инструментов в приложении. Реализация по умолчанию этот метод возвращает пустой размер.  
  
##  <a name="a-namegetcaptionbartextcolora--cmfcvisualmanagergetcaptionbartextcolor"></a><a name="getcaptionbartextcolor"></a>CMFCVisualManager::GetCaptionBarTextColor  
 Платформа вызывает этот метод для извлечения цвет текста в строке заголовка.  
  
```  
virtual COLORREF GetCaptionBarTextColor(CMFCCaptionBar* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на строку заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет текста в `pBar`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить цвет текста для заголовка окна. В переопределенный метод возвращает нужный цвет.  
  
##  <a name="a-namegetcaptionbuttonextrabordera--cmfcvisualmanagergetcaptionbuttonextraborder"></a><a name="getcaptionbuttonextraborder"></a>CMFCVisualManager::GetCaptionButtonExtraBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCaptionButtonExtraBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetdockingpanecaptionextraheighta--cmfcvisualmanagergetdockingpanecaptionextraheight"></a><a name="getdockingpanecaptionextraheight"></a>CMFCVisualManager::GetDockingPaneCaptionExtraHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetDockingPaneCaptionExtraHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetdockingtabsborderssizea--cmfcvisualmanagergetdockingtabsborderssize"></a><a name="getdockingtabsborderssize"></a>CMFCVisualManager::GetDockingTabsBordersSize  
 Платформа вызывает этот метод при отрисовке область, в которой будет закреплено и с вкладками.  
  
```  
virtual int GetDockingTabsBordersSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, указывающее размер границы области, который закреплен с вкладками.  
  
### <a name="remarks"></a>Примечания  
 Закрепленной панели становится вкладок, когда пользователь размещает несколько областей, в то же расположение в приложении.  
  
 Переопределите этот метод в пользовательский диспетчер визуального представления для изменения размера границы полос закрепленного элемента управления вкладками. Реализация по умолчанию возвращает значение -1.  
  
##  <a name="a-namegethighlightedmenuitemtextcolora--cmfcvisualmanagergethighlightedmenuitemtextcolor"></a><a name="gethighlightedmenuitemtextcolor"></a>CMFCVisualManager::GetHighlightedMenuItemTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetHighlightedMenuItemTextColor(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetinstancea--cmfcvisualmanagergetinstance"></a><a name="getinstance"></a>CMFCVisualManager::GetInstance  
 Возвращает указатель на текущий [CMFCVisualManager класс](../../mfc/reference/cmfcvisualmanager-class.md) объекта для приложения.  
  
```  
static CMFCVisualManager* GetInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CMFCVisualManager`.  
  
### <a name="remarks"></a>Примечания  
 Приложение может иметь только один `CMFCVisualManager` объект, связанный с ним. Это включает в себя объект, производный от `CMFCVisualManager` класса. Этот метод возвращает указатель на связанный `CMFCVisualManager` объекта. Если приложение не имеет соответствующего `CMFCVisualManager` объекта, этот метод будет создать и связать ее с приложением.  
  
##  <a name="a-namegetmditabsborderssizea--cmfcvisualmanagergetmditabsborderssize"></a><a name="getmditabsborderssize"></a>CMFCVisualManager::GetMDITabsBordersSize  
 Платформа вызывает этот метод, чтобы определить размер границы окна MDITabs перед его рисует окна.  
  
```  
virtual int GetMDITabsBordersSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер границы окна MDITabs.  
  
### <a name="remarks"></a>Примечания  
 Эта функция в производном классе, чтобы настроить размер границы окна MDITabs переопределяется.  
  
##  <a name="a-namegetmenuimagemargina--cmfcvisualmanagergetmenuimagemargin"></a><a name="getmenuimagemargin"></a>CMFCVisualManager::GetMenuImageMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetMenuImageMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetmenuitemtextcolora--cmfcvisualmanagergetmenuitemtextcolor"></a><a name="getmenuitemtextcolor"></a>CMFCVisualManager::GetMenuItemTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetMenuItemTextColor(
    CMFCToolBarMenuButton* pButton,  
    BOOL bHighlighted,  
    BOOL bDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 [in] `bHighlighted`  
 [in] `bDisabled`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetmenushadowdeptha--cmfcvisualmanagergetmenushadowdepth"></a><a name="getmenushadowdepth"></a>CMFCVisualManager::GetMenuShadowDepth  
 Получает ширину и высоту меню тени.  
  
```  
int GetMenuShadowDepth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина и Высота меню тени в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Ширина и Высота меню тени эквивалентны. Значение по умолчанию — 7 пикселей.  
  
##  <a name="a-namegetncbtnsizea--cmfcvisualmanagergetncbtnsize"></a><a name="getncbtnsize"></a>CMFCVisualManager::GetNcBtnSize  
 Вызывается платформой, когда требуется получить размер кнопок системы.  
  
```  
virtual CSize GetNcBtnSize(BOOL bSmall) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSmall`  
 Логический параметр, указывающий ли `GetNcBtnSize` должен получить размер кнопки крупных или мелких системы. Если `bSmall` — `TRUE`, `GetNcBtnSize` возвращает размер кнопки небольшой системы. В противном случае — возвращает размер кнопки большой системы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) параметр, указывающий размер кнопок системы.  
  
### <a name="remarks"></a>Примечания  
 Система расположены кнопки в заголовке окна фрейма, сопоставляются команды **закрыть**, **свернуть**, **развернуть**, и **восстановить**. Размер этих кнопок зависит текущий диспетчер визуального представления. Переопределите этот метод, если вы хотите настроить размер кнопок системы в приложении.  
  
##  <a name="a-namegetpopupmenubordersizea--cmfcvisualmanagergetpopupmenubordersize"></a><a name="getpopupmenubordersize"></a>CMFCVisualManager::GetPopupMenuBorderSize  
 Платформа вызывает этот метод, чтобы получить размер границы всплывающих меню.  
  
```  
virtual int GetPopupMenuBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, указывающее размер границы всплывающих меню.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы изменить размер границы всплывающих меню в приложении.  
  
##  <a name="a-namegetpopupmenugapa--cmfcvisualmanagergetpopupmenugap"></a><a name="getpopupmenugap"></a>CMFCVisualManager::GetPopupMenuGap  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetPopupMenuGap() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetpropertygridgroupcolora--cmfcvisualmanagergetpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a>CMFCVisualManager::GetPropertyGridGroupColor  
 Платформа вызывает этот метод для получения списка свойств цвет фона.  
  
```  
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPropList`  
 Указатель на список свойств, который рисует платформы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет фона `pPropList`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить цвет фона списка свойств в приложении.  
  
##  <a name="a-namegetpropertygridgrouptextcolora--cmfcvisualmanagergetpropertygridgrouptextcolor"></a><a name="getpropertygridgrouptextcolor"></a>CMFCVisualManager::GetPropertyGridGroupTextColor  
 Платформа вызывает этот метод, чтобы получить список свойств цвет текста.  
  
```  
virtual COLORREF GetPropertyGridGroupTextColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pPropList`  
 Указатель на список свойств.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет текста списка свойств.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить цвет текста список свойств в приложении.  
  
##  <a name="a-namegetribbonhyperlinktextcolora--cmfcvisualmanagergetribbonhyperlinktextcolor"></a><a name="getribbonhyperlinktextcolor"></a>CMFCVisualManager::GetRibbonHyperlinkTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetRibbonHyperlinkTextColor(CMFCRibbonLinkCtrl* pHyperLink);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pHyperLink`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonpopupbordersizea--cmfcvisualmanagergetribbonpopupbordersize"></a><a name="getribbonpopupbordersize"></a>CMFCVisualManager::GetRibbonPopupBorderSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetRibbonPopupBorderSize(const CMFCRibbonPanelMenu*) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CMFCRibbonPanelMenu*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonquickaccesstoolbarchevronoffseta--cmfcvisualmanagergetribbonquickaccesstoolbarchevronoffset"></a><a name="getribbonquickaccesstoolbarchevronoffset"></a>CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetRibbonQuickAccessToolBarChevronOffset();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonquickaccesstoolbarrightmargina--cmfcvisualmanagergetribbonquickaccesstoolbarrightmargin"></a><a name="getribbonquickaccesstoolbarrightmargin"></a>CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetRibbonQuickAccessToolBarRightMargin();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonquickaccesstoolbartextcolora--cmfcvisualmanagergetribbonquickaccesstoolbartextcolor"></a><a name="getribbonquickaccesstoolbartextcolor"></a>CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetRibbonQuickAccessToolBarTextColor(BOOL bDisabled = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDisabled`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonslidercolorsa--cmfcvisualmanagergetribbonslidercolors"></a><a name="getribbonslidercolors"></a>CMFCVisualManager::GetRibbonSliderColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetRibbonSliderColors(
    CMFCRibbonSlider* pSlider,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled,  
    COLORREF& clrLine,  
    COLORREF& clrFill);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pSlider`  
 [in] `bIsHighlighted`  
 [in] `bIsPressed`  
 [in] `bIsDisabled`  
 [in] `clrLine`  
 [in] `clrFill`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetribbonstatusbartextcolora--cmfcvisualmanagergetribbonstatusbartextcolor"></a><a name="getribbonstatusbartextcolor"></a>CMFCVisualManager::GetRibbonStatusBarTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetRibbonStatusBarTextColor(CMFCRibbonStatusBar* pStatusBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pStatusBar`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetshowallmenuitemsheighta--cmfcvisualmanagergetshowallmenuitemsheight"></a><a name="getshowallmenuitemsheight"></a>CMFCVisualManager::GetShowAllMenuItemsHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetShowAllMenuItemsHeight(
    CDC* pDC,  
    const CSize& sizeDefault);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `sizeDefault`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetsmartdockingbaseguidecolorsa--cmfcvisualmanagergetsmartdockingbaseguidecolors"></a><a name="getsmartdockingbaseguidecolors"></a>CMFCVisualManager::GetSmartDockingBaseGuideColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void GetSmartDockingBaseGuideColors(
    COLORREF& clrBaseGroupBackground,  
    COLORREF& clrBaseGroupBorder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrBaseGroupBackground`  
 [in] `clrBaseGroupBorder`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetsmartdockinghighlighttonecolora--cmfcvisualmanagergetsmartdockinghighlighttonecolor"></a><a name="getsmartdockinghighlighttonecolor"></a>CMFCVisualManager::GetSmartDockingHighlightToneColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetSmartDockingHighlightToneColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetsmartdockingthemea--cmfcvisualmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CMFCVisualManager::GetSmartDockingTheme  
 Возвращает тему для отображения интеллектуальные маркеры стыковки.  
  
```  
virtual AFX_SMARTDOCK_THEME GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает одно из следующих значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetstatusbarpanetextcolora--cmfcvisualmanagergetstatusbarpanetextcolor"></a><a name="getstatusbarpanetextcolor"></a>CMFCVisualManager::GetStatusBarPaneTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetStatusBarPaneTextColor(
    CMFCStatusBar* pStatusBar,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pStatusBar`  
 [in] `pPane`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabframecolorsa--cmfcvisualmanagergettabframecolors"></a><a name="gettabframecolors"></a>CMFCVisualManager::GetTabFrameColors  
 Платформа вызывает эту функцию, когда требуется получить набор цветов для рисования вкладки окна.  
  
```  
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF& clrDark,  
    COLORREF& clrBlack,  
    COLORREF& clrHighlight,  
    COLORREF& clrFace,  
    COLORREF& clrDarkShadow,  
    COLORREF& clrLight,  
    CBrush*& pbrFace,  
    CBrush*& pbrBlack);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTabWnd`  
 Указатель окна с вкладками, где кадр рисует вкладки.  
  
 [выходной] `clrDark`  
 Ссылку на [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, где этот метод сохраняет цвет Темная вкладки.  
  
 [выходной] `clrBlack`  
 Ссылку на `COLORREF` параметр, где этот метод сохраняет цвет для границы окна вкладки. Цвет границы по умолчанию является black.  
  
 [выходной] `clrHighlight`  
 Ссылку на `COLORREF` параметр, где этот метод сохраняет цвет для выделения состояние окна вкладки.  
  
 [выходной] `clrFace`  
 Ссылку на `COLORREF` параметр, где этот метод сохраняет цвет шрифта вкладка окна.  
  
 [выходной] `clrDarkShadow`  
 Ссылку на `COLORREF` параметр, где этот метод сохраняет цвет тени окно вкладки.  
  
 [выходной] `clrLight`  
 Ссылку на `COLORREF` параметр, где этот метод сохраняет цвет света края окна вкладки.  
  
 [выходной] `pbrFace`  
 Указатель на ссылку в качестве кисти. Этот метод сохраняет кисть, которая используется для заливки поверхности вкладку окна в этом параметре.  
  
 [выходной] `pbrBlack`  
 Указатель на ссылку в качестве кисти. Этот метод сохраняет кисти, используемые для заполнения черные края окна вкладки в этом параметре.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию в производном классе, если требуется настроить набор цветов, инфраструктура использует при отрисовке окно вкладки.  
  
##  <a name="a-namegettabhorzmargina--cmfcvisualmanagergettabhorzmargin"></a><a name="gettabhorzmargin"></a>CMFCVisualManager::GetTabHorzMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetTabHorzMargin(const CMFCBaseTabCtrl*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CMFCBaseTabCtrl*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettabtextcolora--cmfcvisualmanagergettabtextcolor"></a><a name="gettabtextcolor"></a>CMFCVisualManager::GetTabTextColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetTabTextColor(
    const CMFCBaseTabCtrl*,
    int,
    BOOL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CMFCBaseTabCtrl*`  
 [in] `int`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanegroupcaptionheighta--cmfcvisualmanagergettaskspanegroupcaptionheight"></a><a name="gettaskspanegroupcaptionheight"></a>CMFCVisualManager::GetTasksPaneGroupCaptionHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneGroupCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanegroupcaptionhorzoffseta--cmfcvisualmanagergettaskspanegroupcaptionhorzoffset"></a><a name="gettaskspanegroupcaptionhorzoffset"></a>CMFCVisualManager::GetTasksPaneGroupCaptionHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneGroupCaptionHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanegroupcaptionvertoffseta--cmfcvisualmanagergettaskspanegroupcaptionvertoffset"></a><a name="gettaskspanegroupcaptionvertoffset"></a>CMFCVisualManager::GetTasksPaneGroupCaptionVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneGroupCaptionVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanegroupvertoffseta--cmfcvisualmanagergettaskspanegroupvertoffset"></a><a name="gettaskspanegroupvertoffset"></a>CMFCVisualManager::GetTasksPaneGroupVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneGroupVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanehorzmargina--cmfcvisualmanagergettaskspanehorzmargin"></a><a name="gettaskspanehorzmargin"></a>CMFCVisualManager::GetTasksPaneHorzMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneHorzMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspaneiconhorzoffseta--cmfcvisualmanagergettaskspaneiconhorzoffset"></a><a name="gettaskspaneiconhorzoffset"></a>CMFCVisualManager::GetTasksPaneIconHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneIconHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspaneiconvertoffseta--cmfcvisualmanagergettaskspaneiconvertoffset"></a><a name="gettaskspaneiconvertoffset"></a>CMFCVisualManager::GetTasksPaneIconVertOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneIconVertOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanetaskhorzoffseta--cmfcvisualmanagergettaskspanetaskhorzoffset"></a><a name="gettaskspanetaskhorzoffset"></a>CMFCVisualManager::GetTasksPaneTaskHorzOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneTaskHorzOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettaskspanevertmargina--cmfcvisualmanagergettaskspanevertmargin"></a><a name="gettaskspanevertmargin"></a>CMFCVisualManager::GetTasksPaneVertMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTasksPaneVertMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettoolbarbuttontextcolora--cmfcvisualmanagergettoolbarbuttontextcolor"></a><a name="gettoolbarbuttontextcolor"></a>CMFCVisualManager::GetToolbarButtonTextColor  
 Платформа вызывает этот метод, чтобы определить цвет текста кнопки панели инструментов.  
  
```  
virtual COLORREF GetToolbarButtonTextColor(
    CMFCToolBarButton* pButton,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку панели инструментов.  
  
 [in] `state`  
 Состояние кнопки панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текста `pButton` когда она имеет состояние, определяется `state`.  
  
### <a name="remarks"></a>Примечания  
 Цвет текста [CMFCToolBarButton класс](../../mfc/reference/cmfctoolbarbutton-class.md) объекта зависит от состояния кнопки. Возможные состояния кнопки панели инструментов: `ButtonsIsRegular`, `ButtonsIsPressed`, или `ButtonsIsHighlighted`.  
  
 Переопределите эту функцию, чтобы настроить цвет текста кнопки панели инструментов в приложении.  
  
##  <a name="a-namegettoolbarcustomizebuttonmargina--cmfcvisualmanagergettoolbarcustomizebuttonmargin"></a><a name="gettoolbarcustomizebuttonmargin"></a>CMFCVisualManager::GetToolBarCustomizeButtonMargin  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetToolBarCustomizeButtonMargin() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettoolbardisabledcolora--cmfcvisualmanagergettoolbardisabledcolor"></a><a name="gettoolbardisabledcolor"></a>CMFCVisualManager::GetToolbarDisabledColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetToolbarDisabledColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettoolbardisabledtextcolora--cmfcvisualmanagergettoolbardisabledtextcolor"></a><a name="gettoolbardisabledtextcolor"></a>CMFCVisualManager::GetToolbarDisabledTextColor  
 Платформа вызывает эту функцию, чтобы определить цвет текста кнопки панели инструментов, недоступны.  
  
```  
virtual COLORREF GetToolbarDisabledTextColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, который использует платформу для цвет текста кнопки панели инструментов, недоступны.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в пользовательский диспетчер visual, чтобы задать цвет текста кнопки панели инструментов, недоступны.  
  
##  <a name="a-namegettoolbarhighlightcolora--cmfcvisualmanagergettoolbarhighlightcolor"></a><a name="gettoolbarhighlightcolor"></a>CMFCVisualManager::GetToolbarHighlightColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF GetToolbarHighlightColor();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettooltipinfoa--cmfcvisualmanagergettooltipinfo"></a><a name="gettooltipinfo"></a>CMFCVisualManager::GetToolTipInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetToolTipInfo(
    CMFCToolTipInfo& params,  
    UINT nType = (UINT)(-1));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `params`  
 [in] `nType`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehasoverlappedautohidebuttonsa--cmfcvisualmanagerhasoverlappedautohidebuttons"></a><a name="hasoverlappedautohidebuttons"></a>CMFCVisualManager::HasOverlappedAutoHideButtons  
 Возвращает, пересекается ли автоматического скрытия кнопки в текущий диспетчер визуального представления.  
  
```  
virtual BOOL HasOverlappedAutoHideButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если автоматическое скрытие кнопки пересекаются; `FALSE` при их отсутствии.  
  
##  <a name="a-nameisautodestroya--cmfcvisualmanagerisautodestroy"></a><a name="isautodestroy"></a>CMFCVisualManager::IsAutoDestroy  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdefaultwinxppopupbuttona--cmfcvisualmanagerisdefaultwinxppopupbutton"></a><a name="isdefaultwinxppopupbutton"></a>CMFCVisualManager::IsDefaultWinXPPopupButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultWinXPPopupButton(CMFCDesktopAlertWndButton*) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CMFCDesktopAlertWndButton*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisdockingtabhasbordera--cmfcvisualmanagerisdockingtabhasborder"></a><a name="isdockingtabhasborder"></a>CMFCVisualManager::IsDockingTabHasBorder  
 Возвращает ли текущий диспетчер визуального представления Рисование границы вокруг области, которые будут закреплены и с вкладками.  
  
```  
virtual BOOL IsDockingTabHasBorder();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если диспетчер визуального представления Рисование границы вокруг области, которые будут закреплены и с вкладками; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Закрепленной панели становятся вкладок, когда несколько областей, прикрепленные к той же папке.  
  
##  <a name="a-nameisembossdisabledimagea--cmfcvisualmanagerisembossdisabledimage"></a><a name="isembossdisabledimage"></a>CMFCVisualManager::IsEmbossDisabledImage  
 Указывает, embosses ли платформа образы, которые будут недоступны.  
  
```  
BOOL IsEmbossDisabledImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если платформа embosses образы, которые недоступны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом [CMFCToolBarImages::Draw](../../mfc/reference/cmfctoolbarimages-class.md#draw) при рисовании изображения на панели инструментов, который недоступен.  
  
##  <a name="a-nameisfadeinactiveimagea--cmfcvisualmanagerisfadeinactiveimage"></a><a name="isfadeinactiveimage"></a>CMFCVisualManager::IsFadeInactiveImage  
 Платформа вызывает этот метод при отрисовке неактивные изображения на панели инструментов или меню.  
  
```  
BOOL IsFadeInactiveImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если платформа использует эффект освещения при отрисовке неактивные изображения на панели инструментов или в меню; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить эффект освещения, вызвав [CMFCVisualManager::SetFadeInactiveImage](#setfadeinactiveimage). Действует освещения делает недоступным изображение, которое выглядит яркое.  
  
##  <a name="a-nameisframemenucheckeditemsa--cmfcvisualmanagerisframemenucheckeditems"></a><a name="isframemenucheckeditems"></a>CMFCVisualManager::IsFrameMenuCheckedItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFrameMenuCheckedItems() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameishighlightonenotetabsa--cmfcvisualmanagerishighlightonenotetabs"></a><a name="ishighlightonenotetabs"></a>CMFCVisualManager::IsHighlightOneNoteTabs  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsHighlightOneNoteTabs() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameishighlightwholemenuitema--cmfcvisualmanagerishighlightwholemenuitem"></a><a name="ishighlightwholemenuitem"></a>CMFCVisualManager::IsHighlightWholeMenuItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsHighlightWholeMenuItem();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameislayeredribbonkeytipa--cmfcvisualmanagerislayeredribbonkeytip"></a><a name="islayeredribbonkeytip"></a>CMFCVisualManager::IsLayeredRibbonKeyTip  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsLayeredRibbonKeyTip() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameismenuflatlooka--cmfcvisualmanagerismenuflatlook"></a><a name="ismenuflatlook"></a>CMFCVisualManager::IsMenuFlatLook  
 Указывает, отображаются ли кнопки меню плоскими.  
  
```  
BOOL IsMenuFlatLook() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопки меню отображается плоской; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию меню кнопки не отображаются плоскими. Используйте [CMFCVisualManager::SetMenuFlatLook](#setmenuflatlook) метод, чтобы изменить это поведение. Если меню кнопки отображаются плоскими, они не изменяют внешний вид при нажатии на них.  
  
##  <a name="a-nameisofficexpstylemenusa--cmfcvisualmanagerisofficexpstylemenus"></a><a name="isofficexpstylemenus"></a>CMFCVisualManager::IsOfficeXPStyleMenus  
 Показывает, реализует ли диспетчер визуального представления меню в стиле с Office XP.  
  
```  
virtual BOOL IsOfficeXPStyleMenus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диспетчер визуального представления отображает меню в стиле Microsoft Office XP. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md) вызывает этот метод, когда требуется нарисовать меню и тени. По умолчанию этот метод возвращает `FALSE`. Если вы хотите использовать всплывающие меню аналогично всплывающих меню в Office XP, переопределите этот метод в пользовательский диспетчер визуального представления и возвращают `TRUE`.  
  
##  <a name="a-nameisoffsetpressedbuttona--cmfcvisualmanagerisoffsetpressedbutton"></a><a name="isoffsetpressedbutton"></a>CMFCVisualManager::IsOffsetPressedButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsOffsetPressedButton() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisownerdrawcaptiona--cmfcvisualmanagerisownerdrawcaption"></a><a name="isownerdrawcaption"></a>CMFCVisualManager::IsOwnerDrawCaption  
 Показывает, реализует ли текущий диспетчер визуального представления определяемые владельцем заголовков.  
  
```  
virtual BOOL IsOwnerDrawCaption();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если все окна фрейма в приложении имеют рисование владельцем подписи; `FALSE` в противном случае.  
  
##  <a name="a-nameisownerdrawmenuchecka--cmfcvisualmanagerisownerdrawmenucheck"></a><a name="isownerdrawmenucheck"></a>CMFCVisualManager::IsOwnerDrawMenuCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsOwnerDrawMenuCheck();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisshadowhighlightedimagea--cmfcvisualmanagerisshadowhighlightedimage"></a><a name="isshadowhighlightedimage"></a>CMFCVisualManager::IsShadowHighlightedImage  
 Указывает, отображает ли диспетчер визуального представления тени, при подготовке к просмотру выделенного изображения.  
  
```  
BOOL IsShadowHighlightedImage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, когда диспетчер визуального представления отображает тени под выделенным изображений. в противном случае — 0.  
  
##  <a name="a-nameistoolbarbuttonfillenableda--cmfcvisualmanageristoolbarbuttonfillenabled"></a><a name="istoolbarbuttonfillenabled"></a>CMFCVisualManager::IsToolbarButtonFillEnabled  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsToolbarButtonFillEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameistoolbarroundshapea--cmfcvisualmanageristoolbarroundshape"></a><a name="istoolbarroundshape"></a>CMFCVisualManager::IsToolbarRoundShape  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsToolbarRoundShape(CMFCToolBar*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CMFCToolBar*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameiswindowsthemingsupporteda--cmfcvisualmanageriswindowsthemingsupported"></a><a name="iswindowsthemingsupported"></a>CMFCVisualManager::IsWindowsThemingSupported  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsWindowsThemingSupported() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonactivateappa--cmfcvisualmanageronactivateapp"></a><a name="onactivateapp"></a>CMFCVisualManager::OnActivateApp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnActivateApp(
    CWnd* pWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 [in] `bActive`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawautohidebuttonbordera--cmfcvisualmanagerondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a>CMFCVisualManager::OnDrawAutoHideButtonBorder  
 Этот метод вызывается платформой при рисовании границ кнопки автоматического скрытия.  
  
```  
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectBounds`  
 Размер и расположение кнопка автоматического скрытия.  
  
 [in] `rectBorderSize`  
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) параметр, содержащий размер границы.  
  
 [in] `pButton`  
 Указатель кнопка автоматического скрытия. Платформа рисует границу для этой кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если требуется настроить внешний вид границы кнопка автоматического скрытия. По умолчанию этот метод заполняет плоской границы с цвет тени по умолчанию для вашего приложения.  
  
 `rectBorderSize` Параметр не содержит координаты границы. Он содержит размер границы в `top`, `bottom`, `left`, и `right` данные-члены. Значение меньше или равно 0 указывает на этой стороне кнопка автоматического скрытия без границы.  
  
##  <a name="a-nameondrawbargrippera--cmfcvisualmanagerondrawbargripper"></a><a name="ondrawbargripper"></a>CMFCVisualManager::OnDrawBarGripper  
 Вызывается инфраструктурой при отрисовке захвата для панели элементов управления.  
  
```  
virtual void OnDrawBarGripper(
    CDC* pDC,  
    CRect rectGripper,  
    BOOL bHorz,  
    CBasePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели элементов управления.  
  
 [in] `rectGripper`  
 Ограничивающий прямоугольник для панели управления.  
  
 [in] `bHorz`  
 Логический параметр, указывает ли панель закреплена горизонтально или вертикально.  
  
 [in] `pBar`  
 Указатель на панели управления. Диспетчер визуального представления рисует границу этой панели элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод отображает стандартные захвата. Чтобы настроить внешний вид захвата, переопределите этот метод в пользовательский класс, производный от `CMFCVisualManager` класса.  
  
##  <a name="a-nameondrawbrowsebuttona--cmfcvisualmanagerondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCVisualManager::OnDrawBrowseButton  
 Платформа вызывает этот метод, когда он рисует кнопку для элемента управления.  
  
```  
virtual BOOL OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    CMFCEditBrowseCtrl* pEdit,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки "Обзор".  
  
 [in] `pEdit`  
 Указатель на элемент управления редактированием. Диспетчер визуального представления Рисует кнопку для этого элемента управления редактированием.  
  
 [in] `state`  
 Значение перечисления, указывающее состояние кнопки.  
  
 [выходной] `clrText`  
 Ссылку на [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр. Это зарезервированное значение и в настоящее время не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию в производном классе, если требуется настроить внешний вид кнопки Обзор в экземплярах [CMFCEditBrowseCtrl класса](../../mfc/reference/cmfceditbrowsectrl-class.md). Возможные значения для состояния кнопки `ButtonsIsRegular`, `ButtonsIsPressed`, и `ButtonsIsHighlighted`.  
  
##  <a name="a-nameondrawbuttonbordera--cmfcvisualmanagerondrawbuttonborder"></a><a name="ondrawbuttonborder"></a>CMFCVisualManager::OnDrawButtonBorder  
 Платформа вызывает этот метод при отрисовке границы кнопки панели инструментов.  
  
```  
virtual void OnDrawButtonBorder(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства кнопки панели инструментов.  
  
 [in] `pButton`  
 Указатель на кнопку панели инструментов. Платформа рисует границу этой кнопки.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки панели инструментов.  
  
 [in] `state`  
 Тип перечислимых данных, который указывает текущее состояние кнопки панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод отображает Стандартная граница. Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить внешний вид границы кнопки панели инструментов.  
  
 Возможные состояния кнопки панели инструментов: `ButtonsIsRegular`, `ButtonsIsPressed`, или `ButtonsIsHighlighted`.  
  
##  <a name="a-nameondrawbuttonseparatora--cmfcvisualmanagerondrawbuttonseparator"></a><a name="ondrawbuttonseparator"></a>CMFCVisualManager::OnDrawButtonSeparator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawButtonSeparator(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `state`  
 [in] `bHorz`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawcaptionbarbordera--cmfcvisualmanagerondrawcaptionbarborder"></a><a name="ondrawcaptionbarborder"></a>CMFCVisualManager::OnDrawCaptionBarBorder  
 Платформа вызывает этот метод, когда он рисует границу [CMFCCaptionBar класс](../../mfc/reference/cmfccaptionbar-class.md) объекта.  
  
```  
virtual void OnDrawCaptionBarBorder(
    CDC* pDC,  
    CMFCCaptionBar* pBar,  
    CRect rect,  
    COLORREF clrBarBorder,  
    BOOL bFlatBorder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на объект `CMFCCaptionBar`. Платформа рисует этот заголовок.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы заголовка окна.  
  
 [in] `clrBarBorder`  
 Цвет границы.  
  
 [in] `bFlatBorder`  
 Логический параметр, который указывает, имеет ли граница плоской, двумерный вид.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид границы заголовка окна.  
  
##  <a name="a-nameondrawcaptionbarbuttonbordera--cmfcvisualmanagerondrawcaptionbarbuttonborder"></a><a name="ondrawcaptionbarbuttonborder"></a>CMFCVisualManager::OnDrawCaptionBarButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionBarButtonBorder(
    CDC* pDC,  
    CMFCCaptionBar* pBar,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted,  
    BOOL bIsDisabled,  
    BOOL bHasDropDownArrow,  
    BOOL bIsSysButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rect`  
 [in] `bIsPressed`  
 [in] `bIsHighlighted`  
 [in] `bIsDisabled`  
 [in] `bHasDropDownArrow`  
 [in] `bIsSysButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawcaptionbarinfoareaa--cmfcvisualmanagerondrawcaptionbarinfoarea"></a><a name="ondrawcaptionbarinfoarea"></a>CMFCVisualManager::OnDrawCaptionBarInfoArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCaptionBarInfoArea(
    CDC* pDC,  
    CMFCCaptionBar* pBar,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawcaptionbuttona--cmfcvisualmanagerondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a>CMFCVisualManager::OnDrawCaptionButton  
 Платформа вызывает этот метод при отрисовке [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md) объекта.  
  
```  
virtual void OnDrawCaptionButton (
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на объект `CMFCCaptionButton`. Платформа рисует этой кнопки заголовка.  
  
 [in] `bActive`  
 Логический параметр, который указывает, включен ли кнопки.  
  
 [in] `bHorz`  
 Логический параметр, который указывает, является ли заголовок горизонтальной.  
  
 [in] `bMaximized`  
 Логический параметр, указывающее, развернуто ли в родительской области.  
  
 [in] `bDisabled`  
 Логический параметр, который указывает, отключено ли кнопки заголовка.  
  
 [in] `nImageID`  
 Индекс изображения значка для кнопки. Если `nImageID` равно -1, этот метод использует индекс образа записываются в `pButton`.  
  
### <a name="remarks"></a>Примечания  
 Реализация этого метода по умолчанию отображается маленькая кнопка с глобального экземпляра `CMenuImages` класса. Кнопки, перечислены в файле заголовка для `CMenuImages`. Some examples include `CMenuImages::IdClose`, `CMenuImages::IdArowLeft`, `CMenuImages::IdArowRight`, `CMenuImages::IdArowDown`, `CMenuImages::IdArowUp`, and `CMenuImages::IdPinHorz`.  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид кнопки заголовка.  
  
##  <a name="a-nameondrawcheckboxa--cmfcvisualmanagerondrawcheckbox"></a><a name="ondrawcheckbox"></a>CMFCVisualManager::OnDrawCheckBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCheckBox(
    CDC* pDC,  
    CRect rect,  
    BOOL bHighlighted,  
    BOOL bChecked,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `bHighlighted`  
 [in] `bChecked`  
 [in] `bEnabled`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawcheckboxexa--cmfcvisualmanagerondrawcheckboxex"></a><a name="ondrawcheckboxex"></a>CMFCVisualManager::OnDrawCheckBoxEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawCheckBoxEx(
    CDC* pDC,  
    CRect rect,  
    int nState,  
    BOOL bHighlighted,  
    BOOL bPressed,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `nState`  
 [in] `bHighlighted`  
 [in] `bPressed`  
 [in] `bEnabled`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawcombobordera--cmfcvisualmanagerondrawcomboborder"></a><a name="ondrawcomboborder"></a>CMFCVisualManager::OnDrawComboBorder  
 Платформа вызывает этот метод, когда он рисовал границу вокруг экземпляра [CMFCToolBarComboBoxButton класса](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
```  
virtual void OnDrawComboBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства, кнопки поля со списком.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки, поля со списком.  
  
 [in] `bDisabled`  
 Логический параметр, который указывает, является ли кнопки со списком недоступны.  
  
 [in] `bIsDropped`  
 Логический параметр, указывающий, удаляется ли поле со списком.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли кнопки поля со списком.  
  
 [in] `pButton`  
 Указатель на объект `CMFCToolBarComboBoxButton`. Платформа рисует этой кнопки поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном visual диспетчера настроить внешний вид границы поле со списком.  
  
##  <a name="a-nameondrawcombodropbuttona--cmfcvisualmanagerondrawcombodropbutton"></a><a name="ondrawcombodropbutton"></a>CMFCVisualManager::OnDrawComboDropButton  
 Платформа вызывает этот метод, когда он рисует кнопку раскрывающегося [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
```  
virtual void OnDrawComboDropButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsDropped,  
    BOOL bIsHighlighted,  
    CMFCToolBarComboBoxButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки «drop».  
  
 [in] `bDisabled`  
 Логический параметр, указывает ли кнопка «drop» недоступна.  
  
 [in] `bIsDropped`  
 Логический параметр, указывающий, удаляется ли поле со списком.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли кнопка удаления.  
  
 [in] `pButton`  
 Указатель на объект `CMFCToolBarComboBoxButton`. Платформа Рисует кнопку удаления для этой кнопки поля со списком.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном visual диспетчера настройки внешнего вида кнопки раскрывающегося кнопки поля со списком.  
  
##  <a name="a-nameondrawcontrolbordera--cmfcvisualmanagerondrawcontrolborder"></a><a name="ondrawcontrolborder"></a>CMFCVisualManager::OnDrawControlBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawControlBorder(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndCtrl`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawdefaultribbonimagea--cmfcvisualmanagerondrawdefaultribbonimage"></a><a name="ondrawdefaultribbonimage"></a>CMFCVisualManager::OnDrawDefaultRibbonImage  
 Платформа вызывает этот метод при отрисовке изображение по умолчанию, используемый для кнопки ленты.  
  
```  
virtual void OnDrawDefaultRibbonImage(
    CDC* pDC,  
    CRect rectImage,  
    BOOL bIsDisabled = FALSE,  
    BOOL bIsPressed = FALSE,  
    BOOL bIsHighlighted = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectImage`  
 Прямоугольник, который определяет границы изображения по умолчанию.  
  
 [in] `bIsDisabled`  
 Логический параметр, который указывает, является ли кнопка ленты недоступен.  
  
 [in] `bIsPressed`  
 Логический параметр, указывающий, является ли нажата кнопка ленты.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли кнопка ленты.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите настроить образ, который используется для кнопки ленты, переопределите этот метод в производном диспетчер визуального представления.  
  
##  <a name="a-nameondraweditbordera--cmfcvisualmanagerondraweditborder"></a><a name="ondraweditborder"></a>CMFCVisualManager::OnDrawEditBorder  
 Платформа вызывает этот метод, когда он рисовал границу вокруг экземпляра [CMFCToolBarEditBoxButton класса](../../mfc/reference/cmfctoolbareditboxbutton-class.md).  
  
```  
virtual void OnDrawEditBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bDisabled,  
    BOOL bIsHighlighted,  
    CMFCToolBarEditBoxButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы `CMFCToolBarEditBoxButton` объекта.  
  
 [in] `bDisabled`  
 Логический параметр, указывающий, является ли эта кнопка будет недоступна.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли кнопки.  
  
 [in] `pButton`  
 Указатель на объект `CMFCToolBarEditBoxButton`. Платформа рисует границу этой кнопки поле редактирования.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки границы `CMFCToolBarEditBoxButton` объекта.  
  
##  <a name="a-nameondrawexpandingboxa--cmfcvisualmanagerondrawexpandingbox"></a><a name="ondrawexpandingbox"></a>CMFCVisualManager::OnDrawExpandingBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawExpandingBox(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsOpened,  
    COLORREF colorBox);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `bIsOpened`  
 [in] `colorBox`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawfloatingtoolbarbordera--cmfcvisualmanagerondrawfloatingtoolbarborder"></a><a name="ondrawfloatingtoolbarborder"></a>CMFCVisualManager::OnDrawFloatingToolbarBorder  
 Платформа вызывает этот метод, когда он рисует границу плавающей панели инструментов.  
  
```  
virtual void OnDrawFloatingToolbarBorder(
    CDC* pDC,  
    CMFCBaseToolBar* pToolBar,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pToolBar`  
 Указатель на плавающей панели инструментов.  
  
 [in] `rectBorder`  
 Прямоугольник, который определяет границы плавающей панели инструментов.  
  
 [in] `rectBorderSize`  
 Прямоугольник, который определяет размер границы панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Плавающая панель инструментов — это панель, который отображается в виде окна области. Как правило это происходит, когда пользователь перетаскивает панели инструментов, чтобы он больше не закреплен.  
  
 Задаваемый размер границы соответствующего параметра в `rectBorderSize`. Например, Ширина верхней границы панели инструментов определяется `rectBorderSize.top`.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида границы плавающей панели инструментов.  
  
##  <a name="a-nameondrawheaderctrlbordera--cmfcvisualmanagerondrawheaderctrlborder"></a><a name="ondrawheaderctrlborder"></a>CMFCVisualManager::OnDrawHeaderCtrlBorder  
 Платформа вызывает этот метод, когда он рисовал границу вокруг экземпляра [CMFCHeaderCtrl класса](../../mfc/reference/cmfcheaderctrl-class.md).  
  
```  
virtual void OnDrawHeaderCtrlBorder(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCtrl`  
 Указатель на объект `CMFCHeaderCtrl`. Платформа рисует границу заголовка элемента управления.  
  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который задает границы элемента управления заголовка.  
  
 [in] `bIsPressed`  
 Логический параметр, указывающий, нажата ли заголовок элемента управления.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли заголовок элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки границы элемента управления заголовка.  
  
##  <a name="a-nameondrawheaderctrlsortarrowa--cmfcvisualmanagerondrawheaderctrlsortarrow"></a><a name="ondrawheaderctrlsortarrow"></a>CMFCVisualManager::OnDrawHeaderCtrlSortArrow  
 Платформа вызывает эту функцию при отрисовке стрелку сортировки элемента управления заголовка.  
  
```  
virtual void OnDrawHeaderCtrlSortArrow(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect& rect,  
    BOOL bIsUp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCtrl`  
 Указатель на элемент управления заголовка. Диспетчер визуального представления Рисует стрелку сортировки этого [CMFCHeaderCtrl класс](../../mfc/reference/cmfcheaderctrl-class.md) объекта.  
  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы стрелку сортировки.  
  
 [in] `bIsUp`  
 Логическое значение, указывающее направление сортировки стрелки.  
  
### <a name="remarks"></a>Примечания  
 Если `bIsUp` — `TRUE`, диспетчер визуального представления рисует сортировки со стрелкой вверх. Если это `FALSE`, диспетчер визуального представления Рисует стрелку сортировки. Переопределение `OnDrawHeaderCtrlSortArrow` в производном классе, чтобы настроить внешний вид кнопки сортировки.  
  
##  <a name="a-nameondrawmenuarrowoncustomizelista--cmfcvisualmanagerondrawmenuarrowoncustomizelist"></a><a name="ondrawmenuarrowoncustomizelist"></a>CMFCVisualManager::OnDrawMenuArrowOnCustomizeList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuArrowOnCustomizeList(
    CDC* pDC,  
    CRect rectCommand,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rectCommand`  
 [in] `bSelected`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenubordera--cmfcvisualmanagerondrawmenuborder"></a><a name="ondrawmenuborder"></a>CMFCVisualManager::OnDrawMenuBorder  
 Платформа вызывает этот метод, когда он рисует границу [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md).  
  
```  
virtual void OnDrawMenuBorder(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для `CMFCPopupMenu` объекта.  
  
 [in] `pMenu`  
 Указатель на объект `CMFCPopupMenu`. Платформа рисует границу вокруг это всплывающее меню.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы всплывающее меню.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод отображает границы стандартное меню. Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить внешний вид границы меню.  
  
##  <a name="a-nameondrawmenuchecka--cmfcvisualmanagerondrawmenucheck"></a><a name="ondrawmenucheck"></a>CMFCVisualManager::OnDrawMenuCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuCheck(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rect,  
    BOOL bHighlight,  
    BOOL bIsRadio);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `bHighlight`  
 [in] `bIsRadio`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenuitembuttona--cmfcvisualmanagerondrawmenuitembutton"></a><a name="ondrawmenuitembutton"></a>CMFCVisualManager::OnDrawMenuItemButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuItemButton(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rectButton,  
    BOOL bHighlight,  
    BOOL bDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rectButton`  
 [in] `bHighlight`  
 [in] `bDisabled`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenulabela--cmfcvisualmanagerondrawmenulabel"></a><a name="ondrawmenulabel"></a>CMFCVisualManager::OnDrawMenuLabel  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnDrawMenuLabel(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenuresizebara--cmfcvisualmanagerondrawmenuresizebar"></a><a name="ondrawmenuresizebar"></a>CMFCVisualManager::OnDrawMenuResizeBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuResizeBar(
    CDC* pDC,  
    CRect rect,  
    int nResizeFlags);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `nResizeFlags`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenuscrollbuttona--cmfcvisualmanagerondrawmenuscrollbutton"></a><a name="ondrawmenuscrollbutton"></a>CMFCVisualManager::OnDrawMenuScrollButton  
 Платформа вызывает этот метод при отрисовке меню кнопки прокрутки.  
  
```  
virtual void OnDrawMenuScrollButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsScrollDown,  
    BOOL bIsHighlited,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки прокрутки.  
  
 [in] `bIsScrollDown`  
 Логическое значение, указывающее, какой тип кнопки рисует диспетчер визуального представления. Значение `TRUE` указывает диспетчер визуального представления Рисует кнопку вниз.  
  
 [in] `bIsHighlited`  
 Логическое значение, указывающее, выделен ли кнопки.  
  
 [in] `bIsPressed`  
 Логическое значение, указывающее, является ли кнопка нажата.  
  
 [in] `bIsDisabled`  
 Логическое значение, указывающее, является ли кнопка отключена.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида кнопки меню прокрутки. При общей высоты элементов меню превышает высоту во всплывающем меню кнопки прокрутки меню появляются края всплывающих меню.  
  
##  <a name="a-nameondrawmenushadowa--cmfcvisualmanagerondrawmenushadow"></a><a name="ondrawmenushadow"></a>CMFCVisualManager::OnDrawMenuShadow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMenuShadow(
    CDC* pDC,  
    const CRect& rectClient,  
    const CRect& rectExclude,  
    int nDepth,  
    int iMinBrightness,  
    int iMaxBrightness,  
    CBitmap* pBmpSaveBottom,  
    CBitmap* pBmpSaveRight,  
    BOOL bRTL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rectClient`  
 [in] `rectExclude`  
 [in] `nDepth`  
 [in] `iMinBrightness`  
 [in] `iMaxBrightness`  
 [in] `pBmpSaveBottom`  
 [in] `pBmpSaveRight`  
 [in] `bRTL`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawmenusystembuttona--cmfcvisualmanagerondrawmenusystembutton"></a><a name="ondrawmenusystembutton"></a>CMFCVisualManager::OnDrawMenuSystemButton  
 Платформа вызывает этот метод при отрисовке кнопки меню системы для приложения.  
  
```  
virtual void OnDrawMenuSystemButton(
    CDC* pDC,  
    CRect rect,  
    UINT uiSystemCommand,  
    UINT nStyle,  
    BOOL bHighlight);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки.  
  
 [in] `uiSystemCommand`  
 Флаг, указывающий, какая команда системы связан с кнопкой. Возможные значения: SC_CLOSE, SC_MINIMIZE и SC_RESTORE.  
  
 [in] `nStyle`  
 Флаг, указывающий текущий стиль кнопки. Возможные значения: TBBS_PRESSED, TBBS_DISABLED и 0.  
  
 [in] `bHighlight`  
 Логический параметр, который указывает, выделен ли кнопки.  
  
### <a name="remarks"></a>Примечания  
 Кнопки меню системы **закрыть**, **свернуть**, **развернуть**, и **восстановить** кнопки, расположенные в строке заголовка.  
  
 Реализация по умолчанию для этого метода вызывает [CDC::DrawFrameControl](../../mfc/reference/cdc-class.md#drawframecontrol) с `DFC_CAPTION` типа. Переопределите этот метод в классе, производном диспетчер визуального представления настроить внешний вид кнопки в системе.  
  
##  <a name="a-nameondrawminiframebordera--cmfcvisualmanagerondrawminiframeborder"></a><a name="ondrawminiframeborder"></a>CMFCVisualManager::OnDrawMiniFrameBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawMiniFrameBorder(
    CDC* pDC,  
    CPaneFrameWnd* pFrameWnd,  
    CRect rectBorder,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pFrameWnd`  
 [in] `rectBorder`  
 [in] `rectBorderSize`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawoutlookbarsplittera--cmfcvisualmanagerondrawoutlookbarsplitter"></a><a name="ondrawoutlookbarsplitter"></a>CMFCVisualManager::OnDrawOutlookBarSplitter  
 Платформа вызывает этот метод при отрисовке разделитель для панели Outlook.  
  
```  
virtual void OnDrawOutlookBarSplitter(
    CDC* pDC,  
    CRect rectSplitter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectSplitter`  
 Прямоугольник, который определяет границы разделителя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида разделителей на панель Outlook.  
  
##  <a name="a-nameondrawoutlookpagebuttonbordera--cmfcvisualmanagerondrawoutlookpagebuttonborder"></a><a name="ondrawoutlookpagebuttonborder"></a>CMFCVisualManager::OnDrawOutlookPageButtonBorder  
 Вызывается инфраструктурой при отрисовке границы кнопки страницы Outlook.  
  
```  
virtual void OnDrawOutlookPageButtonBorder(
    CDC* pDC,  
    CRect& rectBtn,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectBtn`  
 Прямоугольник, который определяет границы кнопки страницы Outlook.  
  
 [in] `bIsHighlighted`  
 Логическое значение, указывающее, выделен ли кнопки.  
  
 [in] `bIsPressed`  
 Логическое значение, указывающее, является ли кнопка нажата.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в пользовательский диспетчер визуального представления для изменения внешнего вида кнопки страницы Outlook.  
  
##  <a name="a-nameondrawpanebordera--cmfcvisualmanagerondrawpaneborder"></a><a name="ondrawpaneborder"></a>CMFCVisualManager::OnDrawPaneBorder  
 Платформа вызывает этот метод, когда он рисует границу [CPane класс](../../mfc/reference/cpane-class.md) объекта.  
  
```  
virtual void OnDrawPaneBorder(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства панели элементов управления.  
  
 [in] `pBar`  
 Указатель на область. Диспетчер визуального представления рисует границу панели.  
  
 [in] `rect`  
 Прямоугольник, определяющий границы области.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод отображает Стандартная граница. Переопределите этот метод в производном классе, чтобы настроить внешний вид границы.  
  
##  <a name="a-nameondrawpanecaptiona--cmfcvisualmanagerondrawpanecaption"></a><a name="ondrawpanecaption"></a>CMFCVisualManager::OnDrawPaneCaption  
 Платформа вызывает этот метод при отрисовке заголовка для экземпляра [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).  
  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на объект `CDockablePane`. Платформа рисует заголовок для этой области.  
  
 [in] `bActive`  
 Логический параметр, указывающий, активен ли на панели управления.  
  
 [in] `rectCaption`  
 Прямоугольник, который определяет границы заголовка.  
  
 [in] `rectButtons`  
 Прямоугольник, который определяет границы кнопки заголовка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет текста заголовка.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида области заголовков.  
  
##  <a name="a-nameondrawpanedividera--cmfcvisualmanagerondrawpanedivider"></a><a name="ondrawpanedivider"></a>CMFCVisualManager::OnDrawPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPaneDivider(
    CDC* pDC,  
    CPaneDivider* pSlider,  
    CRect rect,  
    BOOL bAutoHideMode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pSlider`  
 [in] `rect`  
 [in] `bAutoHideMode`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawpopupwindowbordera--cmfcvisualmanagerondrawpopupwindowborder"></a><a name="ondrawpopupwindowborder"></a>CMFCVisualManager::OnDrawPopupWindowBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPopupWindowBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawpopupwindowbuttonbordera--cmfcvisualmanagerondrawpopupwindowbuttonborder"></a><a name="ondrawpopupwindowbuttonborder"></a>CMFCVisualManager::OnDrawPopupWindowButtonBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawPopupWindowButtonBorder(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rectClient`  
 [in] `pButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawpopupwindowcaptiona--cmfcvisualmanagerondrawpopupwindowcaption"></a><a name="ondrawpopupwindowcaption"></a>CMFCVisualManager::OnDrawPopupWindowCaption  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnDrawPopupWindowCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CMFCDesktopAlertWnd* pPopupWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rectCaption`  
 [in] `pPopupWnd`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbonapplicationbuttona--cmfcvisualmanagerondrawribbonapplicationbutton"></a><a name="ondrawribbonapplicationbutton"></a>CMFCVisualManager::OnDrawRibbonApplicationButton  
 Платформа вызывает этот метод при отрисовке **главной кнопки** на ленте.  
  
```  
virtual void OnDrawRibbonApplicationButton(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на **главной кнопки** на ленте.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления, если вы хотите настроить внешний вид **кнопку Main**.  
  
##  <a name="a-nameondrawribbonbuttonbordera--cmfcvisualmanagerondrawribbonbuttonborder"></a><a name="ondrawribbonbuttonborder"></a>CMFCVisualManager::OnDrawRibbonButtonBorder  
 Платформа вызывает этот метод, когда он рисует границу кнопки на ленте.  
  
```  
virtual void OnDrawRibbonButtonBorder(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) объекта. Платформа рисует границу для этой кнопки ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида `CMFCRibbonButton`.  
  
##  <a name="a-nameondrawribbonbuttonsgroupa--cmfcvisualmanagerondrawribbonbuttonsgroup"></a><a name="ondrawribbonbuttonsgroup"></a>CMFCVisualManager::OnDrawRibbonButtonsGroup  
 Платформа вызывает этот метод при отрисовке группу кнопки на ленте.  
  
```  
virtual COLORREF OnDrawRibbonButtonsGroup(
    CDC* pDC,  
    CMFCRibbonButtonsGroup* pGroup,  
    CRect rectGroup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pGroup`  
 Указатель на группу кнопки на ленте. Платформа рисует этой группы кнопок.  
  
 [in] `rectGroup`  
 Прямоугольник, который определяет границы группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зарезервированное значение. Реализация по умолчанию возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида группы кнопки на ленте.  
  
##  <a name="a-nameondrawribboncaptiona--cmfcvisualmanagerondrawribboncaption"></a><a name="ondrawribboncaption"></a>CMFCVisualManager::OnDrawRibbonCaption  
 Платформа вызывает этот метод при отрисовке заголовка окна фрейма главного окна. Платформа вызывает этот метод только в том случае, если лента интегрирован с главного фрейма.  
  
```  
virtual void OnDrawRibbonCaption(
    CDC* pDC,  
    CMFCRibbonBar* pBar,  
    CRect rect,  
    CRect rectText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на панель ленты. Диспетчер визуального представления рисует этой лентой.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы панели ленты.  
  
 [in] `rectText`  
 Прямоугольник, который определяет границы для текста заголовка окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию в производном диспетчер визуального представления для настройки внешнего вида заголовка окна. Этот метод влияет на строке заголовка только в том случае, если лента интегрирован с фрейма главного окна.  
  
##  <a name="a-nameondrawribboncaptionbuttona--cmfcvisualmanagerondrawribboncaptionbutton"></a><a name="ondrawribboncaptionbutton"></a>CMFCVisualManager::OnDrawRibbonCaptionButton  
 Платформа вызывает этот метод при отрисовке заголовка, расположенную на ленте.  
  
```  
virtual void OnDrawRibbonCaptionButton(
    CDC* pDC,  
    CMFCRibbonCaptionButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
 `pButton`  
 Указатель на `CMFCRibbonCaptionButton` класса. Платформа рисует этой кнопки заголовка.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида кнопки заголовка на ленте.  
  
##  <a name="a-nameondrawribboncategorya--cmfcvisualmanagerondrawribboncategory"></a><a name="ondrawribboncategory"></a>CMFCVisualManager::OnDrawRibbonCategory  
 Платформа вызывает этот метод при отрисовке [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md) объекта.  
  
```  
virtual void OnDrawRibbonCategory(
    CDC* pDC,  
    CMFCRibbonCategory* pCategory,  
    CRect rectCategory);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pCategory`  
 Указатель на объект `CMFCRibbonCategory`. Платформа рисует этой категории ленты.  
  
 [in] `rectCategory`  
 Прямоугольник, который определяет границы панели категории на ленте.  
  
### <a name="remarks"></a>Примечания  
 Категория ленты — логическое группирование команд меню. Дополнительные сведения о категориях ленты см. в разделе [CMFCRibbonCategory класса](../../mfc/reference/cmfcribboncategory-class.md).  
  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида категорией ленты.  
  
##  <a name="a-nameondrawribboncategorycaptiona--cmfcvisualmanagerondrawribboncategorycaption"></a><a name="ondrawribboncategorycaption"></a>CMFCVisualManager::OnDrawRibbonCategoryCaption  
 Платформа вызывает этот метод при отрисовке заголовка окна для категории ленты.  
  
```  
virtual COLORREF OnDrawRibbonCategoryCaption(
    CDC* pDC,  
    CMFCRibbonContextCaption* pContextCaption);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Графический контекст.  
  
 [in] `pContextCaption`  
 Указатель на строку заголовка. Рисует диспетчер визуального представления, это [CMFCRibbonContextCaption класс](../../mfc/reference/cmfcribboncontextcaption-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, указывающий цвет текста в строке заголовка.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид заголовка категории ленты. Дополнительные сведения о строке заголовка см. в разделе [CMFCRibbonContextCaption класса](../../mfc/reference/cmfcribboncontextcaption-class.md).  
  
##  <a name="a-nameondrawribboncategoryscrolla--cmfcvisualmanagerondrawribboncategoryscroll"></a><a name="ondrawribboncategoryscroll"></a>CMFCVisualManager::OnDrawRibbonCategoryScroll  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonCategoryScroll(
    CDC* pDC,  
    CRibbonCategoryScroll* pScroll);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pScroll`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribboncategorytaba--cmfcvisualmanagerondrawribboncategorytab"></a><a name="ondrawribboncategorytab"></a>CMFCVisualManager::OnDrawRibbonCategoryTab  
 Платформа вызывает этот метод при отрисовке вкладку категория ленты.  
  
```  
virtual COLORREF OnDrawRibbonCategoryTab(
    CDC* pDC,  
    CMFCRibbonTab* pTab,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pTab`  
 Указатель на экземпляр `CMFCRibbonTab` класса. Платформа рисует на этой вкладке.  
  
 [in] `bIsActive`  
 Логический параметр, указывающий, активна ли вкладка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, который используется для текста на вкладке ленты категории.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида категории вкладки на ленте. Дополнительные сведения о категориях ленты см. в разделе [CMFCRibbonCategory класса](../../mfc/reference/cmfcribboncategory-class.md).  
  
##  <a name="a-nameondrawribboncheckboxonlista--cmfcvisualmanagerondrawribboncheckboxonlist"></a><a name="ondrawribboncheckboxonlist"></a>CMFCVisualManager::OnDrawRibbonCheckBoxOnList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonCheckBoxOnList(
    CDC* pDC,  
    CMFCRibbonCheckBox* pCheckBox,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pCheckBox`  
 [in] `rect`  
 [in] `bIsSelected`  
 [in] `bHighlighted`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribboncolorpaletteboxa--cmfcvisualmanagerondrawribboncolorpalettebox"></a><a name="ondrawribboncolorpalettebox"></a>CMFCVisualManager::OnDrawRibbonColorPaletteBox  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonColorPaletteBox(
    CDC* pDC,  
    CMFCRibbonColorButton* pColorButton,  
    CMFCRibbonGalleryIcon* pIcon,  
    COLORREF color,  
    CRect rect,  
    BOOL bDrawTopEdge,  
    BOOL bDrawBottomEdge,  
    BOOL bIsHighlighted,  
    BOOL bIsChecked,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pColorButton`  
 [in] `pIcon`  
 [in] `color`  
 [in] `rect`  
 [in] `bDrawTopEdge`  
 [in] `bDrawBottomEdge`  
 [in] `bIsHighlighted`  
 [in] `bIsChecked`  
 [in] `bIsDisabled`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbondefaultpanebuttona--cmfcvisualmanagerondrawribbondefaultpanebutton"></a><a name="ondrawribbondefaultpanebutton"></a>CMFCVisualManager::OnDrawRibbonDefaultPaneButton  
 Платформа вызывает этот метод при отрисовке кнопку по умолчанию для панели ленты.  
  
```  
virtual void OnDrawRibbonDefaultPaneButton(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на кнопку по умолчанию для панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Платформа отображает кнопку по умолчанию, когда минимальный размер изменяется область ленты и отсутствует область для отображения содержимого панели. Когда пользователь нажимает на кнопку по умолчанию, платформа отображает раскрывающееся меню с содержимым для панели.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида кнопки по умолчанию.  
  
##  <a name="a-nameondrawribbondefaultpanebuttoncontexta--cmfcvisualmanagerondrawribbondefaultpanebuttoncontext"></a><a name="ondrawribbondefaultpanebuttoncontext"></a>CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonDefaultPaneButtonContext(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbondefaultpanebuttonindicatora--cmfcvisualmanagerondrawribbondefaultpanebuttonindicator"></a><a name="ondrawribbondefaultpanebuttonindicator"></a>CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonDefaultPaneButtonIndicator(
    CDC* pDC,  
    CMFCRibbonButton* pButton,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
 [in] `bIsSelected`  
 [in] `bHighlighted`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbongallerybordera--cmfcvisualmanagerondrawribbongalleryborder"></a><a name="ondrawribbongalleryborder"></a>CMFCVisualManager::OnDrawRibbonGalleryBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonGalleryBorder(
    CDC* pDC,  
    CMFCRibbonGallery* pButton,  
    CRect rectBorder);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rectBorder`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbongallerybuttona--cmfcvisualmanagerondrawribbongallerybutton"></a><a name="ondrawribbongallerybutton"></a>CMFCVisualManager::OnDrawRibbonGalleryButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonGalleryButton(
    CDC* pDC,  
    CMFCRibbonGalleryIcon* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbonkeytipa--cmfcvisualmanagerondrawribbonkeytip"></a><a name="ondrawribbonkeytip"></a>CMFCVisualManager::OnDrawRibbonKeyTip  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonKeyTip(
    CDC* pDC,  
    CMFCRibbonBaseElement* pElement,  
    CRect rect,  
    CString str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pElement`  
 [in] `rect`  
 [in] `str`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbonlabela--cmfcvisualmanagerondrawribbonlabel"></a><a name="ondrawribbonlabel"></a>CMFCVisualManager::OnDrawRibbonLabel  
 Платформа вызывает этот метод при отрисовке метку ленты.  
  
```  
virtual void OnDrawRibbonLabel(
    CDC* pDC,  
    CMFCRibbonLabel* pLabel,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pLabel`  
 Указатель на [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) объекта. Платформа рисует эту метку ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы изменить метку ленты.  
  
##  <a name="a-nameondrawribbonmainpanelbuttonbordera--cmfcvisualmanagerondrawribbonmainpanelbuttonborder"></a><a name="ondrawribbonmainpanelbuttonborder"></a>CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder  
 Платформа вызывает этот метод, когда он рисует границу [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) , находится на **Main** панель.  
  
```  
virtual void OnDrawRibbonMainPanelButtonBorder(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на `CMFCRibbonButton` главной панели ленты. Платформа рисует границу для этой кнопки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить внешний вид границы для `CMFCRibbonButton` на **Main** панель.  
  
##  <a name="a-nameondrawribbonmainpanelframea--cmfcvisualmanagerondrawribbonmainpanelframe"></a><a name="ondrawribbonmainpanelframe"></a>CMFCVisualManager::OnDrawRibbonMainPanelFrame  
 Платформа вызывает этот метод при отрисовке рамку вокруг [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md).  
  
```  
virtual void OnDrawRibbonMainPanelFrame(
    CDC* pDC,  
    CMFCRibbonMainPanel* pPanel,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pPanel`  
 Указатель на `CMFCRibbonMainPanel`.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы `CMFCRibbonMainPanel`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном visual диспетчере, чтобы настроить внешний вид рамки для `CMFCRibbonMainPanel`.  
  
##  <a name="a-nameondrawribbonmenucheckframea--cmfcvisualmanagerondrawribbonmenucheckframe"></a><a name="ondrawribbonmenucheckframe"></a>CMFCVisualManager::OnDrawRibbonMenuCheckFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawRibbonMenuCheckFrame(
    CDC* pDC,  
    CMFCRibbonButton* pButton,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pButton`  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawribbonpanela--cmfcvisualmanagerondrawribbonpanel"></a><a name="ondrawribbonpanel"></a>CMFCVisualManager::OnDrawRibbonPanel  
 Платформа вызывает этот метод при отрисовке [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md) объекта.  
  
```  
virtual COLORREF OnDrawRibbonPanel(
    CDC* pDC,  
    CMFCRibbonPanel* pPanel,  
    CRect rectPanel,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pPanel`  
 Указатель на объект `CMFCRibbonPanel`. Платформа рисует этот панель ленты.  
  
 [in] `rectPanel`  
 Прямоугольник, который определяет границы панели.  
  
 [in] `rectCaption`  
 Прямоугольник, который определяет границы заголовка для панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текста на панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид панели ленты.  
  
##  <a name="a-nameondrawribbonpanelcaptiona--cmfcvisualmanagerondrawribbonpanelcaption"></a><a name="ondrawribbonpanelcaption"></a>CMFCVisualManager::OnDrawRibbonPanelCaption  
 Платформа вызывает этот метод при отрисовке заголовка [CMFCRibbonPanel класса](../../mfc/reference/cmfcribbonpanel-class.md).  
  
```  
virtual void OnDrawRibbonPanelCaption(
    CDC* pDC,  
    CMFCRibbonPanel* pPanel,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pPanel`  
 Указатель на объект `CMFCRibbonPanel`. Платформа рисует заголовок для этой панели ленты.  
  
 [in] `rectCaption`  
 Прямоугольник, который определяет границы заголовка для панели ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид заголовков для панели ленты.  
  
##  <a name="a-nameondrawribbonprogressbara--cmfcvisualmanagerondrawribbonprogressbar"></a><a name="ondrawribbonprogressbar"></a>CMFCVisualManager::OnDrawRibbonProgressBar  
 Платформа вызывает этот метод при отрисовке [CMFCRibbonProgressBar класса](../../mfc/reference/cmfcribbonprogressbar-class.md).  
  
```  
virtual void OnDrawRibbonProgressBar(
    CDC* pDC,  
    CMFCRibbonProgressBar* pProgress,  
    CRect rectProgress,  
    CRect rectChunk,  
    BOOL bInfiniteMode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pProgress`  
 Указатель на объект `CMFCRibbonProgressBar`. Платформа рисует индикатора.  
  
 [in] `rectProgress`  
 Прямоугольник, который определяет границы индикатора хода выполнения.  
  
 [in] `rectChunk`  
 Прямоугольник, который определяет границы области, окружающей индикатора хода выполнения.  
  
 [in] `bInfiniteMode`  
 Логический параметр, указывающий режим индикатора хода выполнения. Значение `TRUE` означает панели в режиме бесконечной. Реализация по умолчанию этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид индикатора.  
  
##  <a name="a-nameondrawribbonquickaccesstoolbarseparatora--cmfcvisualmanagerondrawribbonquickaccesstoolbarseparator"></a><a name="ondrawribbonquickaccesstoolbarseparator"></a>CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator  
 Платформа вызывает этот метод при отрисовке разделителя **быстрого доступа** ленты.  
  
```  
virtual void OnDrawRibbonQuickAccessToolBarSeparator(
    CDC* pDC,  
    CMFCRibbonSeparator* pSeparator,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSeparator`  
 Указатель на [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md) объекта. Платформа рисует этот разделитель ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы разделителя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид разделители ленты на **быстрого доступа**.  
  
##  <a name="a-nameondrawribbonrecentfilesframea--cmfcvisualmanagerondrawribbonrecentfilesframe"></a><a name="ondrawribbonrecentfilesframe"></a>CMFCVisualManager::OnDrawRibbonRecentFilesFrame  
 Платформа вызывает этот метод при отрисовке рамку вокруг списка последних файлов.  
  
```  
virtual void OnDrawRibbonRecentFilesFrame(
    CDC* pDC,  
    CMFCRibbonMainPanel* pPanel,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pPanel`  
 Указатель на **Main** панели на ленте.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы рамки для списка последних файлов.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида списка последних файлов.  
  
##  <a name="a-nameondrawribbonsliderchannela--cmfcvisualmanagerondrawribbonsliderchannel"></a><a name="ondrawribbonsliderchannel"></a>CMFCVisualManager::OnDrawRibbonSliderChannel  
 Платформа вызывает этот метод при отрисовке канала [CMFCRibbonSlider класса](../../mfc/reference/cmfcribbonslider-class.md).  
  
```  
virtual void OnDrawRibbonSliderChannel(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSlider`  
 Указатель на объект CMFCRibbonSlider. Платформа рисует канала для этот ползунок ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы для канала ползунок ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид канала ползунок ленты.  
  
##  <a name="a-nameondrawribbonsliderthumba--cmfcvisualmanagerondrawribbonsliderthumb"></a><a name="ondrawribbonsliderthumb"></a>CMFCVisualManager::OnDrawRibbonSliderThumb  
 Платформа вызывает этот метод при отрисовке ползунка [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) объекта.  
  
```  
virtual void OnDrawRibbonSliderThumb(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSlider`  
 Указатель на `CMFCRibbonSlider`. Платформа рисует бегунка этот ползунок ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы бегунка ползунок ленты.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, если выделяется бегунка.  
  
 [in] `bIsPressed`  
 Логический параметр, указывающий, если нажата бегунка.  
  
 [in] `bIsDisabled`  
 Логический параметр, указывающий, если бегунка недоступна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида бегунка для `CMFCRibbonSlider`.  
  
##  <a name="a-nameondrawribbonsliderzoombuttona--cmfcvisualmanagerondrawribbonsliderzoombutton"></a><a name="ondrawribbonsliderzoombutton"></a>CMFCVisualManager::OnDrawRibbonSliderZoomButton  
 Платформа вызывает этот метод при отрисовке кнопки масштаба для [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) объекта.  
  
```  
virtual void OnDrawRibbonSliderZoomButton(
    CDC* pDC,  
    CMFCRibbonSlider* pSlider,  
    CRect rect,  
    BOOL bIsZoomOut,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSlider`  
 Указатель на объект `CMFCRibbonSlider`. Платформа рисует этот ползунок ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки масштабирования на ползунке ленты.  
  
 [in] `bIsZoomOut`  
 Логический параметр, который указывает, какая кнопка рисует платформы. Значение `TRUE` показывает левая кнопка с «-» для уменьшения. Значение `FALSE` показывает правая кнопка с «+» для увеличения.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли кнопки.  
  
 [in] `bIsPressed`  
 Логический параметр, указывающий, является ли кнопка нажата.  
  
 [in] `bIsDisabled`  
 Логический параметр, указывающий, является ли эта кнопка будет недоступна.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию кнопки на ленте ползунок масштабирования, круг с помощью + или - вход в центре. Чтобы настроить внешний вид кнопки масштабирования, переопределите этот метод в производном диспетчер визуального представления.  
  
##  <a name="a-nameondrawribbonstatusbarpanea--cmfcvisualmanagerondrawribbonstatusbarpane"></a><a name="ondrawribbonstatusbarpane"></a>CMFCVisualManager::OnDrawRibbonStatusBarPane  
 Платформа вызывает этот метод при отрисовке панели в строке состояния.  
  
```  
virtual COLORREF OnDrawRibbonStatusBarPane(
    CDC* pDC,  
    CMFCRibbonStatusBar* pBar,  
    CMFCRibbonStatusBarPane* pPane);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на строку состояния, содержащий область.  
  
 [in] `pPane`  
 Указатель на панели строки состояния. Платформа рисует этот [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зарезервированное значение. Реализация по умолчанию возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида панели в строке состояния.  
  
##  <a name="a-nameondrawribbontabsframea--cmfcvisualmanagerondrawribbontabsframe"></a><a name="ondrawribbontabsframe"></a>CMFCVisualManager::OnDrawRibbonTabsFrame  
 Платформа вызывает этот метод при отрисовке рамку вокруг набора вкладок на ленте.  
  
```  
virtual COLORREF OnDrawRibbonTabsFrame(
    CDC* pDC,  
    CMFCRibbonBar* pWndRibbonBar,  
    CRect rectTab);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
 `pWndRibbonBar`  
 Указатель на [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) объекта. Платформа рисует кадр, для этой панели ленты.  
  
 `rectTab`  
 Прямоугольник, который определяет границы вкладки ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зарезервированное значение. По умолчанию этот метод возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки рамку вокруг набор вкладок на ленте.  
  
##  <a name="a-nameondrawscrollbuttonsa--cmfcvisualmanagerondrawscrollbuttons"></a><a name="ondrawscrollbuttons"></a>CMFCVisualManager::OnDrawScrollButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawScrollButtons(
    CDC* pDC,  
    const CRect& rect,  
    const int nBorderSize,  
    int iImage,  
    BOOL bHilited);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `nBorderSize`  
 [in] `iImage`  
 [in] `bHilited`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawseparatora--cmfcvisualmanagerondrawseparator"></a><a name="ondrawseparator"></a>CMFCVisualManager::OnDrawSeparator  
 Платформа вызывает этот метод при отрисовке разделителя.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели элементов управления.  
  
 [in] `pBar`  
 Указатель на область, содержащая разделитель.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы разделителя.  
  
 [in] `bIsHoriz`  
 Логический параметр, указывающий направление закрепленной панели. Значение `TRUE` указывает, что панель закреплена горизонтально. Значение `FALSE` указывает, что панель закреплена вертикально.  
  
### <a name="remarks"></a>Примечания  
 Разделители используются на панели элементов управления для разделения групп соответствующие значки. Реализация по умолчанию для этого метода отображает стандартный разделитель. Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида разделителя.  
  
##  <a name="a-nameondrawshowallmenuitemsa--cmfcvisualmanagerondrawshowallmenuitems"></a><a name="ondrawshowallmenuitems"></a>CMFCVisualManager::OnDrawShowAllMenuItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawShowAllMenuItems(
    CDC* pDC,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `state`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawspinbuttonsa--cmfcvisualmanagerondrawspinbuttons"></a><a name="ondrawspinbuttons"></a>CMFCVisualManager::OnDrawSpinButtons  
 Платформа вызывает этот метод при отрисовке экземпляр [CMFCSpinButtonCtrl класса](../../mfc/reference/cmfcspinbuttonctrl-class.md).  
  
```  
virtual void OnDrawSpinButtons(
    CDC* pDC,  
    CRect rectSpin,  
    int nState,  
    BOOL bOrientation,  
    CMFCSpinButtonCtrl* pSpinCtrl);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectSpin`  
 Прямоугольник, который задает границы элемента управления "Счетчик".  
  
 [in] `nState`  
 Флаг, указывающий состояние элемента управления "Счетчик". Дополнительные сведения см. в разделе "Примечания".  
  
 [in] `bOrientation`  
 Логический параметр, который задает ориентацию элемента управления "Счетчик". Значение `TRUE` указывает горизонтальной счетчик. В противном случае — это вертикальная.  
  
 [in] `pSpinCtrl`  
 Указатель на элемент управления "Счетчик". Платформа рисует кнопки для данного элемента управления.  
  
### <a name="remarks"></a>Примечания  
 `nState` Указывает состояние элемента управления "Счетчик". Параметр является одним из следующих значений:  
  
-   AFX_SPIN_PRESSEDUP  
  
-   AFX_SPIN_PRESSEDDOWN  
  
-   AFX_SPIN_HIGHLIGHTEDUP  
  
-   AFX_SPIN_HIGHLIGHTEDDOWN  
  
-   AFX_SPIN_DISABLED  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида элемента управления "Счетчик".  
  
##  <a name="a-nameondrawsplitterbordera--cmfcvisualmanagerondrawsplitterborder"></a><a name="ondrawsplitterborder"></a>CMFCVisualManager::OnDrawSplitterBorder  
 Платформа вызывает этот метод, когда он рисовал границу вокруг экземпляра [CSplitterWndEx класса](csplitterwndex-class.md).  
  
```  
virtual void OnDrawSplitterBorder(
    CDC* pDC,  
    CSplitterWndEx* pSplitterWnd,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSplitterWnd`  
 Указатель на окно-разделитель. Платформа рисует границу окна.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы окна-разделителя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить внешний вид границы окна-разделителя.  
  
##  <a name="a-nameondrawsplitterboxa--cmfcvisualmanagerondrawsplitterbox"></a><a name="ondrawsplitterbox"></a>CMFCVisualManager::OnDrawSplitterBox  
 Платформа вызывает этот метод при отрисовке поле Перетащите экземпляр [CSplitterWndEx класса](csplitterwndex-class.md). Перетащите поле появляется, когда пользователь выбирает разделитель и изменяет размеры дочерних окон.  
  
```  
virtual void OnDrawSplitterBox(
    CDC* pDC,  
    CSplitterWndEx* pSplitterWnd,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSplitterWnd`  
 Указатель на окно-разделитель. Платформа Рисует поле для окна-разделителя.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы окна-разделителя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида, перетащите поля для окна-разделителя.  
  
##  <a name="a-nameondrawstatusbarpanebordera--cmfcvisualmanagerondrawstatusbarpaneborder"></a><a name="ondrawstatusbarpaneborder"></a>CMFCVisualManager::OnDrawStatusBarPaneBorder  
 Платформа вызывает этот метод, когда он рисует границу для [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) объекта.  
  
```  
virtual void OnDrawStatusBarPaneBorder(
    CDC* pDC,  
    CMFCStatusBar* pBar,  
    CRect rectPane,  
    UINT uiID,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pBar`  
 Указатель на объект `CMFCStatusBar`. Платформа рисует этот объект состояния панели.  
  
 [in] `rectPane`  
 Прямоугольник, который определяет границы строки состояния.  
  
 [in] `uiID`  
 Идентификатор строки состояния.  
  
 [in] `nStyle`  
 Стиль в строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить внешний вид границы `CMFCStatusBar` объекта.  
  
##  <a name="a-nameondrawstatusbarprogressa--cmfcvisualmanagerondrawstatusbarprogress"></a><a name="ondrawstatusbarprogress"></a>CMFCVisualManager::OnDrawStatusBarProgress  
 Платформа вызывает этот метод при отрисовке индикатора хода выполнения [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) объекта.  
  
```  
virtual void OnDrawStatusBarProgress(
    CDC* pDC,  
    CMFCStatusBar* pStatusBar,  
    CRect rectProgress,  
    int nProgressTotal,  
    int nProgressCurr,  
    COLORREF clrBar,  
    COLORREF clrProgressBarDest,  
    COLORREF clrProgressText,  
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для строки состояния.  
  
 [in] `pStatusBar`  
 `CMFCStatusBar` Объект, который содержит индикатор хода выполнения.  
  
 [in] `rectProgress`  
 Прямоугольник, который определяет границы индикатора хода выполнения.  
  
 [in] `nProgressTotal`  
 Общее количество для индикатора хода выполнения.  
  
 [in] `nProgressCurr`  
 Текущий ход выполнения для индикатора.  
  
 [in] `clrBar`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр, который указывает начальный цвет индикатора хода выполнения. Значение — либо начала градиентной или завершения цвет индикатора хода выполнения.  
  
 [in] `clrProgressBarDest`  
 A `COLORREF` параметр, который указывает конец цветового градиента для индикатора. Если `clrProgressBarDest` равно -1, платформа не рисует индикатор как цветового градиента. Вместо этого он заполняет весь индикатор цвет, определенный параметром `clrBar`.  
  
 [in] `clrProgressText`  
 A `COLORREF` параметр, указывающий цвет текста для текстовое представление текущего хода выполнения. Этот параметр учитывается, если `bProgressText` равен `FALSE`.  
  
 [in] `bProgressText`  
 Логический параметр, который указывает, следует ли отображать текстовое представление текущего хода выполнения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида `CMFCStatusBar` объекта.  
  
##  <a name="a-nameondrawstatusbarsizeboxa--cmfcvisualmanagerondrawstatusbarsizebox"></a><a name="ondrawstatusbarsizebox"></a>CMFCVisualManager::OnDrawStatusBarSizeBox  
 Платформа вызывает этот метод при отрисовке поле размер для [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  
  
```  
virtual void OnDrawStatusBarSizeBox(
    CDC* pDC,  
    CMFCStatusBar* pStatBar,  
    CRect rectSizeBox);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pStatBar`  
 Указатель на строку состояния. Платформа Рисует поле размер для данной строки состояния.  
  
 [in] `rectSizeBox`  
 Прямоугольник, который определяет границы поле размер.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида окна размер на `CMFCStatusBar`.  
  
##  <a name="a-nameondrawtaba--cmfcvisualmanagerondrawtab"></a><a name="ondrawtab"></a>CMFCVisualManager::OnDrawTab  
 Платформа вызывает этот метод при отрисовке вкладки для [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объекта.  
  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectTab`  
 Прямоугольник, который задает границы элемента управления вкладками.  
  
 [in] `iTab`  
 Индекс вкладки, который рисует платформа.  
  
 [in] `bIsActive`  
 Логический параметр, который указывает, активна ли вкладка.  
  
 [in] `pTabWnd`  
 Указатель на объект `CMFCBaseTabCtrl`. Платформа рисует вкладок.  
  
### <a name="remarks"></a>Примечания  
 A `CMFCBaseTabCtrl` объекта вызывает этот метод, когда он обрабатывает сообщение WM_PAINT.  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид вкладок.  
  
##  <a name="a-nameondrawtabclosebuttona--cmfcvisualmanagerondrawtabclosebutton"></a><a name="ondrawtabclosebutton"></a>CMFCVisualManager::OnDrawTabCloseButton  
 Платформа вызывает этот метод при отрисовке **закрыть** кнопку на активной вкладке.  
  
```  
virtual void OnDrawTabCloseButton(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы **закрыть** кнопки.  
  
 [in] `pTabWnd`  
 Указатель на элемент управления вкладками. Рисует платформа **закрыть** кнопки для этого элемента управления вкладками.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий ли **закрыть** выделена кнопка.  
  
 [in] `bIsPressed`  
 Логический параметр, указывающий ли **закрыть** нажата кнопка.  
  
 [in] `bIsDisabled`  
 Логический параметр, указывающий ли **закрыть** кнопка отключена.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида **закрыть** кнопки на вкладке active `pTabWnd`.  
  
##  <a name="a-nameondrawtabcontenta--cmfcvisualmanagerondrawtabcontent"></a><a name="ondrawtabcontent"></a>CMFCVisualManager::OnDrawTabContent  
 Платформа вызывает этот метод при отрисовке содержимого на внутреннюю экземпляр [CMFCBaseTabCtrl класса](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
```  
virtual void OnDrawTabContent(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectTab`  
 Прямоугольник, который определяет границы внутреннюю вкладку.  
  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки. Платформа рисует внутренней части этой вкладки.  
  
 [in] `bIsActive`  
 Логический параметр, указывающий, активен ли вкладка.  
  
 [in] `pTabWnd`  
 Указатель на элемент управления с вкладками, который содержит вкладку, на котором производится рисование.  
  
 [in] `clrText`  
 Цвет текста на внутренней вкладке.  
  
### <a name="remarks"></a>Примечания  
 Внутренняя вкладка содержит текст и значки на вкладке. Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида вкладок.  
  
##  <a name="a-nameondrawtabsbuttonbordera--cmfcvisualmanagerondrawtabsbuttonborder"></a><a name="ondrawtabsbuttonborder"></a>CMFCVisualManager::OnDrawTabsButtonBorder  
 Платформа вызывает этот метод при отрисовке границы кнопки вкладки.  
  
```  
virtual void OnDrawTabsButtonBorder(
    CDC* pDC,  
    CRect& rect,  
    CMFCButton* pButton,  
    UINT uiState,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки «вкладка».  
  
 [in] `pButton`  
 Указатель на [CMFCButton](../../mfc/reference/cmfcbutton-class.md) объекта. Платформа рисует границу для этого `CMFCButton` экземпляра.  
  
 [in] `uiState`  
 Целое число без знака, указывающее состояние кнопки.  
  
 [in] `pWndTab`  
 Указатель на родительское окно вкладки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном visual manager для настройки внешнего вида границы табулятора.  
  
##  <a name="a-nameondrawtaska--cmfcvisualmanagerondrawtask"></a><a name="ondrawtask"></a>CMFCVisualManager::OnDrawTask  
 Платформа вызывает этот метод при отрисовке [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) объекта.  
  
```  
virtual void OnDrawTask(
    CDC* pDC,  
    CMFCTasksPaneTask* pTask,  
    CImageList* pIcons,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pTask`  
 Указатель на [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md) объекта. Платформа рисует этой задачи.  
  
 [in] `pIcons`  
 Указатель на список изображений, связанных с областью задач. Каждая задача содержит индекс изображения в этом списке.  
  
 [in] `bIsHighlighted`  
 Логический параметр, который указывает, выделен ли отображаемых задач.  
  
 [in] `bIsSelected`  
 Логический параметр, который указывает, выбран ли отображаемых задач.  
  
### <a name="remarks"></a>Примечания  
 Платформа отображаются задачи на панели задач значок и текст. `pIcons` Параметр содержит значок для задачи, обозначенными `pTask`.  
  
 Переопределите этот метод в производном классе, чтобы настроить внешний вид задачи на панели задач.  
  
##  <a name="a-nameondrawtasksgroupareabordera--cmfcvisualmanagerondrawtasksgroupareaborder"></a><a name="ondrawtasksgroupareaborder"></a>CMFCVisualManager::OnDrawTasksGroupAreaBorder  
 Платформа вызывает этот метод, когда он рисует границу вокруг группы на [CMFCTasksPane класса](../../mfc/reference/cmfctaskspane-class.md).  
  
```  
virtual void OnDrawTasksGroupAreaBorder(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE,  
    BOOL bNoTitle = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы области группы в области задач.  
  
 [in] `bSpecial`  
 Логический параметр, который указывает, если выделяется границы. Значение `TRUE` указывает, что выделен границы.  
  
 [in] `bNoTitle`  
 Логический параметр, который указывает, имеет ли область группы заголовок. Значение `TRUE` означает, что в области группы не имеет заголовка.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию в производном классе, чтобы настроить границы вокруг области группы в области задач.  
  
##  <a name="a-nameondrawtasksgroupcaptiona--cmfcvisualmanagerondrawtasksgroupcaption"></a><a name="ondrawtasksgroupcaption"></a>CMFCVisualManager::OnDrawTasksGroupCaption  
 Платформа вызывает этот метод при отрисовке заголовка [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) объекта.  
  
```  
virtual void OnDrawTasksGroupCaption(
    CDC* pDC,  
    CMFCTasksPaneTaskGroup* pGroup,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE,  
    BOOL bCanCollapse = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pGroup`  
 Указатель на объект `CMFCTasksPaneTaskGroup`. Платформа рисует заголовок для этой группы.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли группы.  
  
 [in] `bIsSelected`  
 Логический параметр, указывающий, выделен ли в данный момент группы.  
  
 [in] `bCanCollapse`  
 Логический параметр, указывающий, можно ли свернуть группу.  
  
### <a name="remarks"></a>Примечания  
 Группы задач отображаются на [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) объекта.  
  
 Переопределите этот метод в производном классе, чтобы настроить заголовок для `CMFCTasksPaneTaskGroup`.  
  
##  <a name="a-nameondrawtasksgroupicona--cmfcvisualmanagerondrawtasksgroupicon"></a><a name="ondrawtasksgroupicon"></a>CMFCVisualManager::OnDrawTasksGroupIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawTasksGroupIcon(
    CDC* pDC,  
    CMFCTasksPaneTaskGroup* pGroup,  
    int nIconHOffset = 5,  
    BOOL bIsHighlighted = FALSE,  
    BOOL bIsSelected = FALSE,  
    BOOL bCanCollapse = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pGroup`  
 [in] `nIconHOffset`  
 [in] `bIsHighlighted`  
 [in] `bIsSelected`  
 [in] `bCanCollapse`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondrawtearoffcaptiona--cmfcvisualmanagerondrawtearoffcaption"></a><a name="ondrawtearoffcaption"></a>CMFCVisualManager::OnDrawTearOffCaption  
 Платформа вызывает этот метод при отрисовке заголовка [CMFCPopupMenu класса](../../mfc/reference/cmfcpopupmenu-class.md).  
  
```  
virtual void OnDrawTearOffCaption(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы заголовка.  
  
 [in] `bIsActive`  
 `TRUE`Если заголовок является активным; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается инфраструктурой при `CMFCPopupMenu` объект обрабатывает сообщение WM_PAINT и необходимо нарисовать перемещаемые заголовок.  
  
 Переопределите этот метод в производном классе для настройки внешнего вида заголовков перемещаемые полос.  
  
##  <a name="a-nameondrawtoolboxframea--cmfcvisualmanagerondrawtoolboxframe"></a><a name="ondrawtoolboxframe"></a>CMFCVisualManager::OnDrawToolBoxFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawToolBoxFrame(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonerasemdiclientareaa--cmfcvisualmanageronerasemdiclientarea"></a><a name="onerasemdiclientarea"></a>CMFCVisualManager::OnEraseMDIClientArea  
 Платформа вызывает этот метод, когда она удаляет клиентской области MDI.  
  
```  
virtual BOOL OnEraseMDIClientArea(
    CDC* pDC,  
    CRect rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Прямоугольник, который определяет границы клиентской области MDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зарезервированное значение. Реализация по умолчанию возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для выполнения пользовательского кода при наглядный диспетчер стирает клиентской области MDI.  
  
##  <a name="a-nameonerasepopupwindowbuttona--cmfcvisualmanageronerasepopupwindowbutton"></a><a name="onerasepopupwindowbutton"></a>CMFCVisualManager::OnErasePopupWindowButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnErasePopupWindowButton(
    CDC* pDC,  
    CRect rectClient,  
    CMFCDesktopAlertWndButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rectClient`  
 [in] `pButton`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonerasetabsareaa--cmfcvisualmanageronerasetabsarea"></a><a name="onerasetabsarea"></a>CMFCVisualManager::OnEraseTabsArea  
 Платформа вызывает этот метод, когда она удаляет область вкладки окна вкладку.  
  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы области вкладки.  
  
 [in] `pTabWnd`  
 Указатель на окно вкладки. Платформа удаляет область вкладки для указанной вкладки окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается инфраструктурой при [класса CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объекта процессов `WM_PAINT` сообщение и удаляет область вкладки.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида вкладок.  
  
##  <a name="a-nameonerasetabsbuttona--cmfcvisualmanageronerasetabsbutton"></a><a name="onerasetabsbutton"></a>CMFCVisualManager::OnEraseTabsButton  
 Платформа вызывает этот метод, когда он удаляет текст и значок кнопки вкладки.  
  
```  
virtual void OnEraseTabsButton(
    CDC* pDC,  
    CRect rect,  
    CMFCButton* pButton,  
    CMFCBaseTabCtrl* pWndTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки «вкладка».  
  
 [in] `pButton`  
 Указатель на кнопку вкладку. Платформа удаляет текст и значок для этой кнопки.  
  
 [in] `pWndTab`  
 Указатель вкладок, содержащий табулятора.  
  
### <a name="remarks"></a>Примечания  
 Платформа удаляет текст и значок для кнопки при [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) объекта процессов `WM_ERASEBKGND` сообщение.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида кнопок вкладки.  
  
##  <a name="a-nameonerasetabsframea--cmfcvisualmanageronerasetabsframe"></a><a name="onerasetabsframe"></a>CMFCVisualManager::OnEraseTabsFrame  
 Платформа вызывает этот метод, когда она удаляет кадра на [CMFCBaseTabCtrl класса](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
```  
virtual BOOL OnEraseTabsFrame(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы окна вкладки.  
  
 [in] `pTabWnd`  
 Указатель на окно вкладки. Платформа стирает кадр для этого `CMFCBaseTabCtrl`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод заполняет область обозначается `rect` цветом фона активной вкладки. Вызывается при `CMFCBaseTabCtrl` объекта процессов `WM_PAINT` сообщение и удаляет вкладку кадра.  
  
##  <a name="a-nameonfillautohidebuttonbackgrounda--cmfcvisualmanageronfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a>CMFCVisualManager::OnFillAutoHideButtonBackground  
 Этот метод вызывается платформой при заливке фона кнопки автоматического скрытия.  
  
```  
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,  
    CRect rect,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопка автоматического скрытия.  
  
 [in] `pButton`  
 Указатель на [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) объекта. Автоматически заполняются фона эта кнопка автоматического скрытия.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида кнопки автоматического скрытия.  
  
##  <a name="a-nameonfillbarbackgrounda--cmfcvisualmanageronfillbarbackground"></a><a name="onfillbarbackground"></a>CMFCVisualManager::OnFillBarBackground  
 Платформа вызывает этот метод, когда он заполняет фон [CBasePane](../../mfc/reference/cbasepane-class.md) объекта.  
  
```  
virtual void OnFillBarBackground(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rectClient,  
    CRect rectClip,  
    BOOL bNCArea = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для панели элементов управления.  
  
 [in] `pBar`  
 Указатель на объект `CBasePane`. Автоматически заполняются фон панели.  
  
 [in] `rectClient`  
 Прямоугольник, который определяет границы области.  
  
 [in] `rectClip`  
 Прямоугольник, который указывает область отсечения области.  
  
 [in] `bNCArea`  
 Зарезервированное значение.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод заполняет фона строки, цветом фона 3d из глобальной переменной `afxGlobalData`. Переопределите этот метод в производном диспетчер визуального представления для настройки фона панели.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `OnFillBarBackground` в `CMFCVisualManager` класса. Этот фрагмент кода является частью [Outlook демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#4;](../../mfc/reference/codesnippet/cpp/cmfcvisualmanager-class_2.cpp)]  
  
##  <a name="a-nameonfillbuttoninteriora--cmfcvisualmanageronfillbuttoninterior"></a><a name="onfillbuttoninterior"></a>CMFCVisualManager::OnFillButtonInterior  
 Платформа вызывает этот метод, когда он заполняет фона кнопки панели инструментов.  
  
```  
virtual void OnFillButtonInterior(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства кнопки панели инструментов.  
  
 [in] `pButton`  
 Указатель на [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md). Автоматически заполняются фона для этой кнопки.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки панели инструментов.  
  
 [in] `state`  
 Состояние кнопки панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод использует по умолчанию цвет для заливки фона. Переопределите этот метод в производном диспетчер визуального представления для настройки фона кнопки панели инструментов.  
  
 Возможные состояния кнопки панели инструментов: `ButtonsIsRegular`, `ButtonsIsPressed`, или `ButtonsIsHighlighted`.  
  
##  <a name="a-nameonfillcaptionbarbuttona--cmfcvisualmanageronfillcaptionbarbutton"></a><a name="onfillcaptionbarbutton"></a>CMFCVisualManager::OnFillCaptionBarButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillCaptionBarButton(
    CDC* pDC,  
    CMFCCaptionBar* pBar,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted,  
    BOOL bIsDisabled,  
    BOOL bHasDropDownArrow,  
    BOOL bIsSysButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pBar`  
 [in] `rect`  
 [in] `bIsPressed`  
 [in] `bIsHighlighted`  
 [in] `bIsDisabled`  
 [in] `bHasDropDownArrow`  
 [in] `bIsSysButton`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonfillcommandslistbackgrounda--cmfcvisualmanageronfillcommandslistbackground"></a><a name="onfillcommandslistbackground"></a>CMFCVisualManager::OnFillCommandsListBackground  
 Платформа вызывает этот метод, когда он заполняет фона кнопки панели инструментов, к которой принадлежит список команд. Этот список команд входит в диалоговом окне настройки.  
  
```  
virtual COLORREF OnFillCommandsListBackground(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsSelected = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки.  
  
 [in] `bIsSelected`  
 Логический параметр, указывающий, выбран ли кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текста кнопки панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о списке настройки см. в разделе [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist). Реализация по умолчанию для этого метода заполняет фон на основе цветовой схемы, выбранной в данный момент оболочки.  
  
##  <a name="a-nameonfillheaderctrlbackgrounda--cmfcvisualmanageronfillheaderctrlbackground"></a><a name="onfillheaderctrlbackground"></a>CMFCVisualManager::OnFillHeaderCtrlBackground  
 Платформа вызывает этот метод, когда он заполняет фон элемента управления заголовка.  
  
```  
virtual void OnFillHeaderCtrlBackground(
    CMFCHeaderCtrl* pCtrl,  
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pCtrl`  
 Указатель на [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) объекта. Автоматически заполняются фона для заголовка элемента управления.  
  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который задает границы элемента управления заголовка.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида элемента управления заголовка.  
  
##  <a name="a-nameonfillminiframecaptiona--cmfcvisualmanageronfillminiframecaption"></a><a name="onfillminiframecaption"></a>CMFCVisualManager::OnFillMiniFrameCaption  
 Платформа вызывает этот метод, когда он заполняется заголовок мини-окно.  
  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectCaption`  
 Прямоугольник, который определяет границы заголовка окна.  
  
 [in] `pFrameWnd`  
 Указатель на мини-окно. Платформа рисует строке заголовка окна.  
  
 [in] `bActive`  
 Логический параметр, указывающий, если окно является активным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, используемый для заливки фона заголовка окна.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию для этого метода заполняет заголовок с текущий цвет заголовка активного обложки.  
  
##  <a name="a-nameonfilloutlookbarcaptiona--cmfcvisualmanageronfilloutlookbarcaption"></a><a name="onfilloutlookbarcaption"></a>CMFCVisualManager::OnFillOutlookBarCaption  
 Платформа вызывает этот метод, когда он заполняет фона заголовка Outlook.  
  
```  
virtual void OnFillOutlookBarCaption(
    CDC* pDC,  
    CRect rectCaption,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectCaption`  
 Прямоугольник, который определяет границы заголовка окна.  
  
 [выходной] `clrText`  
 Ссылку на [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр. Метод записывает цвет текста в строке заголовка для данного параметра.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод заполняет заголовок с цвет тени, исходя из текущей обложки. Переопределите этот метод в производном диспетчер визуального представления, чтобы настроить цвет заголовка окна Outlook.  
  
##  <a name="a-nameonfilloutlookpagebuttona--cmfcvisualmanageronfilloutlookpagebutton"></a><a name="onfilloutlookpagebutton"></a>CMFCVisualManager::OnFillOutlookPageButton  
 Платформа вызывает этот метод, когда он заполняет внутреннюю часть страницы кнопка Outlook.  
  
```  
virtual void OnFillOutlookPageButton(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPressed,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы кнопки страницы Outlook.  
  
 [in] `bIsHighlighted`  
 Логический параметр, который указывает, выделен ли кнопки.  
  
 [in] `bIsPressed`  
 Логический параметр, который указывает, является ли кнопка нажата.  
  
 [выходной] `clrText`  
 Ссылку на [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) параметр. Этот метод сохраняет цвет текста кнопки страницы outlook в этом параметре.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию в производном наглядный диспетчер настройки внешнего вида кнопки страницы Outlook.  
  
##  <a name="a-nameonfillpopupwindowbackgrounda--cmfcvisualmanageronfillpopupwindowbackground"></a><a name="onfillpopupwindowbackground"></a>CMFCVisualManager::OnFillPopupWindowBackground  
 Платформа вызывает этот метод, когда он заполняет фон всплывающего окна.  
  
```  
virtual void OnFillPopupWindowBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы всплывающего окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида всплывающих окон.  
  
##  <a name="a-nameonfillribbonbuttona--cmfcvisualmanageronfillribbonbutton"></a><a name="onfillribbonbutton"></a>CMFCVisualManager::OnFillRibbonButton  
 Платформа вызывает этот метод, когда он заполняет внутреннюю часть кнопки на ленте.  
  
```  
virtual COLORREF OnFillRibbonButton(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) объекта. Платформа заполняет внутреннюю часть этой кнопки ленты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текста для кнопки ленты, определяемой параметром `pButton` Если кнопка ленты поддерживает текст. Значение -1, если недопустимый текст для кнопки ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида кнопок ленты.  
  
##  <a name="a-nameonfillribbonedita--cmfcvisualmanageronfillribbonedit"></a><a name="onfillribbonedit"></a>CMFCVisualManager::OnFillRibbonEdit  
 Платформа вызывает этот метод, когда он заполняет внутреннюю часть экземпляра `CMFCRibbonRichEditCtrl` класса.  
  
```  
virtual void OnFillRibbonEdit(
    CDC* pDC,  
    CMFCRibbonRichEditCtrl* pEdit,  
    CRect rect,  
    BOOL bIsHighlighted,  
    BOOL bIsPaneHighlighted,  
    BOOL bIsDisabled,  
    COLORREF& clrText,  
    COLORREF& clrSelBackground,  
    COLORREF& clrSelText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pEdit`  
 Указатель на объект `CMFCRibbonRichEditCtrl`. Платформа заполняет внутреннюю часть этого элемента управления редактированием.  
  
 [in] `rect`  
 Прямоугольник, который задает границы элемента управления.  
  
 [in] `bIsHighlighted`  
 Логический параметр, указывающий, выделен ли элемент управления для редактирования.  
  
 [in] `bIsPaneHighlighted`  
 Логический параметр, указывающий, выделен ли в родительской области.  
  
 [in] `bIsDisabled`  
 Логический параметр, который указывает, является ли элемент управления для редактирования недоступен.  
  
 [in] `clrText`  
 Ссылка на цвет текста элемента управления.  
  
 [in] `clrSelBackground`  
 Ссылка на цвет фона элемента управления поля ввода, когда он выделен.  
  
 [in] `clrSelText`  
 Ссылка на цвет выбранного текста в элемент управления для редактирования.  
  
### <a name="remarks"></a>Примечания  
 `CMFCRibbonRichEditCtrl` Обозначается `pEdit` может быть частью кнопки поля со списком на ленте.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида `CMFCRibbonRichEditCtrl`.  
  
##  <a name="a-nameonfillribbonmainpanelbuttona--cmfcvisualmanageronfillribbonmainpanelbutton"></a><a name="onfillribbonmainpanelbutton"></a>CMFCVisualManager::OnFillRibbonMainPanelButton  
 Платформа вызывает этот метод, когда он заполняет внутреннюю часть кнопки ленты, расположенной на **Main** панель.  
  
```  
virtual COLORREF OnFillRibbonMainPanelButton(
    CDC* pDC,  
    CMFCRibbonButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pButton`  
 Указатель на [CMFCRibbonButton класс](../../mfc/reference/cmfcribbonbutton-class.md) объекта. Автоматически заполняются эта кнопка на ленте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет текста для кнопки ленты, определяемой параметром `pButton` Если кнопка ленты поддерживает текст. Значение -1, если недопустимый текст для кнопки ленты.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида кнопок ленты на **Main** панель.  
  
##  <a name="a-nameonfillribbonmenuframea--cmfcvisualmanageronfillribbonmenuframe"></a><a name="onfillribbonmenuframe"></a>CMFCVisualManager::OnFillRibbonMenuFrame  
 Платформа вызывает этот метод, когда он заполняет фрейм меню панели ленты.  
  
```  
virtual void OnFillRibbonMenuFrame(
    CDC* pDC,  
    CMFCRibbonMainPanel* pPanel,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pPanel`  
 Указатель на экземпляр [CMFCRibbonMainPanel класса](../../mfc/reference/cmfcribbonmainpanel-class.md). Автоматически заполняются рамки меню для этой панели ленты.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы рамки меню.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида меню для `CMFCRibbonMainPanel`.  
  
##  <a name="a-nameonfillribbonquickaccesstoolbarpopupa--cmfcvisualmanageronfillribbonquickaccesstoolbarpopup"></a><a name="onfillribbonquickaccesstoolbarpopup"></a>CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnFillRibbonQuickAccessToolBarPopup(
    CDC* pDC,  
    CMFCRibbonPanelMenuBar* pMenuBar,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `pMenuBar`  
 [in] `rect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonfillsplitterbackgrounda--cmfcvisualmanageronfillsplitterbackground"></a><a name="onfillsplitterbackground"></a>CMFCVisualManager::OnFillSplitterBackground  
 Платформа вызывает этот метод, когда он заполняет фон окна-разделителя.  
  
```  
virtual void OnFillSplitterBackground(
    CDC* pDC,  
    CSplitterWndEx* pSplitterWnd,  
    CRect rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pSplitterWnd`  
 Указатель на экземпляр [CSplitterWndEx класса](csplitterwndex-class.md). Автоматически заполняются фона для окна-разделителя.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы окна-разделителя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида окна-разделителя.  
  
##  <a name="a-nameonfilltaba--cmfcvisualmanageronfilltab"></a><a name="onfilltab"></a>CMFCVisualManager::OnFillTab  
 Платформа вызывает этот метод, когда он заполняет фон вкладки окна.  
  
```  
virtual void OnFillTab(
    CDC* pDC,  
    CRect rectFill,  
    CBrush* pbrFill,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectFill`  
 Прямоугольник, который определяет границы окна вкладки.  
  
 [in] `pbrFill`  
 Указатель кисти. Платформа использует данную кисть для заполнения окна вкладки.  
  
 [in] `iTab`  
 Вкладка отсчитываемый от нуля индекс вкладки, для которого автоматически заполняются фона.  
  
 [in] `bIsActive`  
 `TRUE`Если активна вкладка; в противном случае `FALSE`.  
  
 [in] `pTabWnd`  
 Указатель на родительский элемент управления вкладки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида вкладок.  
  
##  <a name="a-nameonfilltasksgroupinteriora--cmfcvisualmanageronfilltasksgroupinterior"></a><a name="onfilltasksgroupinterior"></a>CMFCVisualManager::OnFillTasksGroupInterior  
 Платформа вызывает этот метод, когда он заполняет внутреннюю часть [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) объекта.  
  
```  
virtual void OnFillTasksGroupInterior(
    CDC* pDC,  
    CRect rect,  
    BOOL bSpecial = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Прямоугольник, который определяет границы группы задач.  
  
 [in] `bSpecial`  
 Логическое значение, указывающее, если внутренняя область заполняется специальные цветом.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида группы задач.  
  
##  <a name="a-nameonfilltaskspanebackgrounda--cmfcvisualmanageronfilltaskspanebackground"></a><a name="onfilltaskspanebackground"></a>CMFCVisualManager::OnFillTasksPaneBackground  
 Платформа вызывает этот метод, когда он заполняет фон [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) управления.  
  
```  
virtual void OnFillTasksPaneBackground(
    CDC* pDC,  
    CRect rectWorkArea);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectWorkArea`  
 Прямоугольник, который определяет границы области задач.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида `CMFCTasksPane` объекта.  
  
##  <a name="a-nameonhighlightmenuitema--cmfcvisualmanageronhighlightmenuitem"></a><a name="onhighlightmenuitem"></a>CMFCVisualManager::OnHighlightMenuItem  
 Платформа вызывает этот метод при отрисовке выделенные меню.  
  
```  
virtual void OnHighlightMenuItem(
    CDC* pDC,  
    CMFCToolBarMenuButton* pButton,  
    CRect rect,  
    COLORREF& clrText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства для меню.  
  
 [in] `pButton`  
 Указатель на [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) для отображения. Реализация по умолчанию этот параметр не используется.  
  
 [in] `rect`  
 Прямоугольник, который задает границы данного элемента меню.  
  
 [in] `clrText`  
 Текущий цвет текста пунктов меню выделенным. Реализация по умолчанию этот параметр не используется.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этот метод не использует параметры `pButton` или `clrText`. Он заполняет прямоугольник, задаваемый параметром `rect` стандартные цвета.  
  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида элементов выделенного меню. Используйте `clrText` параметр изменить цвет текста элемента выделенного меню.  
  
##  <a name="a-nameonhighlightrarelyusedmenuitemsa--cmfcvisualmanageronhighlightrarelyusedmenuitems"></a><a name="onhighlightrarelyusedmenuitems"></a>CMFCVisualManager::OnHighlightRarelyUsedMenuItems  
 Платформа вызывает этот метод при отрисовке выделенного меню команды.  
  
```  
virtual void OnHighlightRarelyUsedMenuItems(
    CDC* pDC,  
    CRect rectRarelyUsed);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectRarelyUsed`  
 Прямоугольник, который определяет границы выделенной команды.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном диспетчер визуального представления для настройки внешнего вида выделенного меню команд.  
  
##  <a name="a-nameonncactivatea--cmfcvisualmanageronncactivate"></a><a name="onncactivate"></a>CMFCVisualManager::OnNcActivate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnNcActivate(
    CWnd* pWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 [in] `bActive`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonncpainta--cmfcvisualmanageronncpaint"></a><a name="onncpaint"></a>CMFCVisualManager::OnNcPaint  
 Платформа вызывает этот метод при отрисовке Неклиентская область.  
  
```  
virtual BOOL OnNcPaint(
    CWnd* pWnd,  
    const CObList& lstSysButtons,  
    CRect rectRedraw);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на окно которого неклиентской области рисует платформы.  
  
 [in] `lstSysButtons`  
 Список кнопок системы. Они также известны как кнопки заголовка.  
  
 [in] `rectRedraw`  
 Прямоугольник, который определяет границы неклиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Зарезервированное значение. Реализация по умолчанию возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном наглядный диспетчер настройки внешнего вида кнопки кадра и заголовок окна.  
  
##  <a name="a-nameonsetwindowregiona--cmfcvisualmanageronsetwindowregion"></a><a name="onsetwindowregion"></a>CMFCVisualManager::OnSetWindowRegion  
 Платформа вызывает этот метод после установки область, содержащую кадров и во всплывающих меню.  
  
```  
virtual BOOL OnSetWindowRegion(
    CWnd* pWnd,  
    CSize sizeWindow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на окно с регионом, изменен.  
  
 [in] `sizeWindow`  
 Размер окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для уведомления диспетчер визуального представления, установил регион для кадров и во всплывающих меню. Дополнительные сведения см. в разделе [CWindow::SetWindowRgn](../../atl/reference/cwindow-class.md#setwindowrgn).  
  
##  <a name="a-nameonupdatesystemcolorsa--cmfcvisualmanageronupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>CMFCVisualManager::OnUpdateSystemColors  
 Платформа вызывает эту функцию при его изменении системных цветов.  
  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод как часть обработки `WM_SYSCOLORCHANGE` сообщение. Реализация по умолчанию не выполняет никаких действий. Переопределите этот метод в производном диспетчер визуального представления, если вы хотите выполнять пользовательский код при изменении цветов в приложении.  
  
##  <a name="a-nameredrawalla--cmfcvisualmanagerredrawall"></a><a name="redrawall"></a>CMFCVisualManager::RedrawAll  
 Немедленно перерисовывает панелей элементов управления в приложении.  
  
```  
static void RedrawAll();
```  
  
##  <a name="a-nameribboncategorycolortorgba--cmfcvisualmanagerribboncategorycolortorgb"></a><a name="ribboncategorycolortorgb"></a>CMFCVisualManager::RibbonCategoryColorToRGB  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF RibbonCategoryColorToRGB(AFX_RibbonCategoryColor color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetdefaultmanagera--cmfcvisualmanagersetdefaultmanager"></a><a name="setdefaultmanager"></a>CMFCVisualManager::SetDefaultManager  
 Задает диспетчер по умолчанию.  
  
```  
static void SetDefaultManager(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTI`  
 Указатель на данные времени выполнения для диспетчер визуального представления.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CMFCVisualManager` класса и его производных диспетчеров визуального представления для настройки внешнего вида приложения. После выбора наглядный диспетчер по умолчанию, этот метод перерисовывает приложения, используя новый диспетчер визуального представления. Дополнительные сведения об использовании диспетчеров визуального представления см. в разделе [диспетчер визуализации](../../mfc/visualization-manager.md).  
  
 Этот метод можно используйте для изменения диспетчер визуального представления, используемых приложением.  
  
##  <a name="a-namesetembossdisabledimagea--cmfcvisualmanagersetembossdisabledimage"></a><a name="setembossdisabledimage"></a>CMFCVisualManager::SetEmbossDisabledImage  
 Включает или отключает выступающая режим для изображений отключено панели инструментов.  
  
```  
void SetEmbossDisabledImage (BOOL bEmboss = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEmboss`  
 Логический параметр, который указывает, следует ли включить выступающая режим для изображений отключено панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Используйте функцию [CMFCVisualManager::IsEmbossDisabledImage](#isembossdisabledimage) для определения, включен ли режим приподнятости.  
  
##  <a name="a-namesetfadeinactiveimagea--cmfcvisualmanagersetfadeinactiveimage"></a><a name="setfadeinactiveimage"></a>CMFCVisualManager::SetFadeInactiveImage  
 Включает или отключает эффект освещения для неактивных изображения в меню или панели инструментов.  
  
```  
void SetFadeInactiveImage(BOOL bFade = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bFade`  
 Логический параметр, который указывает, следует ли включить эффект освещения.  
  
### <a name="remarks"></a>Примечания  
 Этот компонент определяет ли неактивных изображения появляются проявление меню или панели инструментов. Используйте метод [CMFCVisualManager::IsFadeInactiveImage](#isfadeinactiveimage) , чтобы определить, включена ли эта функция.  
  
##  <a name="a-namesetmenuflatlooka--cmfcvisualmanagersetmenuflatlook"></a><a name="setmenuflatlook"></a>CMFCVisualManager::SetMenuFlatLook  
 Задает флаг, указывающий, будут ли отображаться плоскими кнопки меню. В противном случае они отображаются трехмерные.  
  
```  
void SetMenuFlatLook(BOOL bMenuFlatLook = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMenuFlatLook`  
 Логический параметр, указывающий, будут ли отображаться плоскими кнопки меню.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция не включена.  
  
##  <a name="a-namesetmenushadowdeptha--cmfcvisualmanagersetmenushadowdepth"></a><a name="setmenushadowdepth"></a>CMFCVisualManager::SetMenuShadowDepth  
 Задает ширину и высоту меню тени.  
  
```  
void SetMenuShadowDepth(int nDepth);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nDepth`  
 Целое число, указывающее глубину меню тени в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Высота и ширина тени меню должны совпадать. Значение по умолчанию — 7 пикселей.  
  
##  <a name="a-namesetshadowhighlightedimagea--cmfcvisualmanagersetshadowhighlightedimage"></a><a name="setshadowhighlightedimage"></a>CMFCVisualManager::SetShadowHighlightedImage  
 Задает флаг, указывающий, является ли [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md) отображает тени для выделенного изображения.  
  
```  
void SetShadowHighlightedImage(BOOL bShadow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShadow`  
 Логический параметр, указывающий, отображается ли диспетчер визуального представления тень под выделенным изображениями.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот компонент отключен.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager::GetInstance](#getinstance)   
 [Диспетчер визуализации](../../mfc/visualization-manager.md)



