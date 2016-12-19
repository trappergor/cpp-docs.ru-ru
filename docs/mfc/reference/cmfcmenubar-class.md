---
title: "CMFCMenuBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuBar class"
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMenuBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Строка меню, закрепление инструментов.  
  
## Синтаксис  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMenuBar::AdjustLocations](../Topic/CMFCMenuBar::AdjustLocations.md)|\(Переопределяет `CMFCToolBar::AdjustLocations`\).|  
|[CMFCMenuBar::AllowChangeTextLabels](../Topic/CMFCMenuBar::AllowChangeTextLabels.md)|Указывает, будут ли текстовые подписи можно отобразить с образами в кнопках панели инструментов.  \(Переопределяет [CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)\).|  
|[CMFCMenuBar::AllowShowOnPaneMenu](../Topic/CMFCMenuBar::AllowShowOnPaneMenu.md)|\(Переопределяет `CPane::AllowShowOnPaneMenu`\).|  
|[CMFCMenuBar::CalcFixedLayout](../Topic/CMFCMenuBar::CalcFixedLayout.md)|Вычисляет горизонтальный размер панели инструментов.  \(Переопределяет [CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)\).|  
|[CMFCMenuBar::CalcLayout](../Topic/CMFCMenuBar::CalcLayout.md)|\(Переопределяет `CMFCToolBar::CalcLayout`\).|  
|[CMFCMenuBar::CalcMaxButtonHeight](../Topic/CMFCMenuBar::CalcMaxButtonHeight.md)|Вычисляет максимальную высоту кнопок на панели инструментов.  \(Переопределяет [CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)\).|  
|[CMFCMenuBar::CanBeClosed](../Topic/CMFCMenuBar::CanBeClosed.md)|Указывает, может ли пользователь закрыть панель инструментов.  \(Переопределяет [CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)\).|  
|[CMFCMenuBar::CanBeRestored](../Topic/CMFCMenuBar::CanBeRestored.md)|Определяет, может ли система получить панели инструментов в исходное состояние после настройки.  \(Переопределяет [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)\).|  
|[CMFCMenuBar::Create](../Topic/CMFCMenuBar::Create.md)|Создает элемент управления меню и вложение его к объекту `CMFCMenuBar`.|  
|[CMFCMenuBar::CreateEx](../Topic/CMFCMenuBar::CreateEx.md)|Создает объект `CMFCMenuBar` с дополнительными параметрами стиля.|  
|[CMFCMenuBar::CreateFromMenu](../Topic/CMFCMenuBar::CreateFromMenu.md)|Инициализирует объект `CMFCMenuBar`.  Принимает параметр `HMENU`, который выступает в качестве шаблона заполняется автоматически в соответствии `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](../Topic/CMFCMenuBar::EnableHelpCombobox.md)|Включает поле со списком **Справка**, найдено с правой стороны строки меню.|  
|[CMFCMenuBar::EnableMenuShadows](../Topic/CMFCMenuBar::EnableMenuShadows.md)|Указывает, нужно ли отображать тени для всплывающих меню.|  
|[CMFCMenuBar::GetAvailableExpandSize](../Topic/CMFCMenuBar::GetAvailableExpandSize.md)|\(Переопределяет [CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md)\).|  
|[CMFCMenuBar::GetColumnWidth](../Topic/CMFCMenuBar::GetColumnWidth.md)|Возвращает ширину кнопки панели инструментов.  \(Переопределяет [CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)\).|  
|[CMFCMenuBar::GetDefaultMenu](../Topic/CMFCMenuBar::GetDefaultMenu.md)|Возвращает дескриптор к исходному меню в файле ресурсов.|  
|[CMFCMenuBar::GetDefaultMenuResId](../Topic/CMFCMenuBar::GetDefaultMenuResId.md)|Возвращает идентификатор ресурса для исходного меню в файле ресурсов.|  
|[CMFCMenuBar::GetFloatPopupDirection](../Topic/CMFCMenuBar::GetFloatPopupDirection.md)||  
|[CMFCMenuBar::GetForceDownArrows](../Topic/CMFCMenuBar::GetForceDownArrows.md)||  
|[CMFCMenuBar::GetHelpCombobox](../Topic/CMFCMenuBar::GetHelpCombobox.md)|Возвращает указатель на поле со списком **Справка**.|  
|[CMFCMenuBar::GetHMenu](../Topic/CMFCMenuBar::GetHMenu.md)|Возвращает дескриптор меню, присоединяется к объекту `CMFCMenuBar`.|  
|[CMFCMenuBar::GetMenuFont](../Topic/CMFCMenuBar::GetMenuFont.md)|Возвращает текущий шрифт меню для глобальных объектов.|  
|[CMFCMenuBar::GetMenuItem](../Topic/CMFCMenuBar::GetMenuItem.md)|Возвращает кнопку панели инструментов, связанную с предоставленным индекс элемента.|  
|[CMFCMenuBar::GetRowHeight](../Topic/CMFCMenuBar::GetRowHeight.md)|Возвращает высоту кнопок панели инструментов.  \(Переопределяет [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)\).|  
|[CMFCMenuBar::GetSystemButton](../Topic/CMFCMenuBar::GetSystemButton.md)||  
|[CMFCMenuBar::GetSystemButtonsCount](../Topic/CMFCMenuBar::GetSystemButtonsCount.md)||  
|[CMFCMenuBar::GetSystemMenu](../Topic/CMFCMenuBar::GetSystemMenu.md)||  
|[CMFCMenuBar::HighlightDisabledItems](../Topic/CMFCMenuBar::HighlightDisabledItems.md)|Указывает, следует ли выделены отключенные пунктов меню.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](../Topic/CMFCMenuBar::IsButtonExtraSizeAvailable.md)|Определяет, является ли панель инструментов может отображаться кнопки, удлиняли границы.  \(Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)\).|  
|[CMFCMenuBar::IsHighlightDisabledItems](../Topic/CMFCMenuBar::IsHighlightDisabledItems.md)|Указывает, следует ли выделены отключенные элементы.|  
|[CMFCMenuBar::IsMenuShadows](../Topic/CMFCMenuBar::IsMenuShadows.md)|Указывает, следует ли нарисована тени для всплывающих меню.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](../Topic/CMFCMenuBar::IsRecentlyUsedMenus.md)|Указывает, отображаются ли использовавшиеся команды меню в строке меню.|  
|[CMFCMenuBar::IsShowAllCommands](../Topic/CMFCMenuBar::IsShowAllCommands.md)|Указывает, отображаются ли всплывающие меню все команды.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](../Topic/CMFCMenuBar::IsShowAllCommandsDelay.md)|Указывает, отображаются ли все команды меню после небольшой задержки.|  
|[CMFCMenuBar::LoadState](../Topic/CMFCMenuBar::LoadState.md)|Загружает состояние объекта `CMFCMenuBar` из реестра.|  
|[CMFCMenuBar::OnChangeHot](../Topic/CMFCMenuBar::OnChangeHot.md)|Вызываемый платформой, когда пользователь выбирает кнопку на панели инструментов.  \(Переопределяет [CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)\).|  
|[CMFCMenuBar::OnDefaultMenuLoaded](../Topic/CMFCMenuBar::OnDefaultMenuLoaded.md)|Вызываемый платформой, когда фреймовое окно загрузит по умолчанию меню из файла ресурсов.|  
|[CMFCMenuBar::OnSendCommand](../Topic/CMFCMenuBar::OnSendCommand.md)|\(Переопределяет `CMFCToolBar::OnSendCommand`\).|  
|[CMFCMenuBar::OnSetDefaultButtonText](../Topic/CMFCMenuBar::OnSetDefaultButtonText.md)|Вызываемый платформой, когда меню в режиме настройки и пользователь изменяет текст пункта меню.|  
|[CMFCMenuBar::OnToolHitTest](../Topic/CMFCMenuBar::OnToolHitTest.md)|\(Переопределяет `CMFCToolBar::OnToolHitTest`\).|  
|[CMFCMenuBar::PreTranslateMessage](../Topic/CMFCMenuBar::PreTranslateMessage.md)|\(Переопределяет `CMFCToolBar::PreTranslateMessage`\).|  
|[CMFCMenuBar::RestoreOriginalstate](../Topic/CMFCMenuBar::RestoreOriginalstate.md)|Вызываемый платформой, когда меню в режиме настройки, и пользователя, выберите **Сброс** для строки меню.|  
|[CMFCMenuBar::SaveState](../Topic/CMFCMenuBar::SaveState.md)|Сохраняет состояние объекта `CMFCMenuBar` в реестр.|  
|[CMFCMenuBar::SetDefaultMenuResId](../Topic/CMFCMenuBar::SetDefaultMenuResId.md)|Устанавливает исходную меню в файле ресурсов.|  
|[CMFCMenuBar::SetForceDownArrows](../Topic/CMFCMenuBar::SetForceDownArrows.md)||  
|[CMFCMenuBar::SetMaximizeMode](../Topic/CMFCMenuBar::SetMaximizeMode.md)|Вызываемый платформой, когда дочернее окно MDI изменяет свой режим отображения.  Если дочернее окно MDI вновь развернуто больше не развернуто, то обновления данного метода строки меню.|  
|[CMFCMenuBar::SetMenuButtonRTC](../Topic/CMFCMenuBar::SetMenuButtonRTC.md)|Устанавливает данные времени выполнения класса, которое создается, когда пользователь динамически создает кнопки меню.|  
|[CMFCMenuBar::SetMenuFont](../Topic/CMFCMenuBar::SetMenuFont.md)|Задает шрифт для всех меню в приложении.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](../Topic/CMFCMenuBar::SetRecentlyUsedMenus.md)|Определяет, указывает ли строка меню, использовавшиеся команды меню.|  
|[CMFCMenuBar::SetShowAllCommands](../Topic/CMFCMenuBar::SetShowAllCommands.md)|Определяет, указывает ли строка меню все команды.|  
  
## Заметки  
 Класс `CMFCMenuBar` строка меню, средства закрепляющего функциональные возможности.  Он похож на панель инструментов, хотя его нельзя закрыть \- он всегда отображается.  
  
 `CMFCMenuBar` поддерживает параметр отображения недавно используемых объектов пункта меню.  Если этот параметр включен, то `CMFCMenuBar` отображаются только подмножество доступных команд на первом просмотре.  Таким образом, использовавшиеся команды отображаются вместе с первоначальным подмножеством команд.  Кроме того, пользователь всегда может развернуть меню, чтобы просмотреть все доступные команды.  Таким образом, каждая команда настроитьа доступная для константу, указывающую или отображать только в том случае, если она недавно была выделена.  
  
 Чтобы использовать объект `CMFCMenuBar`, внедрение его в объекте фрейма главного окна.  При обработке сообщения `WM_CREATE`, вызовите `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`.  Независимо от того, что создает функцию использовании передайте указатель к главному фреймовому окно.  Затем включение закрепления путем вызова [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md).  Закрепите это меню путем вызова [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md).  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCMenuBar`.  Примере показано, как задать стиль панели включить кнопку настройки, чтобы включить средство просмотра Справки, чтобы включить тени для всплывающих меню и обновить строку меню.  Этот фрагмент кода является частью [Пример demo IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/CPP/cmfcmenubar-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)  
  
## Требования  
 **заголовок:** afxmenubar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)