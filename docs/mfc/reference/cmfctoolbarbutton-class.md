---
title: "CMFCToolBarButton Class | Microsoft Docs"
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
  - "CMFCToolBarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarButton class"
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности для кнопки панели инструментов.  
  
## Синтаксис  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarButton::CMFCToolBarButton](../Topic/CMFCToolBarButton::CMFCToolBarButton.md)|Создания и инициализации объект `CMFCToolBarButton`.|  
|`CMFCToolBarButton::~CMFCToolBarButton`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarButton::CanBeDropped](../Topic/CMFCToolBarButton::CanBeDropped.md)|Указывает, может ли пользователь изменить расположение кнопки на панели инструментов или меню во время настройки.|  
|[CMFCToolBarButton::CanBeStored](../Topic/CMFCToolBarButton::CanBeStored.md)|Определяет, является ли кнопка может быть сохранен.|  
|[CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md)|Указывает, может ли пользователь растянуть кнопка во время настройки.|  
|[CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)|Сравнивает данный экземпляр с предоставленным объектом `CMFCToolBarButton`.|  
|[CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)|Копирует свойства другой кнопки панели инструментов с текущим кнопке.|  
|[CMFCToolBarButton::CreateFromOleData](../Topic/CMFCToolBarButton::CreateFromOleData.md)|Создает объект `CMFCToolBarButton` из предоставленного объекта `COleDataObject`.|  
|`CMFCToolBarButton::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CMFCToolBarButton::EnableWindow](../Topic/CMFCToolBarButton::EnableWindow.md)|Включение или отключение ввода мыши и клавиатуры.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|Копии вставке СМС из кнопок панели инструментов в меню.|  
|[CMFCToolBarButton::GetClipboardFormat](../Topic/CMFCToolBarButton::GetClipboardFormat.md)|Получает глобальный формат буфера обмена для приложения.|  
|[CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md)|Получает дескриптор окна, который связан с кнопкой панели инструментов.|  
|[CMFCToolBarButton::GetImage](../Topic/CMFCToolBarButton::GetImage.md)|Извлекает индекс образа кнопки.|  
|[CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md)|Извлекает область клиентской области кнопки, в которой должен перерисовать.|  
|[CMFCToolBarButton::GetParentWnd](../Topic/CMFCToolBarButton::GetParentWnd.md)|Возвращает родительское окно кнопки.|  
|[CMFCToolBarButton::GetProtectedCommands](../Topic/CMFCToolBarButton::GetProtectedCommands.md)|Извлекает список команд, которые пользователь не может настраивать.|  
|[CMFCToolBarButton::GetTextSize](../Topic/CMFCToolBarButton::GetTextSize.md)|Получает размер текста кнопки.|  
|[CMFCToolBarButton::HasFocus](../Topic/CMFCToolBarButton::HasFocus.md)|Указывает, имеет ли кнопка текущий фокус ввода.|  
|[CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)|Указывает, отображается ли граница кнопки, когда пользователь выбирает кнопку.|  
|[CMFCToolBarButton::IsDrawImage](../Topic/CMFCToolBarButton::IsDrawImage.md)|Указывает, отображается ли образ на кнопке.|  
|[CMFCToolBarButton::IsDrawText](../Topic/CMFCToolBarButton::IsDrawText.md)|Указывает, отображается ли метка текстовой подписи на кнопке.|  
|[CMFCToolBarButton::IsDroppedDown](../Topic/CMFCToolBarButton::IsDroppedDown.md)|Определяет, указывает ли кнопка подменю.|  
|[CMFCToolBarButton::IsEditable](../Topic/CMFCToolBarButton::IsEditable.md)|Определяет, является ли кнопка можно настраивать.|  
|[CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)|Определяет, является ли кнопка может отображаться с расширенной границей.|  
|[CMFCToolBarButton::IsFirstInGroup](../Topic/CMFCToolBarButton::IsFirstInGroup.md)|Определяет, является ли кнопка в первую позицию в этой группе кнопки.|  
|[CMFCToolBarButton::IsHidden](../Topic/CMFCToolBarButton::IsHidden.md)|Определяет скрыта ли кнопка.|  
|[CMFCToolBarButton::IsHorizontal](../Topic/CMFCToolBarButton::IsHorizontal.md)|Определяет, является ли найдено кнопки на горизонтальной панели инструментов.|  
|[CMFCToolBarButton::IsLastInGroup](../Topic/CMFCToolBarButton::IsLastInGroup.md)|Определяет, является ли кнопка в последней позиции в этой группе кнопки.|  
|[CMFCToolBarButton::IsLocked](../Topic/CMFCToolBarButton::IsLocked.md)|Определяет, является ли кнопка панели инструментов, блокированных \(настраиваемой\).|  
|[CMFCToolBarButton::IsOwnerOf](../Topic/CMFCToolBarButton::IsOwnerOf.md)|Определяет, является ли кнопка владелец предоставленного дескриптора окна.|  
|[CMFCToolBarButton::IsVisible](../Topic/CMFCToolBarButton::IsVisible.md)|Указывает, видима ли кнопка панели инструментов.|  
|[CMFCToolBarButton::IsWindowVisible](../Topic/CMFCToolBarButton::IsWindowVisible.md)|Определяет, является ли базовый дескриптор окна кнопки становится видимым.|  
|[CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)|Определяет, выполняет ли кнопка сообщение [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591).|  
|[CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md)|Вызываемый платформой, когда кнопка будет добавлена к компоненту **Настроить**.|  
|[CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)|Определяет, является ли кнопка можно перетаскивать.|  
|[CMFCToolBarButton::OnBeforeDrop](../Topic/CMFCToolBarButton::OnBeforeDrop.md)|Указывает, может ли пользователь кнопку удалить на панели инструментов целевого объекта.|  
|[CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)|Вызываемый платформой, чтобы вычислить размер кнопки для указанного контекста устройства и состояния закрепления.|  
|[CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)|Вызываемый платформой для обработки сообщения [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615).|  
|[CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)|Вызываемый платформой, если кнопка будет вставлена в новую панель инструментов.|  
|[CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)|Вызываемый платформой, когда пользователь нажимает кнопку мыши.|  
|[CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)|Вызываемый платформой, когда пользователь освобождает кнопки мыши.|  
|[CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)|Вызываемый платформой если панель инструментов `WM_HELPHITTEST` родителя обрабатывающий сообщение.|  
|[CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md)|Вызываемый платформой если панель инструментов `WM_CTLCOLOR` родителя обрабатывающий сообщение.|  
|[CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)|Разрешает кнопку, чтобы изменить предоставленный меню, когда приложение отображает контекстное меню в родительской панели инструментов.|  
|[CMFCToolBarButton::OnDblClk](../Topic/CMFCToolBarButton::OnDblClk.md)|Вызываемый платформой если панель инструментов [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) родителя обрабатывающий сообщение.|  
|[CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)|Вызываемый платформой для рисования кнопки с помощью указанных стилей и параметров.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)|Вызываемый платформой для рисования кнопки на панели **Команды** диалогового окна **Настроить**.|  
|[CMFCToolBarButton::OnGetCustomToolTipText](../Topic/CMFCToolBarButton::OnGetCustomToolTipText.md)|Вызываемый платформой для получения пользовательский текст всплывающей подсказки для кнопки.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md)|Вызываемый платформой, если глобальный шрифт изменяется.|  
|[CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md)|Вызываемый платформой, если родительская панель инструментов.|  
|[CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md)|Когда кнопка становится видимой называется структурой или невидимой.|  
|[CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md)|Вызываемый платформой, если родительская панели инструментов меняет его размер или положение и это изменение требуют кнопку изменяет размер.|  
|[CMFCToolBarButton::OnToolHitTest](../Topic/CMFCToolBarButton::OnToolHitTest.md)|Вызываемый платформой, если родительская панель инструментов должна определить, находится ли точка в ограничивающем прямоугольнике кнопки.|  
|[CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md)|Вызываемый платформой, если родительская панель инструментов обновляет его текст подсказки.|  
|[CMFCToolBarButton::PrepareDrag](../Topic/CMFCToolBarButton::PrepareDrag.md)|Вызывается инфраструктурой при нажатии кнопки " собирается выполнять операции перетаскивания.|  
|[CMFCToolBarButton::Rect](../Topic/CMFCToolBarButton::Rect.md)|Получает ограничивающий прямоугольник кнопки.|  
|[CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)|Наборы по умолчанию образ, который связан с кнопкой.|  
|[CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)|Сохраняет состояние кнопки панели инструментов.|  
|[CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)|Считывает этот объект из архива или записывает его в архив.  \(Переопределяет [CObject::Serialize](../Topic/CObject::Serialize.md)\).|  
|[CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)|Заполняет предоставленный объект `CAccessibilityData` со сведениями о специальных возможностей от кнопки панели инструментов.|  
|[CMFCToolBarButton::SetClipboardFormatName](../Topic/CMFCToolBarButton::SetClipboardFormatName.md)|Переименовывает глобальный формат буфера обмена.|  
|[CMFCToolBarButton::SetImage](../Topic/CMFCToolBarButton::SetImage.md)|Устанавливает индекс образа кнопки.|  
|[CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)|Задает список команд, которые пользователь не может настраивать.|  
|[CMFCToolBarButton::SetRadio](../Topic/CMFCToolBarButton::SetRadio.md)|Вызываемый платформой, если кнопка изменяет ее состояние флажка.|  
|[CMFCToolBarButton::SetRect](../Topic/CMFCToolBarButton::SetRect.md)|Задает прямоугольник кнопки.|  
|[CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)|Задает стиль кнопки.|  
|[CMFCToolBarButton::SetVisible](../Topic/CMFCToolBarButton::SetVisible.md)|Определяет, является ли кнопка видима.|  
|[CMFCToolBarButton::Show](../Topic/CMFCToolBarButton::Show.md)|Показать или скрывает кнопки.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarButton::m\_bImage](../Topic/CMFCToolBarButton::m_bImage.md)|Указывает, отображается ли образ на кнопке.|  
|[CMFCToolBarButton::m\_bText](../Topic/CMFCToolBarButton::m_bText.md)|Указывает, отображается ли метка текстовой подписи на кнопке.|  
|[CMFCToolBarButton::m\_bTextBelow](../Topic/CMFCToolBarButton::m_bTextBelow.md)|Указывает, отображается ли метка текстовой подписи под образом на кнопке.|  
|[CMFCToolBarButton::m\_bUserButton](../Topic/CMFCToolBarButton::m_bUserButton.md)|Указывает, имеет ли определяемый пользователем кнопки образ.|  
|[CMFCToolBarButton::m\_bWholeText](../Topic/CMFCToolBarButton::m_bWholeText.md)|Определяет, указывает ли кнопка свою полнотекстовую метку, даже если она не адаптирует в ограничивающем прямоугольнике.|  
|[CMFCToolBarButton::m\_bWrap](../Topic/CMFCToolBarButton::m_bWrap.md)|Указывает, будет ли кнопка рядом с разделителем переходит на следующую строку.|  
|[CMFCToolBarButton::m\_bWrapText](../Topic/CMFCToolBarButton::m_bWrapText.md)|Определяет, включаются ли многополосные текстовые подписи.|  
|[CMFCToolBarButton::m\_nID](../Topic/CMFCToolBarButton::m_nID.md)|Идентификатор команды кнопки.|  
|[CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)|Стиль кнопки.|  
|[CMFCToolBarButton::m\_strText](../Topic/CMFCToolBarButton::m_strText.md)|Текстовая подпись кнопки.|  
  
## Заметки  
 Объект `CMFCToolbarButton` элемент управления, который находится на панели инструментов.  Его функциональности напоминает любая из обычной кнопки.  Можно присвоить образ и текстовая подпись к данному объекту.  Кнопка панели инструментов может также иметь идентификатор команды.  При нажатии пользователем кнопки панели инструментов границы выполнить команду, которую этот идентификатор указывается.  
  
 Обычно кнопки панели инструментов можно настраивать. пользователь может перетащить кнопки из одной панели инструментов в другую и копировать, вставлять, удалять и изменять текстовые подписи и изображений.  Для предотвращения пользователя от настройки панели инструментов можно блокировать панели инструментов в одном из 2 способов.  Любой набор пометить `bLocked` к `TRUE` при вызове [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md) или добавляет идентификатор команды отдельной кнопки глобальный список защищенных команд с помощью метода [CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md).  
  
 `CMFCToolBarButton` возражает образы отображения из глобальных коллекций образов панели инструментов в приложении.  Эти коллекции поддерживаются родительский элемент панели инструментов, [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).  Дополнительные сведения см. в разделе [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md).  
  
 При нажатии пользователем кнопки панели инструментов, его родителя обрабатывающей сообщение мыши панель инструментов и передает необходимые действия на кнопке.  Если кнопка имеет допустимый идентификатор команды, то родительской панели инструментов отправляет сообщение `WM_COMMAND` к родительским кадром.  
  
 Класс `CMFCToolBarButton` базового класса для других классов кнопки панели инструментов, как [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton Class](../Topic/CMFCToolBarEditBoxButton%20Class.md) и [CMFCToolBarComboBoxButton Class](../Topic/CMFCToolBarComboBoxButton%20Class.md).  
  
## Пример  
 В следующем примере показано, как настроить объект `CMFCToolBarButton` с помощью различных методов в классе `CMFCToolBarButton`.  Примере показано, как включить ввода мыши и клавиатуры, задать индекс образа кнопки установить ограничивающий прямоугольник кнопки и сделать кнопку видимым.  Этот фрагмент кода является частью [Образец набора вкладок](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TabControl#1](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl#2](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Требования  
 **заголовок:** afxtoolbarbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages Class](../../mfc/reference/cmfctoolbarimages-class.md)   
 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)   
 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)