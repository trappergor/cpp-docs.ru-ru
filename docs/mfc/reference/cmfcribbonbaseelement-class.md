---
title: "CMFCRibbonBaseElement Class | Microsoft Docs"
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
  - "CMFCRibbonBaseElement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBaseElement class"
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBaseElement Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonBaseElement` базовый класс для всех элементов, которые можно добавить к [область ленты](../../mfc/reference/cmfcribbonbar-class.md).  Примеры элементов ленты кнопки ленты, флажки ленты и поля со списком на ленте.  
  
## Синтаксис  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonBaseElement`|Создает объект `CMFCRibbonBaseElement`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonBaseElement::AddToKeyList](../Topic/CMFCRibbonBaseElement::AddToKeyList.md)|Добавляет keytip для элемента ленты в массив keytips.|  
|[CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)|Добавляет элемент ленты к указанному списку команд ленты.|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](../Topic/CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar.md)|Указывает, является ли элемент ленты можно добавить на панели инструментов быстрого доступа.|  
|[CMFCRibbonBaseElement::CanBeCompacted](../Topic/CMFCRibbonBaseElement::CanBeCompacted.md)|Указывает, является ли размер элемента ленты может быть компактн.|  
|[CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)|Указывает, является ли высота элемента ленты может увеличиваться по вертикали для высоты строки ленты.|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](../Topic/CMFCRibbonBaseElement::CanBeStretchedHorizontally.md)|Указывает, будет ли ширина элемента ленты может измениться.|  
|[CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)|Очищает параметры измерения для элемента ленты.|  
|[CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)|Закрыть контекстное меню для элемента меню ленты.|  
|[CMFCRibbonBaseElement::CopyFrom](../Topic/CMFCRibbonBaseElement::CopyFrom.md)|Копирует состояние заданного `CMFCRibbonBaseElement` к текущему объекту.|  
|[CMFCRibbonBaseElement::DestroyCtrl](../Topic/CMFCRibbonBaseElement::DestroyCtrl.md)|Удаляет элемент на ленте.|  
|[CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)|Рисует изображение для элемента ленты.|  
|[CMFCRibbonBaseElement::Find](../Topic/CMFCRibbonBaseElement::Find.md)|Возвращает заданный указатель к элементу ленты, если он указывает на текущий объект.|  
|[CMFCRibbonBaseElement::FindByData](../Topic/CMFCRibbonBaseElement::FindByData.md)|Извлекает указатель к элементу ленты, если он содержит указанные данные.|  
|[CMFCRibbonBaseElement::FindByID](../Topic/CMFCRibbonBaseElement::FindByID.md)|Извлекает указатель к элементу ленты, если этот элемент задан указанным идентификатором команды|  
|[CMFCRibbonBaseElement::FindByOriginal](../Topic/CMFCRibbonBaseElement::FindByOriginal.md)|Извлекает указатель к элементу ленты, если элемент на ленте исходного соответствующий указанному элементу ленты.|  
|[CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)|Возвращает компактный размер элемента ленты.|  
|[CMFCRibbonBaseElement::GetData](../Topic/CMFCRibbonBaseElement::GetData.md)|Извлекает определяемые пользователем данные, связанные с элементом ленты.|  
|[CMFCRibbonBaseElement::GetDescription](../Topic/CMFCRibbonBaseElement::GetDescription.md)|Возвращает описание элемента ленты.|  
|[CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md)|Извлекает указатель к элементу ленты, если его контекстное меню меню удалено вниз.|  
|[CMFCRibbonBaseElement::GetElements](../Topic/CMFCRibbonBaseElement::GetElements.md)|Добавляет текущий элемент ленты в указанный массив.|  
|[CMFCRibbonBaseElement::GetElementsByID](../Topic/CMFCRibbonBaseElement::GetElementsByID.md)|Добавляет текущий элемент ленты в указанный массив, если текущий элемент ленты содержит заданный идентификатор команды.|  
|[CMFCRibbonBaseElement::GetHighlighted](../Topic/CMFCRibbonBaseElement::GetHighlighted.md)|Извлекает указатель к элементу ленты, если элемент выбран.|  
|[CMFCRibbonBaseElement::GetID](../Topic/CMFCRibbonBaseElement::GetID.md)|Возвращает идентификатор команды элемента ленты.|  
|[CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)|Возвращает размер образа элемента ленты.|  
|[CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)|Возвращает размер элемента ленты в своем промежуточном состоянии.|  
|[CMFCRibbonBaseElement::GetKeys](../Topic/CMFCRibbonBaseElement::GetKeys.md)|Возвращает keytip, связанное с элементом ленты.|  
|[CMFCRibbonBaseElement::GetKeyTipRect](../Topic/CMFCRibbonBaseElement::GetKeyTipRect.md)|Получает прямоугольник границы keytip для элемента ленты.|  
|[CMFCRibbonBaseElement::GetKeyTipSize](../Topic/CMFCRibbonBaseElement::GetKeyTipSize.md)|Получает размер текста keytip.|  
|[CMFCRibbonBaseElement::GetLocationInGroup](../Topic/CMFCRibbonBaseElement::GetLocationInGroup.md)|Указывает место отображения элемента ленты в группе ленты.|  
|[CMFCRibbonBaseElement::GetMenuKeys](../Topic/CMFCRibbonBaseElement::GetMenuKeys.md)|Возвращает keytips, связанные с кнопкой.|  
|[CMFCRibbonBaseElement::GetNotifyID](../Topic/CMFCRibbonBaseElement::GetNotifyID.md)|Извлекает идентификатор команды уведомления для элемента ленты.|  
|[CMFCRibbonBaseElement::GetOriginal](../Topic/CMFCRibbonBaseElement::GetOriginal.md)|Извлекает исходный элемент " на ленте.|  
|[CMFCRibbonBaseElement::GetParentCategory](../Topic/CMFCRibbonBaseElement::GetParentCategory.md)|Получает категорию ленты для элемента ленты.|  
|[CMFCRibbonBaseElement::GetParentPanel](../Topic/CMFCRibbonBaseElement::GetParentPanel.md)|Извлекает область ленты, содержащую элемент ленты.|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](../Topic/CMFCRibbonBaseElement::GetParentRibbonBar.md)|Получает родительскую область ленты для элемента ленты.|  
|[CMFCRibbonBaseElement::GetParentWnd](../Topic/CMFCRibbonBaseElement::GetParentWnd.md)|Возвращает родительское окно для элемента ленты.|  
|[CMFCRibbonBaseElement::GetPressed](../Topic/CMFCRibbonBaseElement::GetPressed.md)|Извлекает указатель к элементу ленты, если пользователь нажимает ее в настоящее время.|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](../Topic/CMFCRibbonBaseElement::GetQuickAccessToolBarID.md)|Извлекает идентификатор команды элемента ленты, когда он найдено на панели инструментов быстрого доступа.|  
|[CMFCRibbonBaseElement::GetRect](../Topic/CMFCRibbonBaseElement::GetRect.md)|Возвращает ограничивающий прямоугольник элемента ленты.|  
|[CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)|Возвращает обычный размер элемента ленты.|  
|[CMFCRibbonBaseElement::GetSize](../Topic/CMFCRibbonBaseElement::GetSize.md)|Возвращает текущий размер элемента ленты.|  
|[CMFCRibbonBaseElement::GetText](../Topic/CMFCRibbonBaseElement::GetText.md)|Возвращает текст, связанный с элементом ленты.|  
|[CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)|Текст подсказки возвращений элемента ленты.|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](../Topic/CMFCRibbonBaseElement::GetTopLevelRibbonBar.md)|Извлекает область ленты верхнего уровня для элемента ленты.|  
|[CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)|Указывает, имеет ли элемент на ленте компактный режим.|  
|[CMFCRibbonBaseElement::HasFocus](../Topic/CMFCRibbonBaseElement::HasFocus.md)|Указывает, имеет ли родительский элемент фокус клавиатуры.|  
|[CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)|Указывает, имеет ли элемент на ленте промежуточный режим.|  
|[CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)|Указывает, имеет ли элемент лент большой режим.|  
|[CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)|Указывает, имеет ли элемент на ленте меню.|  
|[CMFCRibbonBaseElement::HitTest](../Topic/CMFCRibbonBaseElement::HitTest.md)|Извлекает указатель к элементу ленты, если указанная точка найдено в ней.|  
|[CMFCRibbonBaseElement::IsAlignByColumn](../Topic/CMFCRibbonBaseElement::IsAlignByColumn.md)|Указывает, является ли элемент ленты выравнивание по вертикали с другими элементами ленты.|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)|Указывает, является ли размер образа элемента ленты всегда большой.|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](../Topic/CMFCRibbonBaseElement::IsAutoRepeatMode.md)|Указывает, является ли элемент ленты в автоматическом режиме повторений.|  
|[CMFCRibbonBaseElement::IsChecked](../Topic/CMFCRibbonBaseElement::IsChecked.md)|Определяет проверить, является ли элемент на ленте.|  
|[CMFCRibbonBaseElement::IsCompactMode](../Topic/CMFCRibbonBaseElement::IsCompactMode.md)|Указывает, является ли элемент ленты в компактном режиме.|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](../Topic/CMFCRibbonBaseElement::IsDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::IsDisabled](../Topic/CMFCRibbonBaseElement::IsDisabled.md)|Определяет блокировку, является ли элемент на ленте.|  
|[CMFCRibbonBaseElement::IsDroppedDown](../Topic/CMFCRibbonBaseElement::IsDroppedDown.md)|Указывает, будут ли отображаться элемент раскрывающегося меню и контекстное меню ленты.|  
|[CMFCRibbonBaseElement::IsFocused](../Topic/CMFCRibbonBaseElement::IsFocused.md)|Указывает, имеет ли элемент фокус на ленте.|  
|[CMFCRibbonBaseElement::IsGalleryIcon](../Topic/CMFCRibbonBaseElement::IsGalleryIcon.md)|Указывает, содержится ли элемент ленты в коллекции ленты.|  
|[CMFCRibbonBaseElement::IsHighlighted](../Topic/CMFCRibbonBaseElement::IsHighlighted.md)|Определяет выбрать ли элемент на ленте.|  
|[CMFCRibbonBaseElement::IsIntermediateMode](../Topic/CMFCRibbonBaseElement::IsIntermediateMode.md)|Указывает, является ли текущий способ для элемента ленты средний размер.|  
|[CMFCRibbonBaseElement::IsLargeMode](../Topic/CMFCRibbonBaseElement::IsLargeMode.md)|Указывает, является ли текущий способ для элемента ленты большой \- заданный размер.|  
|[CMFCRibbonBaseElement::IsMenuMode](../Topic/CMFCRibbonBaseElement::IsMenuMode.md)|Указывает, содержится ли элемент в меню ленты.|  
|[CMFCRibbonBaseElement::IsPressed](../Topic/CMFCRibbonBaseElement::IsPressed.md)|Указывает, щелкнул ли пользователь элемент ленты.|  
|[CMFCRibbonBaseElement::IsQATMode](../Topic/CMFCRibbonBaseElement::IsQATMode.md)|Указывает, содержится ли элемент на панели инструментов быстрого доступа ленты.|  
|[CMFCRibbonBaseElement::IsSeparator](../Topic/CMFCRibbonBaseElement::IsSeparator.md)|Указывает, является ли элемент на ленте разделитель отображения.|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](../Topic/CMFCRibbonBaseElement::IsShowGroupBorder.md)|Указывает, содержится ли элемент на ленте в группе, которая показывает типичную границу.|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](../Topic/CMFCRibbonBaseElement::IsShowTooltipOnBottom.md)|Указывает, отображается ли подсказка под элементом ленты.|  
|[CMFCRibbonBaseElement::IsTabStop](../Topic/CMFCRibbonBaseElement::IsTabStop.md)|Указывает, является ли элемент ленты можно выбрать с помощью клавиатуры.|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::IsTextAlwaysOnRight.md)|Указывает, отображается ли текст для элемента ленты справа.|  
|[CMFCRibbonBaseElement::IsVisible](../Topic/CMFCRibbonBaseElement::IsVisible.md)|Указывает, отображается ли элемент ленты в данный момент.|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](../Topic/CMFCRibbonBaseElement::IsWholeRowHeight.md)|Указывает, является ли heigth отображения элемента ленты такой же, как и высота отображения области ленты, в которой он содержится.|  
|[CMFCRibbonBaseElement::NotifyCommand](../Topic/CMFCRibbonBaseElement::NotifyCommand.md)|Отправляет уведомление команды к родительскому окну элемента ленты.|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](../Topic/CMFCRibbonBaseElement::NotifyHighlightListItem.md)|Уведомляет родительское окно области ленты, когда пользователь выбирает элемент ленты, найти в списке.|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](../Topic/CMFCRibbonBaseElement::OnAddToQAToolbar.md)|Добавляет элемент ленты на указанной панели инструментов быстрого доступа.|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](../Topic/CMFCRibbonBaseElement::OnAfterChangeRect.md)|Обновляет подсказки для элемента ленты.|  
|[CMFCRibbonBaseElement::OnAutoRepeat](../Topic/CMFCRibbonBaseElement::OnAutoRepeat.md)|Обновляет элемент ленты в ответ на вытерпели входные данные пользователя.|  
|[CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)|Вычисляет размер текста для элемента ленты.|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](../Topic/CMFCRibbonBaseElement::OnChangeMenuHighlight.md)|Вызываемый платформой, если выделение изменений для элемента в меню ленты, чтобы найти.|  
|[CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)|Вызываемый платформой для рисования элемента ленты.|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](../Topic/CMFCRibbonBaseElement::OnDrawKeyTip.md)|Вызываемый платформой для рисования keytip для элемента ленты.|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)|Вызываемый платформой, когда будет создать образ меню для элемента ленты.|  
|[CMFCRibbonBaseElement::OnDrawOnList](../Topic/CMFCRibbonBaseElement::OnDrawOnList.md)|Вызываемый платформой для рисования элемента ленты в списке команды.|  
|[CMFCRibbonBaseElement::OnKey](../Topic/CMFCRibbonBaseElement::OnKey.md)|Вызываемый платформой, когда пользователь нажимает keytip и элемент ленты имеют фокус.|  
|[CMFCRibbonBaseElement::OnMenuKey](../Topic/CMFCRibbonBaseElement::OnMenuKey.md)||  
|[CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md)|Вызываемый платформой, если структура изменяет направление.|  
|[CMFCRibbonBaseElement::OnShow](../Topic/CMFCRibbonBaseElement::OnShow.md)|Вызываемый платформой, чтобы отображать или скрывать элемент ленты.|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](../Topic/CMFCRibbonBaseElement::OnShowPopupMenu.md)|Вызываемый платформой, когда элемент будет направлена отобразить контекстное меню меню ленты.|  
|[CMFCRibbonBaseElement::PostMenuCommand](../Topic/CMFCRibbonBaseElement::PostMenuCommand.md)||  
|[CMFCRibbonBaseElement::Redraw](../Topic/CMFCRibbonBaseElement::Redraw.md)|Обновляет отображение элемента ленты.|  
|[CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)|Задает сведения о специальных возможностей для элемента ленты.|  
|[CMFCRibbonBaseElement::SetCompactMode](../Topic/CMFCRibbonBaseElement::SetCompactMode.md)|Задает размер отображения элемента ленты.|  
|[CMFCRibbonBaseElement::SetData](../Topic/CMFCRibbonBaseElement::SetData.md)|Связывает элемент данных с элементом ленты.|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](../Topic/CMFCRibbonBaseElement::SetDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)|Задает описание для элемента ленты.|  
|[CMFCRibbonBaseElement::SetID](../Topic/CMFCRibbonBaseElement::SetID.md)|Задает идентификатор команды элемента ленты.|  
|[CMFCRibbonBaseElement::SetInitialMode](../Topic/CMFCRibbonBaseElement::SetInitialMode.md)|Задает начальный размер отображения элемента ленты.|  
|[CMFCRibbonBaseElement::SetKeys](../Topic/CMFCRibbonBaseElement::SetKeys.md)|Задает keytip для элемента ленты.|  
|[CMFCRibbonBaseElement::SetOriginal](../Topic/CMFCRibbonBaseElement::SetOriginal.md)|Задает исходный элемент ленты для элемента ленты.|  
|[CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)|Задает родительскую категорию элемента ленты.|  
|[CMFCRibbonBaseElement::SetParentMenu](../Topic/CMFCRibbonBaseElement::SetParentMenu.md)|Устанавливает родительский контейнер меню для элемента ленты.|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](../Topic/CMFCRibbonBaseElement::SetParentRibbonBar.md)|Задает родительскую область ленты для элемента ленты.|  
|[CMFCRibbonBaseElement::SetRect](../Topic/CMFCRibbonBaseElement::SetRect.md)|Устанавливает измерения fot отображается прямоугольник для элемента ленты.|  
|[CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)|Задает текст для элемента ленты.|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::SetTextAlwaysOnRight.md)|Задает текст для элемента ленты для отображения справа.|  
|[CMFCRibbonBaseElement::SetToolTipText](../Topic/CMFCRibbonBaseElement::SetToolTipText.md)|Задает текст подсказки для элемента ленты.|  
|[CMFCRibbonBaseElement::SetVisible](../Topic/CMFCRibbonBaseElement::SetVisible.md)|Устанавливает состояние видимости элемента ленты.|  
|[CMFCRibbonBaseElement::StretchHorizontally](../Topic/CMFCRibbonBaseElement::StretchHorizontally.md)|Растянет ширина элемента ленты.|  
|[CMFCRibbonBaseElement::StretchToWholeRow](../Topic/CMFCRibbonBaseElement::StretchToWholeRow.md)|Изменяет высоту отображения элемента ленты в указанной высоты строк.|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](../Topic/CMFCRibbonBaseElement::UpdateTooltipInfo.md)|Обновляет текст всплывающей подсказки с помощью ресурса команды для элемента ленты.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonBaseElement::OnProcessKey](../Topic/CMFCRibbonBaseElement::OnProcessKey.md)|Вызываемый платформой, когда пользователь отожмет сочетание клавиш.|  
|[CMFCRibbonBaseElement::OnSetFocus](../Topic/CMFCRibbonBaseElement::OnSetFocus.md)|Вызываемый платформой, когда элемент теряет фокус ввода получит или на ленте.|  
  
## Заметки  
 Класс `CMFCRibbonBaseElement` задает свойства, общие для всех элементов ленты, включающие идентификатор команды, текстовую подпись, текст подсказки, описание элемента и состояние, которое может фокусироваться \(выберите отключить, нажмите, чтобы проверить или списке\).  
  
 Размер образа элемента ленты определяется элементом `RibbonImageType`, может принимать одно из следующих значений:  
  
-   `RibbonImageLarge`  
  
-   `RibbonImageSmall`  
  
 В зависимости от ее размера элемента ленты показывает или маленький или большой образа.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCRibbonBaseElement`.  Примере показано, как получить объект `CMFCRibbonBaseElement` от класса `CMFCRibbonStatusBar` присвойте описание элемента ленты, установите текст, установите keytip и укажите текст подсказки для элемента ленты.  Этот фрагмент кода является частью [Образец клиента рисования](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#8](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_1.cpp)]  
[!code-cpp[NVC_MFC_DrawClient#9](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## Требования  
 **заголовок:** afxbaseribbonelement.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)