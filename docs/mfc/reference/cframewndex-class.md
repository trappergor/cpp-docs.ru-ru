---
title: "CFrameWndEx Class | Microsoft Docs"
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
  - "CFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWndEx class"
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функциональность фреймового окна интерфейса одинарного документа Windows \(SDI\) или перекрывающихся контекстного меню и предоставляет члены для управления окна.  Он расширяет класс [CFrameWnd](../../mfc/reference/cframewnd-class.md).  
  
## Синтаксис  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](../Topic/CFrameWndEx::ActiveItemRecalcLayout.md)|Обрабатывает структуру элемента клиента OLE и клиентской области фреймов.|  
|`CFrameWndEx::AddDockSite`|Этот метод не используется.|  
|[CFrameWndEx::AddPane](../Topic/CFrameWndEx::AddPane.md)|Регистрирует область элементов управления с диспетчером закрепления.|  
|[CFrameWndEx::AdjustDockingLayout](../Topic/CFrameWndEx::AdjustDockingLayout.md)|Повторно вычисляет макет всех панелей, закреплены к фреймовому окно.|  
|[CFrameWndEx::DelayUpdateFrameMenu](../Topic/CFrameWndEx::DelayUpdateFrameMenu.md)|Устанавливает меню, а затем обновления кадра его при обработке команды бездействует.|  
|[CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md)|Закрепит указанная область в фреймовому окно.|  
|[CFrameWndEx::DockPaneLeftOf](../Topic/CFrameWndEx::DockPaneLeftOf.md)|Закрепления одна область слева от другой области.|  
|[CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md)|Включает режим автоматического скрытия для панелей, когда они закреплены с указанным сторонам главного фреймового окна.|  
|[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)|Включает закрепления панелей, принадлежащих фреймовому окно.|  
|[CFrameWndEx::EnableFullScreenMainMenu](../Topic/CFrameWndEx::EnableFullScreenMainMenu.md)|Отображать или скрывать главное меню в режиме " во весь экран.|  
|[CFrameWndEx::EnableFullScreenMode](../Topic/CFrameWndEx::EnableFullScreenMode.md)|Включает полноэкранный режим, фреймового окна.|  
|[CFrameWndEx::EnableLoadDockState](../Topic/CFrameWndEx::EnableLoadDockState.md)|Включение или отключение загрузки состояния закрепления.|  
|[CFrameWndEx::EnablePaneMenu](../Topic/CFrameWndEx::EnablePaneMenu.md)|Позволяет включить или отключить автоматическую обработку меню панели.|  
|[CFrameWndEx::GetActivePopup](../Topic/CFrameWndEx::GetActivePopup.md)|Возвращает указатель на текущий момент, показанному всплывающему меню.|  
|[CFrameWndEx::GetDefaultResId](../Topic/CFrameWndEx::GetDefaultResId.md)|Возвращает идентификатор ресурса, который был указан при нагрузили фреймовое окно границы.|  
|[CFrameWndEx::GetDockingManager](../Topic/CFrameWndEx::GetDockingManager.md)|Извлекает объект [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) для фреймового окна.|  
|[CFrameWndEx::GetMenuBar](../Topic/CFrameWndEx::GetMenuBar.md)|Возвращает указатель на вложенный объект строки меню в фреймовому окно.|  
|[CFrameWndEx::GetPane](../Topic/CFrameWndEx::GetPane.md)|Возвращает указатель на панели, имеющего указанный идентификатор.|  
|[CFrameWndEx::GetRibbonBar](../Topic/CFrameWndEx::GetRibbonBar.md)|Извлекает элемент управления ленты для кадра.|  
|[CFrameWndEx::GetTearOffBars](../Topic/CFrameWndEx::GetTearOffBars.md)|Возвращает список объектов области, в перемещаемом состоянии.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](../Topic/CFrameWndEx::GetToolbarButtonToolTipText.md)|Вызываемый платформой, когда приложение отображает подсказки для кнопки панели инструментов.|  
|[CFrameWndEx::InsertPane](../Topic/CFrameWndEx::InsertPane.md)|Регистрирует область с диспетчером закрепления.|  
|[CFrameWndEx::IsFullScreen](../Topic/CFrameWndEx::IsFullScreen.md)|Определяет, является ли фреймовое окно находится в режиме " во весь экран.|  
|[CFrameWndEx::IsMenuBarAvailable](../Topic/CFrameWndEx::IsMenuBarAvailable.md)|Определяет, находится ли указатель на объект строки меню является допустимым.|  
|[CFrameWndEx::IsPointNearDockSite](../Topic/CFrameWndEx::IsPointNearDockSite.md)|Указывает, найдено ли точка в зоне выравнивания.|  
|[CFrameWndEx::IsPrintPreview](../Topic/CFrameWndEx::IsPrintPreview.md)|Указывает, является ли фреймовое окно находится в режиме предварительного просмотра.|  
|[CFrameWndEx::LoadFrame](../Topic/CFrameWndEx::LoadFrame.md)|Этот метод вызывается после проектирования для создания фреймовое окно и загрузить его ресурсам.|  
|[CFrameWndEx::NegotiateBorderSpace](../Topic/CFrameWndEx::NegotiateBorderSpace.md)|Согласование клиентских инструментов " границы OLE.|  
|[CFrameWndEx::OnActivate](../Topic/CFrameWndEx::OnActivate.md)|Платформа вызывает этот метод, когда входные данные пользователя переключается на или с кадром.|  
|[CFrameWndEx::OnActivateApp](../Topic/CFrameWndEx::OnActivateApp.md)|Вызываемый платформой, когда будет выделен или невыбранное или приложение.|  
|[CFrameWndEx::OnChangeVisualManager](../Topic/CFrameWndEx::OnChangeVisualManager.md)|Вызываемый платформой, если изменение потребует изменения к кадру диспетчеру визуального представления.|  
|[CFrameWndEx::OnClose](../Topic/CFrameWndEx::OnClose.md)|Границы вызывают этот метод, чтобы закрыть кадр.|  
|[CFrameWndEx::OnCloseDockingPane](../Topic/CFrameWndEx::OnCloseDockingPane.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Закрыть** на панели закрепления.|  
|[CFrameWndEx::OnCloseMiniFrame](../Topic/CFrameWndEx::OnCloseMiniFrame.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Закрыть** на фреймовом окне плавающей запятой миниом.|  
|[CFrameWndEx::OnClosePopupMenu](../Topic/CFrameWndEx::OnClosePopupMenu.md)|Вызываемый платформой, когда контекстное меню меню активного отображает сообщение WM\_DESTROY.|  
|[CFrameWndEx::OnCmdMsg](../Topic/CFrameWndEx::OnCmdMsg.md)|Сообщения команды диспетчеров.|  
|[CFrameWndEx::OnContextHelp](../Topic/CFrameWndEx::OnContextHelp.md)|Связанные с платформой для отображения контекста справки.|  
|[CFrameWndEx::OnCreate](../Topic/CFrameWndEx::OnCreate.md)|Вызываемый средой после кадра создать.|  
|[CFrameWndEx::OnDestroy](../Topic/CFrameWndEx::OnDestroy.md)|Вызываемый платформой, когда фрейм будет уничтожен.|  
|[CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md)|Вызываемый платформой, когда приложение строит образ, связанный с пунктом меню.|  
|[CFrameWndEx::OnDrawMenuLogo](../Topic/CFrameWndEx::OnDrawMenuLogo.md)|Вызываемый платформой, когда объект `CMFCPopupMenu` отображает сообщение [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213).|  
|[CFrameWndEx::OnDWMCompositionChanged](../Topic/CFrameWndEx::OnDWMCompositionChanged.md)|Вызываемый платформой, когда была включена или отключена композиция диспетчер окон рабочего стола \(диспетчер окон рабочего стола\).|  
|[CFrameWndEx::OnExitSizeMove](../Topic/CFrameWndEx::OnExitSizeMove.md)|Вызываемый платформой, когда фрейм останавливает перемещение или изменение размера.|  
|[CFrameWndEx::OnGetMinMaxInfo](../Topic/CFrameWndEx::OnGetMinMaxInfo.md)|Вызываемый платформой, когда фрейм будет размер для задания ограничения размеры окна.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](../Topic/CFrameWndEx::OnIdleUpdateCmdUI.md)|Вызываемый платформой, чтобы обновить отображение кадра при обработке команды бездействует.|  
|[CFrameWndEx::OnLButtonDown](../Topic/CFrameWndEx::OnLButtonDown.md)|Платформа вызывает этот метод, когда пользователь нажимает нажатие левой кнопки мыши.|  
|[CFrameWndEx::OnLButtonUp](../Topic/CFrameWndEx::OnLButtonUp.md)|Платформа вызывает этот метод, когда пользователь освобождает нажатие левой кнопки мыши.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](../Topic/CFrameWndEx::OnMenuButtonToolHitTest.md)|Вызываемый платформой, когда объект `CMFCToolBarButton` отображает сообщение `WM_NCHITTEST`.|  
|[CFrameWndEx::OnMenuChar](../Topic/CFrameWndEx::OnMenuChar.md)|Вызываемый платформой, когда меню отображается, и пользователь нажимает ключ, который не соответствует команде.|  
|[CFrameWndEx::OnMouseMove](../Topic/CFrameWndEx::OnMouseMove.md)|Платформа вызывает этот метод, когда указатель перемещается.|  
|[CFrameWndEx::OnMoveMiniFrame](../Topic/CFrameWndEx::OnMoveMiniFrame.md)|Если окно панель с границами.|  
|[CFrameWndEx::OnNcActivate](../Topic/CFrameWndEx::OnNcActivate.md)|Вызываемый платформой, когда область кадра, отличного от клиента должен перерисовать, чтобы показать изменения в активном состоянии.|  
|[CFrameWndEx::OnNcCalcSize](../Topic/CFrameWndEx::OnNcCalcSize.md)|Вызываемый платформой, когда размер и положение клиентской области необходимо вычислить.|  
|[CFrameWndEx::OnNcHitTest](../Topic/CFrameWndEx::OnNcHitTest.md)|Вызываемый платформой, когда указатель перемещается или когда нажата кнопка мыши или освобождено.|  
|[CFrameWndEx::OnNcMouseMove](../Topic/CFrameWndEx::OnNcMouseMove.md)|Вызываемый платформой, когда указатель перемещается в области клиента, не являющегося.|  
|[CFrameWndEx::OnNcPaint](../Topic/CFrameWndEx::OnNcPaint.md)|Вызываемый платформой, когда область клиента, не являющегося необходимости рисования.|  
|[CFrameWndEx::OnPaneCheck](../Topic/CFrameWndEx::OnPaneCheck.md)|Вызываемый платформой для контроля видимости области.|  
|[CFrameWndEx::OnPostPreviewFrame](../Topic/CFrameWndEx::OnPostPreviewFrame.md)|Вызываемый платформой, когда пользователь изменяет режим предварительного просмотра.|  
|[CFrameWndEx::OnPowerBroadcast](../Topic/CFrameWndEx::OnPowerBroadcast.md)|Вызываемый платформой, когда событие управления питанием.|  
|[CFrameWndEx::OnSetMenu](../Topic/CFrameWndEx::OnSetMenu.md)|Вызываемый платформой, чтобы заменить меню фреймового окна.|  
|[CFrameWndEx::OnSetPreviewMode](../Topic/CFrameWndEx::OnSetPreviewMode.md)|Вызываемый платформой, чтобы установить режим предварительного просмотра для кадра.|  
|[CFrameWndEx::OnSetText](../Topic/CFrameWndEx::OnSetText.md)|Вызываемый платформой для задания текста окна.|  
|[CFrameWndEx::OnShowCustomizePane](../Topic/CFrameWndEx::OnShowCustomizePane.md)|Вызываемый платформой, когда быстрая настраивает панель включена.|  
|[CFrameWndEx::OnShowPanes](../Topic/CFrameWndEx::OnShowPanes.md)|Вызываемый платформой, чтобы показать или скрыть панель.|  
|[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md)|Вызываемый платформой, когда контекстное меню меню будет включена.|  
|[CFrameWndEx::OnSize](../Topic/CFrameWndEx::OnSize.md)|Платформа вызывает этот метод после изменения размера кадра.|  
|[CFrameWndEx::OnSizing](../Topic/CFrameWndEx::OnSizing.md)|Платформа вызывает этот метод, когда пользователь изменяет размер кадр.|  
|[CFrameWndEx::OnSysColorChange](../Topic/CFrameWndEx::OnSysColorChange.md)|Вызывается инфраструктурой при изменении системных цветов.|  
|[CFrameWndEx::OnTearOffMenu](../Topic/CFrameWndEx::OnTearOffMenu.md)|Вызываемый платформой, когда меню, имеющее перемещаемую панель включено.|  
|[CFrameWndEx::OnToolbarContextMenu](../Topic/CFrameWndEx::OnToolbarContextMenu.md)|Вызываемый платформой для построения контекстное меню панели инструментов.|  
|[CFrameWndEx::OnToolbarCreateNew](../Topic/CFrameWndEx::OnToolbarCreateNew.md)|Границы вызывают этот метод для создания новой панели инструментов.|  
|[CFrameWndEx::OnToolbarDelete](../Topic/CFrameWndEx::OnToolbarDelete.md)|Если панель инструментов с платформой будет удаляется.|  
|[CFrameWndEx::OnUpdateFrameMenu](../Topic/CFrameWndEx::OnUpdateFrameMenu.md)|Вызываемый платформой для задания меню кадра.|  
|[CFrameWndEx::OnUpdateFrameTitle](../Topic/CFrameWndEx::OnUpdateFrameTitle.md)|Границы вызывают этот метод для обновления заголовок окна фреймового окна.|  
|[CFrameWndEx::OnUpdatePaneMenu](../Topic/CFrameWndEx::OnUpdatePaneMenu.md)|Вызываемый платформой для обновления панели меню.|  
|[CFrameWndEx::OnWindowPosChanged](../Topic/CFrameWndEx::OnWindowPosChanged.md)|Вызываемый платформой, когда размер кадра, позиция z\-порядка или изменяются в результате вызова метода управления для окна.|  
|[CFrameWndEx::PaneFromPoint](../Topic/CFrameWndEx::PaneFromPoint.md)|Возвращает панели закрепления, которая содержит указанную точку.|  
|[CFrameWndEx::PreTranslateMessage](../Topic/CFrameWndEx::PreTranslateMessage.md)|Обрабатывает сообщения окна конкретных, прежде чем они отправляются.|  
|[CFrameWndEx::RecalcLayout](../Topic/CFrameWndEx::RecalcLayout.md)|Обрабатывает структуру и его дочерних окон.|  
|[CFrameWndEx::RemovePaneFromDockManager](../Topic/CFrameWndEx::RemovePaneFromDockManager.md)|Отменяет регистрацию панель и удаляет его из внутреннего списка в диспетчере закрепления.|  
|[CFrameWndEx::SetDockState](../Topic/CFrameWndEx::SetDockState.md)|Извлекает структуру закрепления состояния закрепления, хранящихся в реестре.|  
|[CFrameWndEx::SetPrintPreviewFrame](../Topic/CFrameWndEx::SetPrintPreviewFrame.md)|Устанавливает фреймовое окно предварительного просмотра.|  
|[CFrameWndEx::SetupToolbarMenu](../Topic/CFrameWndEx::SetupToolbarMenu.md)|Вставляет определяемые пользователем команды в меню панели инструментов.|  
|[CFrameWndEx::ShowFullScreen](../Topic/CFrameWndEx::ShowFullScreen.md)|Переключение между экраном большую фрейма во весь и обычный режимами.|  
|[CFrameWndEx::ShowPane](../Topic/CFrameWndEx::ShowPane.md)|Показать или скрывает указанную область.|  
|[CFrameWndEx::UpdateCaption](../Topic/CFrameWndEx::UpdateCaption.md)|Вызываемый платформой для обновления заголовок границы окна.|  
|[CFrameWndEx::WinHelp](../Topic/CFrameWndEx::WinHelp.md)|Вызывает или приложение `WinHelp` или связанную контекстом справки.|  
  
## Пример  
 В следующем примере показано, как наследовать класс от класса `CFrameWndEx`.  Пример иллюстрирует сигнатуры метода в подклассе, и, как переопределить метод `OnShowPopupMenu`.  Этот фрагмент кода является частью [Пример запуска площадки слова](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/CPP/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/CPP/cframewndex-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## Требования  
 **заголовок:** afxframewndex.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)