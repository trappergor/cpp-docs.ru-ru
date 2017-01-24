---
title: "CMFCToolBarMenuButton Class | Microsoft Docs"
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
  - "CMFCToolBarMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarMenuButton class"
ms.assetid: cfa50176-7e4b-4527-9904-86a1b48fc1bc
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Кнопка панели инструментов, содержащая всплывающее меню.  
  
## Синтаксис  
  
```  
class CMFCToolBarMenuButton : public CMFCToolBarButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarMenuButton::CMFCToolBarMenuButton](../Topic/CMFCToolBarMenuButton::CMFCToolBarMenuButton.md)|Создает объект `CMFCToolBarMenuButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarMenuButton::CompareWith](../Topic/CMFCToolBarMenuButton::CompareWith.md)|Сравнивает данный экземпляр с предоставленным объектом `CMFCToolBarButton`.  \(Переопределяет [CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)\).|  
|[CMFCToolBarMenuButton::CopyFrom](../Topic/CMFCToolBarMenuButton::CopyFrom.md)|Копирует свойства другой кнопки панели инструментов с текущим кнопке.  \(Переопределяет [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)\).|  
|[CMFCToolBarMenuButton::CreateFromMenu](../Topic/CMFCToolBarMenuButton::CreateFromMenu.md)|Инициализирует меню панели инструментов из дескриптора меню Windows.|  
|[CMFCToolBarMenuButton::CreateMenu](../Topic/CMFCToolBarMenuButton::CreateMenu.md)|Создает меню Windows, состоящее из команд в меню панели инструментов.  Возвращает дескриптор меню Windows.|  
|[CMFCToolBarMenuButton::CreatePopupMenu](../Topic/CMFCToolBarMenuButton::CreatePopupMenu.md)|Создает объект раскрывающегося меню \([CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md)\) для отображения меню панели инструментов.|  
|[CMFCToolBarMenuButton::EnableQuickCustomize](../Topic/CMFCToolBarMenuButton::EnableQuickCustomize.md)||  
|[CMFCToolBarMenuButton::GetCommands](../Topic/CMFCToolBarMenuButton::GetCommands.md)|Предоставляет доступ только для чтения список команд в меню панели инструментов.|  
|[CMFCToolBarMenuButton::GetImageRect](../Topic/CMFCToolBarMenuButton::GetImageRect.md)|Возвращает ограничивающий прямоугольник для образа кнопки.|  
|[CMFCToolBarMenuButton::GetPaletteRows](../Topic/CMFCToolBarMenuButton::GetPaletteRows.md)|Возвращает число строк во всплывающем меню, когда меню в режиме палитры.|  
|[CMFCToolBarMenuButton::GetPopupMenu](../Topic/CMFCToolBarMenuButton::GetPopupMenu.md)|Возвращает указатель на объект раскрывающегося меню, который связан с кнопкой.|  
|[CMFCToolBarMenuButton::HasButton](../Topic/CMFCToolBarMenuButton::HasButton.md)||  
|[CMFCToolBarMenuButton::HaveHotBorder](../Topic/CMFCToolBarMenuButton::HaveHotBorder.md)|Указывает, отображается ли граница кнопки, когда пользователь выбирает кнопку.  \(Переопределяет [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)\).|  
|[CMFCToolBarMenuButton::IsBorder](../Topic/CMFCToolBarMenuButton::IsBorder.md)||  
|[CMFCToolBarMenuButton::IsClickedOnMenu](../Topic/CMFCToolBarMenuButton::IsClickedOnMenu.md)||  
|[CMFCToolBarMenuButton::IsDroppedDown](../Topic/CMFCToolBarMenuButton::IsDroppedDown.md)|Указывает, отображается ли контекстное меню меню.|  
|[CMFCToolBarMenuButton::IsEmptyMenuAllowed](../Topic/CMFCToolBarMenuButton::IsEmptyMenuAllowed.md)|Вызываемый средой, чтобы определить, может ли пользователь открыть вложенное меню от выбранного пункта меню.|  
|[CMFCToolBarMenuButton::IsExclusive](../Topic/CMFCToolBarMenuButton::IsExclusive.md)|Определяет, является ли кнопка в монопольном режиме, то есть ли открытые остатки раскрывающегося меню, даже когда пользователь перемещает указатель над другими панелью инструментов и кнопкой.|  
|[CMFCToolBarMenuButton::IsMenuPaletteMode](../Topic/CMFCToolBarMenuButton::IsMenuPaletteMode.md)|Определяет, является ли контекстное меню меню в режиме палитры.|  
|[CMFCToolBarMenuButton::IsQuickMode](../Topic/CMFCToolBarMenuButton::IsQuickMode.md)||  
|[CMFCToolBarMenuButton::IsTearOffMenu](../Topic/CMFCToolBarMenuButton::IsTearOffMenu.md)|Указывает, имеет ли контекстное меню меню перемещаемую панель.|  
|[CMFCToolBarMenuButton::OnAfterCreatePopupMenu](../Topic/CMFCToolBarMenuButton::OnAfterCreatePopupMenu.md)||  
|[CMFCToolBarMenuButton::OnBeforeDrag](../Topic/CMFCToolBarMenuButton::OnBeforeDrag.md)|Определяет, является ли кнопка можно перетаскивать.  \(Переопределяет [CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)\).|  
|[CMFCToolBarMenuButton::OnCalculateSize](../Topic/CMFCToolBarMenuButton::OnCalculateSize.md)|Вызываемый платформой, чтобы вычислить размер кнопки для указанного контекста устройства и состояния закрепления.  \(Переопределяет [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)\).|  
|[CMFCToolBarMenuButton::OnCancelMode](../Topic/CMFCToolBarMenuButton::OnCancelMode.md)|Вызываемый платформой для обработки сообщения [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615).  \(Переопределяет [CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)\).|  
|[CMFCToolBarMenuButton::OnChangeParentWnd](../Topic/CMFCToolBarMenuButton::OnChangeParentWnd.md)|Вызываемый платформой, если кнопка будет вставлена в новую панель инструментов.  \(Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)\).|  
|[CMFCToolBarMenuButton::OnClick](../Topic/CMFCToolBarMenuButton::OnClick.md)|Вызываемый платформой, когда пользователь нажимает кнопку мыши.  \(Переопределяет [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)\).|  
|[CMFCToolBarMenuButton::OnClickMenuItem](../Topic/CMFCToolBarMenuButton::OnClickMenuItem.md)|Вызываемый платформой, когда пользователь выбирает элемент в всплывающем меню.|  
|[CMFCToolBarMenuButton::OnContextHelp](../Topic/CMFCToolBarMenuButton::OnContextHelp.md)|Вызываемый платформой если панель инструментов `WM_HELPHITTEST` родителя обрабатывающий сообщение.  \(Переопределяет [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)\).|  
|[CMFCToolBarMenuButton::OnDraw](../Topic/CMFCToolBarMenuButton::OnDraw.md)|Вызываемый платформой для рисования кнопки с помощью указанных стилей и параметров.  \(Переопределяет [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)\).|  
|[CMFCToolBarMenuButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarMenuButton::OnDrawOnCustomizeList.md)|Вызываемый платформой для рисования кнопки на панели **Команды** диалогового окна **Настроить**.  \(Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)\).|  
|[CMFCToolBarMenuButton::OpenPopupMenu](../Topic/CMFCToolBarMenuButton::OpenPopupMenu.md)|Вызываемый платформой, когда пользователь будет открыто всплывающее меню.|  
|[CMFCToolBarMenuButton::ResetImageToDefault](../Topic/CMFCToolBarMenuButton::ResetImageToDefault.md)|Наборы по умолчанию образ, который связан с кнопкой.  \(Переопределяет [CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)\).|  
|[CMFCToolBarMenuButton::SaveBarState](../Topic/CMFCToolBarMenuButton::SaveBarState.md)|Сохраняет состояние кнопки панели инструментов.  \(Переопределяет [CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)\).|  
|[CMFCToolBarMenuButton::Serialize](../Topic/CMFCToolBarMenuButton::Serialize.md)|Считывает этот объект из архива или записывает его в архив.  \(Переопределяет [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)\).|  
|[CMFCToolBarMenuButton::SetACCData](../Topic/CMFCToolBarMenuButton::SetACCData.md)|Заполняет предоставленный объект `CAccessibilityData` со сведениями о специальных возможностей от кнопки панели инструментов.  \(Переопределяет [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)\).|  
|[CMFCToolBarMenuButton::SetMenuOnly](../Topic/CMFCToolBarMenuButton::SetMenuOnly.md)|Определяет, является ли кнопка может быть добавлен на панели инструментов.|  
|[CMFCToolBarMenuButton::SetMenuPaletteMode](../Topic/CMFCToolBarMenuButton::SetMenuPaletteMode.md)|Определяет, является ли контекстное меню меню в режиме палитры.|  
|[CMFCToolBarMenuButton::SetMessageWnd](../Topic/CMFCToolBarMenuButton::SetMessageWnd.md)||  
|[CMFCToolBarMenuButton::SetRadio](../Topic/CMFCToolBarMenuButton::SetRadio.md)|Принудительно кнопку меню панели инструментов для отображения значка, указывающий, что элемент выбран.|  
|[CMFCToolBarMenuButton::SetTearOff](../Topic/CMFCToolBarMenuButton::SetTearOff.md)|Определяет перемещаемое идентификатор области для раскрывающегося меню.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarMenuButton::DrawDocumentIcon](../Topic/CMFCToolBarMenuButton::DrawDocumentIcon.md)|Рисует значка на кнопке меню.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarMenuButton::m\_bAlwaysCallOwnerDraw](../Topic/CMFCToolBarMenuButton::m_bAlwaysCallOwnerDraw.md)|Если `TRUE` платформа всегда вызывает метод [CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md), когда кнопка нарисована.|  
  
## Заметки  
 `CMFCToolBarMenuButton` может отображаться как меню выберите пункт меню, имеющий подменю или кнопку которой выполняется команда или отображает меню или кнопка, которая показывает только меню.  Указать расширение функциональности и внешний вид кнопки меню, указав такие параметры, как изображение, текст дескриптор меню и идентификатор команды, сопоставлено с кнопкой в конструкторе `CMFCToolbarMenuButton::CMFCToolbarMenuButton`.  
  
 Пользовательский класс, унаследованный от класса `CMFCToolbarMenuButton` должен использовать макрос [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md).  Макрос [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) формирует ошибку, когда приложение закрывает.  
  
## Пример  
 В следующем примере показано, как настроить объект `CMFCToolBarMenuButton`.  Код иллюстрирует, как указать, что раскрывающееся меню в режиме палитры и указать идентификатор для перемещаемой панели, создана, когда пользователь перетаскивает меню кнопки строки меню.  Этот фрагмент кода является частью [Пример запуска площадки слова](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#10](../../mfc/reference/codesnippet/CPP/cmfctoolbarmenubutton-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
## Требования  
 **заголовок:** afxtoolbarmenubutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md)