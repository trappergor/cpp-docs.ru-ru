---
title: "CMFCToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBar class"
ms.assetid: e7679c01-fb94-44c0-98c6-3af955292fb5
caps.latest.revision: 48
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 50
---
# CMFCToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCToolBar` напоминает [CToolBar Class](../../mfc/reference/ctoolbar-class.md), но обеспечивает дополнительную поддержку функций пользовательского интерфейса.  Они включают плоские панели инструментов панели инструментов с образами горячими большие значки панели инструментов кнопки страничного навигатора, блокированных элементы управления " Главная панель текста под образов, фоновые изображения и со вкладками панели инструментов.  Класс `CMFCToolBar` также содержит встроенную поддержку для настройки пользователя панелей инструментов и меню, между панелями инструментов и меню перетаскивания, кнопок полей со списком, кнопок полей ввода, цветов и кнопки сведения.  
  
## Синтаксис  
  
```  
class CMFCToolBar : public CMFCBaseToolBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCToolBar::CMFCToolBar`|Конструктор по умолчанию.|  
|`CMFCToolBar::~CMFCToolBar`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBar::AddBasicCommand](../Topic/CMFCToolBar::AddBasicCommand.md)|Добавление команды меню в список команд, которые отображаются всегда, когда пользователь открывает меню.|  
|[CMFCToolBar::AddCommandUsage](../Topic/CMFCToolBar::AddCommandUsage.md)|Увеличивает на единицу счетчик, который связан с данной командой.|  
|[CMFCToolBar::AddToolBarForImageCollection](../Topic/CMFCToolBar::AddToolBarForImageCollection.md)|Добавляет образы из ресурсов пользовательского интерфейса в коллекции изображений в приложении.|  
|[CMFCToolBar::AdjustLayout](../Topic/CMFCToolBar::AdjustLayout.md)|Повторно вычисляет размер и положение панели инструментов.  \(Переопределяет метод [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md).\)|  
|[CMFCToolBar::AdjustSize](../Topic/CMFCToolBar::AdjustSize.md)|Повторно вычисляет размер панели инструментов.|  
|[CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)|Указывает, будут ли текстовые подписи можно отобразить с образами в кнопках панели инструментов.|  
|[CMFCToolBar::AreTextLabels](../Topic/CMFCToolBar::AreTextLabels.md)|Указывает, отображаются ли текстовые подписи с образами в настоящее время на кнопках панели инструментов.|  
|[CMFCToolBar::AutoGrayInactiveImages](../Topic/CMFCToolBar::AutoGrayInactiveImages.md)|Включить или отключить автоматическое формирование неактивных изображений кнопок.|  
|[CMFCToolBar::ButtonToIndex](../Topic/CMFCToolBar::ButtonToIndex.md)|Возвращает индекс указанного объекта [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) в данной панели инструментов.|  
|[CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)|Вычисляет горизонтальный размер панели инструментов.  \(Переопределяет [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)\).|  
|[CMFCToolBar::CalcSize](../Topic/CMFCToolBar::CalcSize.md)|Вызываемый платформой как часть процесса вычисления макета.  \(Переопределяет [CPane::CalcSize](../Topic/CPane::CalcSize.md)\).|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Определяет, находятся ли панель инструментов и его элемент того же уровня на одну и ту же область.|  
|[CMFCToolBar::CleanUpImages](../Topic/CMFCToolBar::CleanUpImages.md)|Освобождает ресурсы системы, выбранные для образов панели инструментов.|  
|[CMFCToolBar::CleanUpLockedImages](../Topic/CMFCToolBar::CleanUpLockedImages.md)|Освобождает ресурсы системы, выбранные для образов блокированных панели инструментов.|  
|[CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)|Указывает, может ли пользователь закрыть панель инструментов.  \(Переопределяет [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\).|  
|[CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)|Определяет, может ли система получить панели инструментов в исходное состояние после настройки.|  
|[CMFCToolBar::CanFocus](../Topic/CMFCToolBar::CanFocus.md)|Определяет, является ли панель может получать фокус.  \(Переопределяет [CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)\).|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Определяет, находятся ли панель инструментов и его элемент того же уровня на одну и ту же область.|  
|[CMFCToolBar::CommandToIndex](../Topic/CMFCToolBar::CommandToIndex.md)|Возвращает индекс кнопок на панели инструментов с указанным идентификатором команды|  
|[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)|Создает объект `CMFCToolBar`.|  
|[CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md)|Создает объект `CMFCToolBar`, использующий дополнительные параметры стиля, в виде крупных значков.|  
|[CMFCToolBar::Deactivate](../Topic/CMFCToolBar::Deactivate.md)|Деактивирует панель инструментов.|  
|[CMFCToolBar::EnableCustomizeButton](../Topic/CMFCToolBar::EnableCustomizeButton.md)|Позволяет включить или отключить кнопку **Добавить или удалить кнопки** , которая отображается на окончании панели инструментов.|  
|[CMFCToolBar::EnableDocking](../Topic/CMFCToolBar::EnableDocking.md)|Включает закрепления панелей в главного фрейма.  \(Переопределяет [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)\).|  
|[CMFCToolBar::EnableLargeIcons](../Topic/CMFCToolBar::EnableLargeIcons.md)|Включение или отключение крупных значков на кнопках панели инструментов.|  
|[CMFCToolBar::EnableQuickCustomization](../Topic/CMFCToolBar::EnableQuickCustomization.md)|Позволяет включить или отключить быструю настройку панелей инструментов, чтобы пользователь мог нажать кнопку ключ **Alt** и перетащите в новое расположение.|  
|[CMFCToolBar::EnableReflections](../Topic/CMFCToolBar::EnableReflections.md)|Включение или отключение отражение команды.|  
|[CMFCToolBar::EnableTextLabels](../Topic/CMFCToolBar::EnableTextLabels.md)|Включение или отключение текстовые подписи с образами кнопки панели инструментов.|  
|[CMFCToolBar::FromHandlePermanent](../Topic/CMFCToolBar::FromHandlePermanent.md)|Извлекает указатель на объект `CMFCToolBar`, содержащий заданный дескриптор окна.|  
|[CMFCToolBar::GetAllButtons](../Topic/CMFCToolBar::GetAllButtons.md)|Возвращает только для чтения список кнопок на панели инструментов.|  
|[CMFCToolBar::GetAllToolbars](../Topic/CMFCToolBar::GetAllToolbars.md)|Возвращает только для чтения список всех панелей инструментов в приложении.|  
|[CMFCToolBar::GetBasicCommands](../Topic/CMFCToolBar::GetBasicCommands.md)|Возвращает только для чтения список основных команд, определенных в приложении.|  
|[CMFCToolBar::GetButton](../Topic/CMFCToolBar::GetButton.md)|Возвращает указатель на объект `CMFCToolBarButton`, имеющий указанный индекс кнопки панели инструментов.|  
|[CMFCToolBar::GetButtonInfo](../Topic/CMFCToolBar::GetButtonInfo.md)|Возвращает идентификатор команды, стиль и индекс изображения кнопок по указанному индексу.|  
|[CMFCToolBar::GetButtonSize](../Topic/CMFCToolBar::GetButtonSize.md)|Возвращает измерения каждой кнопки на панели инструментов.|  
|[CMFCToolBar::GetButtonStyle](../Topic/CMFCToolBar::GetButtonStyle.md)|Возвращает текущий стиль кнопки панели инструментов, найдено по указанному индексу.|  
|[CMFCToolBar::GetButtonText](../Topic/CMFCToolBar::GetButtonText.md)|Возвращает текстовую подпись кнопки, имеющий указанный индекс.|  
|[CMFCToolBar::GetColdImages](../Topic/CMFCToolBar::GetColdImages.md)|Возвращает указатель на коллекцию холодных изображений кнопок панели инструментов в приложении.|  
|[CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)|Возвращает ширину кнопки панели инструментов.|  
|[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)|Возвращает список кнопок с указанным идентификатором команды из всех панелей инструментов в приложении.|  
|[CMFCToolBar::GetCount](../Topic/CMFCToolBar::GetCount.md)|Получает число кнопок и разделителей на панели инструментов.|  
|[CMFCToolBar::GetCustomizeButton](../Topic/CMFCToolBar::GetCustomizeButton.md)|Извлекает указатель на объект `CMFCCustomizeButton`, который связан с панелью инструментов.|  
|[CMFCToolBar::GetDefaultImage](../Topic/CMFCToolBar::GetDefaultImage.md)|Возвращает индекс по умолчанию образа для кнопок панели инструментов с указанным идентификатором команды|  
|[CMFCToolBar::GetDisabledImages](../Topic/CMFCToolBar::GetDisabledImages.md)|Возвращает указатель на коллекции изображений, используемых при отключенных кнопок панели инструментов в приложении.|  
|[CMFCToolBar::GetDisabledMenuImages](../Topic/CMFCToolBar::GetDisabledMenuImages.md)|Возвращает указатель на коллекции изображений, используемых при отключенных кнопок меню в приложении.|  
|[CMFCToolBar::GetDroppedDownMenu](../Topic/CMFCToolBar::GetDroppedDownMenu.md)|Извлекает указатель на объект button меню, который в данный момент указывает его подменю.|  
|[CMFCToolBar::GetGrayDisabledButtons](../Topic/CMFCToolBar::GetGrayDisabledButtons.md)|Определяет, является ли образы отключенных кнопок уменьшен яркостьые версии обычных изображений кнопок или принятый из коллекции отключенных изображений кнопок.|  
|[CMFCToolBar::GetHighlightedButton](../Topic/CMFCToolBar::GetHighlightedButton.md)|Возвращает указатель на кнопке панели инструментов, которая в настоящий момент выделена.|  
|[CMFCToolBar::GetHotBorder](../Topic/CMFCToolBar::GetHotBorder.md)|Определяет, является ли высокий\- отслеживаются кнопки панели инструментов.|  
|[CMFCToolBar::GetHotTextColor](../Topic/CMFCToolBar::GetHotTextColor.md)|Возвращает цвет текста выбранных кнопок панели инструментов.|  
|[CMFCToolBar::GetHwndLastFocus](../Topic/CMFCToolBar::GetHwndLastFocus.md)|Возвращает дескриптор окна, которое имело фокус ввода непосредственно перед панель инструментов сделала.|  
|[CMFCToolBar::GetIgnoreSetText](../Topic/CMFCToolBar::GetIgnoreSetText.md)|Определяет, является ли игнорируются вызовы задать метки кнопки.|  
|[CMFCToolBar::GetImageSize](../Topic/CMFCToolBar::GetImageSize.md)|Возвращает текущий размер изображений кнопок панели инструментов.|  
|[CMFCToolBar::GetImages](../Topic/CMFCToolBar::GetImages.md)|Возвращает указатель на коллекции образов кнопку по умолчанию в приложении.|  
|[CMFCToolBar::GetImagesOffset](../Topic/CMFCToolBar::GetImagesOffset.md)|Возвращает смещение индекса, который используется для получения изображений кнопок панели инструментов для данной панели инструментов в глобальном списке изображений кнопок панели инструментов.|  
|[CMFCToolBar::GetInvalidateItemRect](../Topic/CMFCToolBar::GetInvalidateItemRect.md)|Извлекает область клиентской области, должен перерисовать для кнопки по заданному индексу.|  
|[CMFCToolBar::GetItemID](../Topic/CMFCToolBar::GetItemID.md)|Возвращает идентификатор команды кнопки панели инструментов по указанному индексу.|  
|[CMFCToolBar::GetItemRect](../Topic/CMFCToolBar::GetItemRect.md)|Возвращает ограничивающий прямоугольник для кнопки по указанному индексу.|  
|[CMFCToolBar::GetLargeColdImages](../Topic/CMFCToolBar::GetLargeColdImages.md)|Возвращает указатель на коллекции больших холодных изображений кнопок панели инструментов в приложении.|  
|[CMFCToolBar::GetLargeDisabledImages](../Topic/CMFCToolBar::GetLargeDisabledImages.md)|Возвращает указатель на коллекции больших отключенных изображений кнопок панели инструментов в приложении.|  
|[CMFCToolBar::GetLargeImages](../Topic/CMFCToolBar::GetLargeImages.md)|Возвращает указатель на коллекции больших изображений кнопок панели инструментов в приложении.|  
|[CMFCToolBar::GetLockedColdImages](../Topic/CMFCToolBar::GetLockedColdImages.md)|Возвращает указатель на коллекцию холодных блокированных изображений на панели инструментов.|  
|[CMFCToolBar::GetLockedDisabledImages](../Topic/CMFCToolBar::GetLockedDisabledImages.md)|Возвращает указатель на коллекции образов заблокированных заблокированным на панели инструментов.|  
|[CMFCToolBar::GetLockedImages](../Topic/CMFCToolBar::GetLockedImages.md)|Возвращает указатель на коллекции блокированных изображений кнопок на панели инструментов.|  
|[CMFCToolBar::GetLockedImageSize](../Topic/CMFCToolBar::GetLockedImageSize.md)|Возвращает размер по умолчанию образов блокированных панели инструментов.|  
|[CMFCToolBar::GetLockedMenuImages](../Topic/CMFCToolBar::GetLockedMenuImages.md)|Возвращает указатель на коллекции образов блокированных меню панели инструментов на панели инструментов.|  
|[CMFCToolBar::GetMenuButtonSize](../Topic/CMFCToolBar::GetMenuButtonSize.md)|Возвращает размер кнопок меню в приложении.|  
|[CMFCToolBar::GetMenuImageSize](../Topic/CMFCToolBar::GetMenuImageSize.md)|Возвращает размер изображений кнопок меню в приложении.|  
|[CMFCToolBar::GetMenuImages](../Topic/CMFCToolBar::GetMenuImages.md)|Возвращает указатель на коллекции изображений кнопок меню в приложении.|  
|[CMFCToolBar::GetOrigButtons](../Topic/CMFCToolBar::GetOrigButtons.md)|Извлекает коллекцию настраиваемых, отличного от кнопок панели инструментов.|  
|[CMFCToolBar::GetOrigResetButtons](../Topic/CMFCToolBar::GetOrigResetButtons.md)|Извлекает коллекцию настраиваемых возврата, отличного от кнопок панели инструментов.|  
|[CMFCToolBar::GetResourceID](../Topic/CMFCToolBar::GetResourceID.md)|Извлекает идентификатор ресурса панели инструментов.|  
|[CMFCToolBar::GetRouteCommandsViaFrame](../Topic/CMFCToolBar::GetRouteCommandsViaFrame.md)|Определяет, какой объект или владелец, отправляют родительским кадром команд на панели инструментов.|  
|[CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)|Возвращает высоту кнопок панели инструментов.|  
|[CMFCToolBar::GetShowTooltips](../Topic/CMFCToolBar::GetShowTooltips.md)|Указывает, отображаются ли всплывающие подсказки для кнопки панели инструментов.|  
|[CMFCToolBar::GetSiblingToolBar](../Topic/CMFCToolBar::GetSiblingToolBar.md)|Извлекает одноуровневый элемент панели инструментов.|  
|[CMFCToolBar::GetUserImages](../Topic/CMFCToolBar::GetUserImages.md)|Возвращает указатель на коллекцию определяемых пользователем изображений кнопок панели инструментов в приложении.|  
|[CMFCToolBar::HitTest](../Topic/CMFCToolBar::HitTest.md)|Возвращает индекс кнопки панели инструментов, найдено в заданной позиции.|  
|[CMFCToolBar::InsertButton](../Topic/CMFCToolBar::InsertButton.md)|Представляет кнопку на панели инструментов.|  
|[CMFCToolBar::InsertSeparator](../Topic/CMFCToolBar::InsertSeparator.md)|Вставляет разделитель на панели инструментов.|  
|[CMFCToolBar::InvalidateButton](../Topic/CMFCToolBar::InvalidateButton.md)|Делает недействительной клиентской области кнопки панели инструментов, существует по указанному индексу.|  
|[CMFCToolBar::IsAddRemoveQuickCustomize](../Topic/CMFCToolBar::IsAddRemoveQuickCustomize.md)|Указывает, может ли пользователь добавлять или удалять кнопки панели инструментов с помощью пункта меню **Настроить**.|  
|[CMFCToolBar::IsAltCustomizeMode](../Topic/CMFCToolBar::IsAltCustomizeMode.md)|Указывает, используется ли *быстрой настройкой* для перетаскивания.|  
|[CMFCToolBar::IsAutoGrayInactiveImages](../Topic/CMFCToolBar::IsAutoGrayInactiveImages.md)|Определяет, является ли включающие автоматическое формирование неактивных \(выделенных\), изображений кнопок.|  
|[CMFCToolBar::IsBasicCommand](../Topic/CMFCToolBar::IsBasicCommand.md)|Определяет, является ли команда в списке основных команд.|  
|[CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)|Определяет, является ли панель инструментов может отображаться кнопки, удлиняли границы.|  
|[CMFCToolBar::IsButtonHighlighted](../Topic/CMFCToolBar::IsButtonHighlighted.md)|Определяет, является ли выделена кнопки на панели инструментов.|  
|[CMFCToolBar::IsCommandPermitted](../Topic/CMFCToolBar::IsCommandPermitted.md)|Указывает, разрешена ли команда.|  
|[CMFCToolBar::IsCommandRarelyUsed](../Topic/CMFCToolBar::IsCommandRarelyUsed.md)|Указывает, используется ли команда редко \(см. [CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)\).|  
|[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)|Определяет, является ли границы панели инструментов в режиме настройки.|  
|[CMFCToolBar::IsDragButton](../Topic/CMFCToolBar::IsDragButton.md)|Определяет, перетащив ли кнопка панели инструментов.|  
|[CMFCToolBar::IsExistCustomizeButton](../Topic/CMFCToolBar::IsExistCustomizeButton.md)|Определяет, содержит ли панель инструментов кнопку **Настроить**.|  
|[CMFCToolBar::IsFloating](../Topic/CMFCToolBar::IsFloating.md)|Указывает, располагается ли панель инструментов.|  
|[CMFCToolBar::IsLargeIcons](../Topic/CMFCToolBar::IsLargeIcons.md)|Указывает, отображаются ли панели инструментов в приложении в настоящее время крупные значки.|  
|[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)|Указывает, была ли выполнена команда отправлена последним из указанной кнопки панели инструментов.|  
|[CMFCToolBar::IsLocked](../Topic/CMFCToolBar::IsLocked.md)|Определяет, является ли панель инструментов блокирована.|  
|[CMFCToolBar::IsOneRowWithSibling](../Topic/CMFCToolBar::IsOneRowWithSibling.md)|Определяет, находятся ли панель инструментов и панели инструментов одноуровневого на одну и ту же строку.|  
|[CMFCToolBar::IsUserDefined](../Topic/CMFCToolBar::IsUserDefined.md)|Определяет, является ли панель инструментов определяется пользователем.|  
|[CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)|Загружает образы панели инструментов из ресурсов приложения.|  
|[CMFCToolBar::LoadBitmapEx](../Topic/CMFCToolBar::LoadBitmapEx.md)|Загружает образы панели инструментов из ресурсов приложения.  Включает большие изображений.|  
|[CMFCToolBar::LoadParameters](../Topic/CMFCToolBar::LoadParameters.md)|Загружает глобальные параметры панели инструментов из реестра Windows.|  
|[CMFCToolBar::LoadState](../Topic/CMFCToolBar::LoadState.md)|Загружает сведения о состоянии панели инструментов из реестра Windows.  \(Переопределяет [CPane::LoadState](../Topic/CPane::LoadState.md)\).|  
|[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)|Загружает панель инструментов из ресурсов приложения.|  
|[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)|Загружает панель инструментов из ресурсов приложения с помощью вспомогательного класса `CMFCToolBarInfo`, чтобы разрешить приложению использовать большие изображений.|  
|[CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)|Вызываемый платформой, когда пользователь выбирает кнопку на панели инструментов.|  
|[CMFCToolBar::OnFillBackground](../Topic/CMFCToolBar::OnFillBackground.md)|Вызываемый платформой из [CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md) для заливки фона панели инструментов.|  
|[CMFCToolBar::OnReset](../Topic/CMFCToolBar::OnReset.md)|Извлекает панели инструментов в исходное состояние.|  
|[CMFCToolBar::OnSetAccData](../Topic/CMFCToolBar::OnSetAccData.md)|\(Переопределяет [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)\).|  
|[CMFCToolBar::OnSetDefaultButtonText](../Topic/CMFCToolBar::OnSetDefaultButtonText.md)|Извлекает текст кнопки панели инструментов в состоянии по умолчанию.|  
|`CMFCToolBar::OnUpdateCmdUI`|Для внутреннего использования.|  
|[CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)|Удаляет все кнопки на панели инструментов.|  
|[CMFCToolBar::RemoveButton](../Topic/CMFCToolBar::RemoveButton.md)|Удаляет кнопку с указанным индексом из панели инструментов.|  
|[CMFCToolBar::RemoveStateFromRegistry](../Topic/CMFCToolBar::RemoveStateFromRegistry.md)|Удаляет сведения о состоянии панели инструментов из реестра Windows.|  
|[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)|Заменяет кнопка панели инструментов с кнопкой панели инструментов.|  
|[CMFCToolBar::ResetAll](../Topic/CMFCToolBar::ResetAll.md)|Извлекает все панели инструментов в исходном состояниям.|  
|[CMFCToolBar::ResetAllImages](../Topic/CMFCToolBar::ResetAllImages.md)|Удаляет все коллекции образа панели инструментов в приложении.|  
|[CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)|Получает исходное состояние панели инструментов.|  
|[CMFCToolBar::SaveState](../Topic/CMFCToolBar::SaveState.md)|Сохраняет сведения о состоянии панели инструментов в реестре Windows.  \(Переопределяет [CPane::SaveState](../Topic/CPane::SaveState.md)\).|  
|`CMFCToolBar::Serialize`|\(Переопределяет `CBasePane::Serialize`\).|  
|[CMFCToolBar::SetBasicCommands](../Topic/CMFCToolBar::SetBasicCommands.md)|Задает список команд, которые отображаются всегда, когда пользователь открывает меню.|  
|[CMFCToolBar::SetButtonInfo](../Topic/CMFCToolBar::SetButtonInfo.md)|Задает идентификатор команды, стиль и идентификатор образа кнопки панели инструментов.|  
|[CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)|Задает стиль кнопок панели инструментов с заданного индекса.|  
|[CMFCToolBar::SetButtonText](../Topic/CMFCToolBar::SetButtonText.md)|Задает текстовую подпись кнопки панели инструментов.|  
|[CMFCToolBar::SetButtons](../Topic/CMFCToolBar::SetButtons.md)|Задает кнопки панели инструментов.|  
|[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)|Указывает, когда редко используемые команды не отображаются в меню приложения.|  
|[CMFCToolBar::SetCustomizeMode](../Topic/CMFCToolBar::SetCustomizeMode.md)|Включение или отключение режима настройки для всех панелей инструментов в приложении.|  
|[CMFCToolBar::SetGrayDisabledButtons](../Topic/CMFCToolBar::SetGrayDisabledButtons.md)|Определяет, можно ли уменьшить яркость отключенные кнопки на панели инструментов или если отключенные образы используются для отключенных кнопок.|  
|[CMFCToolBar::SetHeight](../Topic/CMFCToolBar::SetHeight.md)|Задает высоту панели инструментов.|  
|[CMFCToolBar::SetHotBorder](../Topic/CMFCToolBar::SetHotBorder.md)|Определяет, является ли высокий\- отслеживаются кнопки панели инструментов.|  
|[CMFCToolBar::SetHotTextColor](../Topic/CMFCToolBar::SetHotTextColor.md)|Задает цвет текста для кнопок панели инструментов в активном состоянии.|  
|[CMFCToolBar::SetLargeIcons](../Topic/CMFCToolBar::SetLargeIcons.md)|Указывает, отображаются ли кнопки панели инструментов крупные значки.|  
|[CMFCToolBar::SetLockedSizes](../Topic/CMFCToolBar::SetLockedSizes.md)|Устанавливает размеры блокированных и блокировать изображений кнопок на панели инструментов.|  
|[CMFCToolBar::SetMenuSizes](../Topic/CMFCToolBar::SetMenuSizes.md)|Задает размер кнопок меню, панели инструментов и их изображений.|  
|[CMFCToolBar::SetNonPermittedCommands](../Topic/CMFCToolBar::SetNonPermittedCommands.md)|Задает список команд, которые не могут быть исполнитьы пользователем.|  
|[CMFCToolBar::SetOneRowWithSibling](../Topic/CMFCToolBar::SetOneRowWithSibling.md)|Располагает панелью инструментов и его одноуровневый элемент на том же гребет.|  
|[CMFCToolBar::SetPermament](../Topic/CMFCToolBar::SetPermament.md)|Указывает, может ли пользователь закрыть панель инструментов.|  
|[CMFCToolBar::SetRouteCommandsViaFrame](../Topic/CMFCToolBar::SetRouteCommandsViaFrame.md)|Определяет, отправляет ли родительский кадр или владелец команды на панели инструментов.|  
|[CMFCToolBar::SetShowTooltips](../Topic/CMFCToolBar::SetShowTooltips.md)|Указывает, отображаются ли границы всплывающие подсказки.|  
|[CMFCToolBar::SetSiblingToolBar](../Topic/CMFCToolBar::SetSiblingToolBar.md)|Определяет одноуровневый элемент панели инструментов.|  
|[CMFCToolBar::SetSizes](../Topic/CMFCToolBar::SetSizes.md)|Определяет размер кнопок и образы для всех панелях инструментов.|  
|[CMFCToolBar::SetToolBarBtnText](../Topic/CMFCToolBar::SetToolBarBtnText.md)|Определяет свойства кнопок на панели инструментов.|  
|[CMFCToolBar::SetTwoRowsWithSibling](../Topic/CMFCToolBar::SetTwoRowsWithSibling.md)|Располагает панелью инструментов и его элемент того же уровня на отдельные строки.|  
|[CMFCToolBar::SetUserImages](../Topic/CMFCToolBar::SetUserImages.md)|Задает коллекцию определяемых пользователем изображений в приложении.|  
|[CMFCToolBar::StretchPane](../Topic/CMFCToolBar::StretchPane.md)|Растянет панель инструментов по вертикали или по горизонтали. \(Переопределяет [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)\).|  
|[CMFCToolBar::TranslateChar](../Topic/CMFCToolBar::TranslateChar.md)|Выполняет команду кнопки, если код заданного ключа соответствует сочетанию клавиш являются допустимыми.|  
|[CMFCToolBar::UpdateButton](../Topic/CMFCToolBar::UpdateButton.md)|Обновляет состояние указанной кнопки.|  
|[CMFCToolBar::WrapToolBar](../Topic/CMFCToolBar::WrapToolBar.md)|Перемещает кнопки панели инструментов в заданном измерений.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBar::AllowShowOnList](../Topic/CMFCToolBar::AllowShowOnList.md)|Указывает, отображается ли панель инструментов в списке на панели **Панели инструментов** диалогового окна **Настроить**.|  
|[CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)|Вычисляет максимальную высоту кнопок на панели инструментов.|  
|[CMFCToolBar::DoPaint](../Topic/CMFCToolBar::DoPaint.md)|Обновляет панель инструментов.|  
|[CMFCToolBar::DrawButton](../Topic/CMFCToolBar::DrawButton.md)|Обновляет кнопки панели инструментов.|  
|[CMFCToolBar::DrawSeparator](../Topic/CMFCToolBar::DrawSeparator.md)|Обновляет разделителя на панели инструментов.|  
|[CMFCToolBar::OnUserToolTip](../Topic/CMFCToolBar::OnUserToolTip.md)|Вызываемый платформой, когда подсказки для кнопки будет отображаться.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBar::m\_bDontScaleImages](../Topic/CMFCToolBar::m_bDontScaleImages.md)|Определяет, является ли масштабирование или не образы панели инструментов на высоком режиме ТОЧКА НА ДЮЙМ.|  
|[CMFCToolBar::m\_dblLargeImageRatio](../Topic/CMFCToolBar::m_dblLargeImageRatio.md)|Определяет отношение между измерением \(высоты или ширины\) больших изображений и измерением обычных изображений.|  
  
## Заметки  
 Для включения объект `CMFCToolBar` в приложении, выполните следующие действия:  
  
1.  Добавьте объект `CMFCToolBar` к главному фреймовому окно.  
  
2.  При обработке сообщения `WM_CREATE` для главного фреймового окна, вызовите метод [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md) или [CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md) чтобы создать панель инструментов и задать его стиль.  
  
3.  Вызовите [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md), чтобы определить стиль закрепления.  
  
 Ввод специальной кнопки, в поле со списком или раскрывающаяся панель инструментов, резервирует думмичную кнопку в родительском ресурсе и заменяет думмичная кнопка во время выполнения с помощью [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  Дополнительные сведения см. в разделе [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
 `CMFCToolBar` базовый класс для классов [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md), [Класс CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) и [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) библиотеки MFC.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCToolBar`.  Примере показано, как задать текст метки окна панели инструментов, чтобы задать границы, чтобы задать стиль панели и включить кнопку **Добавить или удалить кнопки**, которая отображается на окончании панели инструментов.  Этот фрагмент кода является частью [Пример demo IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#6](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#8](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_2.cpp)]  
  
## Требования  
 **заголовок:** afxtoolbar.h  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md)   
 [Класс CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)