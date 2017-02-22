---
title: "CMFCRibbonBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBar class"
ms.assetid: a65d06fa-1a28-4cc0-8971-bc9d7c9198fe
caps.latest.revision: 41
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 43
---
# CMFCRibbonBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonBar` реализует панель ленты. Аналогичная реализация использовалась в Office 2007.  
  
## Синтаксис  
  
```  
class CMFCRibbonBar : public CPane  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonBar::CMFCRibbonBar`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonBar::ActivateContextCategory](../Topic/CMFCRibbonBar::ActivateContextCategory.md)|Активирует уже видимую категорию контекста.|  
|[CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md)|Добавляет на ленту новую категорию.|  
|[CMFCRibbonBar::AddContextCategory](../Topic/CMFCRibbonBar::AddContextCategory.md)|Добавляет категорию контекста.|  
|[CMFCRibbonBar::AddMainCategory](../Topic/CMFCRibbonBar::AddMainCategory.md)|Добавляет новую основную категорию ленты.|  
|[CMFCRibbonBar::AddPrintPreviewCategory](../Topic/CMFCRibbonBar::AddPrintPreviewCategory.md)||  
|[CMFCRibbonBar::AddQATOnlyCategory](../Topic/CMFCRibbonBar::AddQATOnlyCategory.md)||  
|[CMFCRibbonBar::AddToTabs](../Topic/CMFCRibbonBar::AddToTabs.md)|Добавляет элемент ленты справа от панели ленты.|  
|[CMFCRibbonBar::CreateEx](../Topic/CMFCRibbonBar::CreateEx.md)|Создает панель элементов управления и прикрепляет ее к объекту [CPane](../../mfc/reference/cpane-class.md).  \(Переопределяет метод [CPane::CreateEx](../Topic/CPane::CreateEx.md).\)|  
|[CMFCRibbonBar::Create](../Topic/CMFCRibbonBar::Create.md)|Создает элемент управления панели ленты и прикрепляет его к панели ленты.|  
|[CMFCRibbonBar::DeactivateKeyboardFocus](../Topic/CMFCRibbonBar::DeactivateKeyboardFocus.md)||  
|[CMFCRibbonBar::DrawMenuImage](../Topic/CMFCRibbonBar::DrawMenuImage.md)||  
|[CMFCRibbonBar::DWMCompositionChanged](../Topic/CMFCRibbonBar::DWMCompositionChanged.md)||  
|[CMFCRibbonBar::EnableKeyTips](../Topic/CMFCRibbonBar::EnableKeyTips.md)|Включает или отключает всплывающие подсказки для элемента управления ленты.|  
|[CMFCRibbonBar::EnablePrintPreview](../Topic/CMFCRibbonBar::EnablePrintPreview.md)|Делает доступной вкладку **Предварительный просмотр**.|  
|[CMFCRibbonBar::EnableToolTips](../Topic/CMFCRibbonBar::EnableToolTips.md)|Включает или отключает всплывающие подсказки и описания на панели ленты.|  
|[CMFCRibbonBar::FindByData](../Topic/CMFCRibbonBar::FindByData.md)|Поиск элемента ленты по указанным пользователем данным.|  
|[CMFCRibbonBar::FindByID](../Topic/CMFCRibbonBar::FindByID.md)|Находит элемент ленты по указанному идентификатору команды.|  
|[CMFCRibbonBar::FindCategoryIndexByData](../Topic/CMFCRibbonBar::FindCategoryIndexByData.md)|Находит индекс категории ленты, содержащей определенные пользователем данные.|  
|[CMFCRibbonBar::ForceRecalcLayout](../Topic/CMFCRibbonBar::ForceRecalcLayout.md)||  
|[CMFCRibbonBar::GetActiveCategory](../Topic/CMFCRibbonBar::GetActiveCategory.md)|Возвращает указатель на активную категорию.|  
|[CMFCRibbonBar::GetCaptionHeight](../Topic/CMFCRibbonBar::GetCaptionHeight.md)|Возвращает высоту заголовка.  \(Переопределяет метод [CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md).\)|  
|[CMFCRibbonBar::GetCategory](../Topic/CMFCRibbonBar::GetCategory.md)|Возвращает указатель на категорию, расположенную по указанному индексу.|  
|[CMFCRibbonBar::GetCategoryCount](../Topic/CMFCRibbonBar::GetCategoryCount.md)|Возвращает число категорий ленты на панели ленты.|  
|[CMFCRibbonBar::GetCategoryHeight](../Topic/CMFCRibbonBar::GetCategoryHeight.md)||  
|[CMFCRibbonBar::GetCategoryIndex](../Topic/CMFCRibbonBar::GetCategoryIndex.md)|Возвращает индекс категории ленты.|  
|[CMFCRibbonBar::GetContextName](../Topic/CMFCRibbonBar::GetContextName.md)|Извлекает имя заголовка категории контекста, указанного с помощью идентификатора.|  
|[CMFCRibbonBar::GetDroppedDown](../Topic/CMFCRibbonBar::GetDroppedDown.md)||  
|[CMFCRibbonBar::GetElementsByID](../Topic/CMFCRibbonBar::GetElementsByID.md)|Возвращает массив, содержащий указатели на все элементы ленты с указанными идентификаторами.|  
|[CMFCRibbonBar::GetApplicationButton](../Topic/CMFCRibbonBar::GetApplicationButton.md)|Возвращает указатель на кнопку ленты.|  
|[CMFCRibbonBar::GetFocused](../Topic/CMFCRibbonBar::GetFocused.md)|Возвращает элемент, имеющий фокус ввода.|  
|[CMFCRibbonBar::GetHideFlags](../Topic/CMFCRibbonBar::GetHideFlags.md)||  
|[CMFCRibbonBar::GetItemIDsList](../Topic/CMFCRibbonBar::GetItemIDsList.md)||  
|[CMFCRibbonBar::GetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::GetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelCurrent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelCurrent.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelParent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelParent.md)||  
|[CMFCRibbonBar::GetMainCategory](../Topic/CMFCRibbonBar::GetMainCategory.md)|Возвращает указатель на выбранную категорию ленты.|  
|[CMFCRibbonBar::GetQATCommandsLocation](../Topic/CMFCRibbonBar::GetQATCommandsLocation.md)||  
|[CMFCRibbonBar::GetQATDroppedDown](../Topic/CMFCRibbonBar::GetQATDroppedDown.md)||  
|[CMFCRibbonBar::GetQuickAccessCommands](../Topic/CMFCRibbonBar::GetQuickAccessCommands.md)|Заполняет список идентификаторами команд всех элементов, отображающихся на панели быстрого доступа.|  
|[CMFCRibbonBar::GetQuickAccessToolbarLocation](../Topic/CMFCRibbonBar::GetQuickAccessToolbarLocation.md)||  
|[CMFCRibbonBar::GetTabTrancateRatio](../Topic/CMFCRibbonBar::GetTabTrancateRatio.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthLargeImage](../Topic/CMFCRibbonBar::GetTooltipFixedWidthLargeImage.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthRegular](../Topic/CMFCRibbonBar::GetTooltipFixedWidthRegular.md)||  
|[CMFCRibbonBar::GetVisibleCategoryCount](../Topic/CMFCRibbonBar::GetVisibleCategoryCount.md)||  
|[CMFCRibbonBar::HideAllContextCategories](../Topic/CMFCRibbonBar::HideAllContextCategories.md)|Скрывает все видимые и активные категории.|  
|[CMFCRibbonBar::HideKeyTips](../Topic/CMFCRibbonBar::HideKeyTips.md)||  
|[CMFCRibbonBar::HitTest](../Topic/CMFCRibbonBar::HitTest.md)|Находит указатель на элемент ленты, расположенный в указанной точке клиентских координат панели ленты.|  
|[CMFCRibbonBar::IsKeyTipEnabled](../Topic/CMFCRibbonBar::IsKeyTipEnabled.md)|Определяет, включены ли ключевые подсказки.|  
|[CMFCRibbonBar::IsMainRibbonBar](../Topic/CMFCRibbonBar::IsMainRibbonBar.md)||  
|[CMFCRibbonBar::IsPrintPreviewEnabled](../Topic/CMFCRibbonBar::IsPrintPreviewEnabled.md)|Определяет, активна ли вкладка **Предварительный просмотр**.|  
|[CMFCRibbonBar::IsQATEmpty](../Topic/CMFCRibbonBar::IsQATEmpty.md)||  
|[CMFCRibbonBar::IsQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::IsQuickAccessToolbarOnTop.md)|Определяет, находится ли панель быстрого доступа над панелью ленты.|  
|[CMFCRibbonBar::IsReplaceFrameCaption](../Topic/CMFCRibbonBar::IsReplaceFrameCaption.md)|Определяет, заменяет панель ленты заголовок главного фрейма или добавляется под ним.|  
|[CMFCRibbonBar::IsShowGroupBorder](../Topic/CMFCRibbonBar::IsShowGroupBorder.md)||  
|[CMFCRibbonBar::IsToolTipDescrEnabled](../Topic/CMFCRibbonBar::IsToolTipDescrEnabled.md)|Определяет, включены ли всплывающие описания.|  
|[CMFCRibbonBar::IsToolTipEnabled](../Topic/CMFCRibbonBar::IsToolTipEnabled.md)|Определяет, включены ли всплывающие подсказки для ленты.|  
|[CMFCRibbonBar::IsTransparentCaption](../Topic/CMFCRibbonBar::IsTransparentCaption.md)||  
|[CMFCRibbonBar::IsWindows7Look](../Topic/CMFCRibbonBar::IsWindows7Look.md)|Указывает, оформлена ли лента в стиле Windows 7 \(небольшая прямоугольная кнопка приложения\).|  
|[CMFCRibbonBar::LoadFromResource](../Topic/CMFCRibbonBar::LoadFromResource.md)|Перегружен.  Загружает панель ленты из ресурсов приложения.|  
|[CMFCRibbonBar::OnClickButton](../Topic/CMFCRibbonBar::OnClickButton.md)||  
|[CMFCRibbonBar::OnEditContextMenu](../Topic/CMFCRibbonBar::OnEditContextMenu.md)||  
|[CMFCRibbonBar::OnRTLChanged](../Topic/CMFCRibbonBar::OnRTLChanged.md)|\(Переопределяет метод `CPane::OnRTLChanged`.\)|  
|[CMFCRibbonBar::OnSetAccData](../Topic/CMFCRibbonBar::OnSetAccData.md)|\(Переопределяет метод [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCRibbonBar::OnShowRibbonContextMenu](../Topic/CMFCRibbonBar::OnShowRibbonContextMenu.md)||  
|[CMFCRibbonBar::OnShowRibbonQATMenu](../Topic/CMFCRibbonBar::OnShowRibbonQATMenu.md)||  
|[CMFCRibbonBar::OnSysKeyDown](../Topic/CMFCRibbonBar::OnSysKeyDown.md)||  
|[CMFCRibbonBar::OnSysKeyUp](../Topic/CMFCRibbonBar::OnSysKeyUp.md)||  
|[CMFCRibbonBar::PopTooltip](../Topic/CMFCRibbonBar::PopTooltip.md)||  
|[CMFCRibbonBar::PreTranslateMessage](../Topic/CMFCRibbonBar::PreTranslateMessage.md)|\(Переопределяет метод `CBasePane::PreTranslateMessage`.\)|  
|[CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md)|\(Переопределяет метод [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CMFCRibbonBar::RemoveAllCategories](../Topic/CMFCRibbonBar::RemoveAllCategories.md)|Удаляет все категории с панели ленты.|  
|[CMFCRibbonBar::RemoveAllFromTabs](../Topic/CMFCRibbonBar::RemoveAllFromTabs.md)|Удаляет все элементы ленты из области вкладки.|  
|[CMFCRibbonBar::RemoveCategory](../Topic/CMFCRibbonBar::RemoveCategory.md)|Удаляет категорию ленты, расположенную по указанному индексу.|  
|[CMFCRibbonBar::SaveToXMLBuffer](../Topic/CMFCRibbonBar::SaveToXMLBuffer.md)|Сохраняет панель ленты в буфер.|  
|[CMFCRibbonBar::SaveToXMLFile](../Topic/CMFCRibbonBar::SaveToXMLFile.md)|Сохраняет панель ленты в файл XML.|  
|[CMFCRibbonBar::SetActiveCategory](../Topic/CMFCRibbonBar::SetActiveCategory.md)|Назначает указанной категории ленты активное состояние.|  
|[CMFCRibbonBar::SetActiveMDIChild](../Topic/CMFCRibbonBar::SetActiveMDIChild.md)||  
|[CMFCRibbonBar::SetElementKeys](../Topic/CMFCRibbonBar::SetElementKeys.md)|Задает указанные ключевые подсказки для всех элементов ленты, которые имеют указанный идентификатор команды.|  
|[CMFCRibbonBar::SetApplicationButton](../Topic/CMFCRibbonBar::SetApplicationButton.md)|Помещает на панель ленты кнопку приложения.|  
|[CMFCRibbonBar::SetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::SetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::SetMaximizeMode](../Topic/CMFCRibbonBar::SetMaximizeMode.md)||  
|[CMFCRibbonBar::SetQuickAccessCommands](../Topic/CMFCRibbonBar::SetQuickAccessCommands.md)|Добавляет один или несколько элементов ленты на панель быстрого доступа.|  
|[CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)|Задает состояние панели быстрого доступа по умолчанию.|  
|[CMFCRibbonBar::SetQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::SetQuickAccessToolbarOnTop.md)|Помещает панель быстрого доступа над панелью ленты или под ней.|  
|[CMFCRibbonBar::SetTooltipFixedWidth](../Topic/CMFCRibbonBar::SetTooltipFixedWidth.md)||  
|[CMFCRibbonBar::SetWindows7Look](../Topic/CMFCRibbonBar::SetWindows7Look.md)|Включает или отключает оформление ленты в стиле Windows 7 \(небольшая прямоугольная кнопка приложения\).|  
|[CMFCRibbonBar::ShowCategory](../Topic/CMFCRibbonBar::ShowCategory.md)|Отображает или скрывает указанную категорию ленты.|  
|[CMFCRibbonBar::ShowContextCategories](../Topic/CMFCRibbonBar::ShowContextCategories.md)|Показывает или скрывает категории контекста с указанным идентификатором.|  
|[CMFCRibbonBar::ShowKeyTips](../Topic/CMFCRibbonBar::ShowKeyTips.md)||  
|[CMFCRibbonBar::ToggleMimimizeState](../Topic/CMFCRibbonBar::ToggleMimimizeState.md)|Переключает панель ленты между свернутым и развернутым состояниями.|  
|[CMFCRibbonBar::TranslateChar](../Topic/CMFCRibbonBar::TranslateChar.md)||  
  
## Заметки  
 Корпорация Майкрософт представила ленту \(Office Fluent Ribbon\) вместе с выпуском Microsoft Office 2007.  Панель ленты — это не просто новый элемент управления.  Она представляет собой новый подход к пользовательскому интерфейсу.  Лента — это панель с вкладками, которые называются категориями.  Каждая категория делится на группы, содержащие различные элементы управления и кнопки команд.  
  
 Элементы, отображающиеся на панели ленты, разворачиваются и сворачиваются, чтобы оптимально задействовать доступное пространство.  Например, если в группе ленты становится недостаточно места для отображения всех необходимых элементов, она превращается в кнопку, элементы которой показываются во всплывающем меню.  Лента ведет себя как статическая \(неперемещаемая\) панель элементов управления, которую можно закрепить в верхней части фрейма.  
  
 С помощью класса `CMFCRibbonStatusBar` вы можете реализовать строку состояния, аналогичную используемой в Office 2007.  В категории ленты содержится \(и отображается\) определенное число [групп ленты](../../mfc/reference/cmfcribbonpanel-class.md).  Каждая группа ленты содержит один или несколько элементов ленты, производных от [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md).  
  
 Дополнительные сведения о добавлении панели ленты в существующее приложение MFC см. в разделе [Пошаговое руководство. Обновление приложения MFC Scribble](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
## Требования  
 **Заголовок:** afxribbonbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Пошаговое руководство. Обновление приложения MFC Scribble](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)