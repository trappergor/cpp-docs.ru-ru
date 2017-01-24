---
title: "CToolBarCtrl Class | Microsoft Docs"
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
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl class"
  - "всплывающие подсказки [C++], уведомления"
  - "элементы управления панели инструментов [MFC], CToolBarCtrl class"
  - "Windows common controls [C++], CToolBarCtrl"
ms.assetid: 8f2f8ad2-05d7-4975-8715-3f2eed795248
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CToolBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления панели инструментов Windows общего.  
  
## Синтаксис  
  
```  
class CToolBarCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CToolBarCtrl::CToolBarCtrl](../Topic/CToolBarCtrl::CToolBarCtrl.md)|Создает объект `CToolBarCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CToolBarCtrl::AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md)|Добавляет один или несколько изображений кнопок растрового изображения в список изображений кнопок, доступных для элемента управления панели инструментов.|  
|[CToolBarCtrl::AddButtons](../Topic/CToolBarCtrl::AddButtons.md)|Добавляет один или несколько кнопок к элементу управления " Панель инструментов.|  
|[CToolBarCtrl::AddString](../Topic/CToolBarCtrl::AddString.md)|Добавляет новую строку, передаваемого в качестве идентификатора ресурса в список панели инструментов внутреннее строк.|  
|[CToolBarCtrl::AddStrings](../Topic/CToolBarCtrl::AddStrings.md)|Добавляет новые строки или строк, переданных как указатель на буфер null\-, разделенных строк в список панели инструментов внутреннее строк.|  
|[CToolBarCtrl::AutoSize](../Topic/CToolBarCtrl::AutoSize.md)|Изменяет размер элемента управления панели инструментов.|  
|[CToolBarCtrl::ChangeBitmap](../Topic/CToolBarCtrl::ChangeBitmap.md)|Изменяет растровое изображение для кнопки в текущем элементе управления " Панель инструментов.|  
|[CToolBarCtrl::CheckButton](../Topic/CToolBarCtrl::CheckButton.md)|Проверка целостности или снимите клиринги данной кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::CommandToIndex](../Topic/CToolBarCtrl::CommandToIndex.md)|Извлекает нулевой\- основан индекс для кнопки, связанной с указанным идентификатором команды.|  
|[CToolBarCtrl::Create](../Topic/CToolBarCtrl::Create.md)|Создает элемент управления " Панель инструментов и вложение его к объекту `CToolBarCtrl`.|  
|[CToolBarCtrl::CreateEx](../Topic/CToolBarCtrl::CreateEx.md)|Создает элемент управления " Панель инструментов с заданными стилей расширенными Windows и вложение его к объекту `CToolBarCtrl`.|  
|[CToolBarCtrl::Customize](../Topic/CToolBarCtrl::Customize.md)|Открывает диалоговое окно настройки панели инструментов.|  
|[CToolBarCtrl::DeleteButton](../Topic/CToolBarCtrl::DeleteButton.md)|Удаляет из элемента управления кнопка панели инструментов.|  
|[CToolBarCtrl::EnableButton](../Topic/CToolBarCtrl::EnableButton.md)|Включение или отключение указанную кнопку в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::GetAnchorHighlight](../Topic/CToolBarCtrl::GetAnchorHighlight.md)|Извлекает параметр выделения привязки для панели инструментов.|  
|[CToolBarCtrl::GetBitmap](../Topic/CToolBarCtrl::GetBitmap.md)|Извлекает индекс растрового изображения, связанного с кнопкой на панели инструментов.|  
|[CToolBarCtrl::GetBitmapFlags](../Topic/CToolBarCtrl::GetBitmapFlags.md)|Возвращает флаги, связанные с растровым изображением панели инструментов.|  
|[CToolBarCtrl::GetButton](../Topic/CToolBarCtrl::GetButton.md)|Возвращает сведения об указанной кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::GetButtonCount](../Topic/CToolBarCtrl::GetButtonCount.md)|Получает число кнопок в данный момент в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::GetButtonInfo](../Topic/CToolBarCtrl::GetButtonInfo.md)|Извлекает сведения для кнопок на панели инструментов.|  
|[CToolBarCtrl::GetButtonSize](../Topic/CToolBarCtrl::GetButtonSize.md)|Извлекает текущую ширину и высоту кнопок панели инструментов в пикселях.|  
|[CToolBarCtrl::GetColorScheme](../Topic/CToolBarCtrl::GetColorScheme.md)|Возвращает цветовую схему текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md)|Извлекает список образа, элемент управления " Панель инструментов используется для отображения отключенных кнопок.|  
|[CToolBarCtrl::GetDropTarget](../Topic/CToolBarCtrl::GetDropTarget.md)|Извлекает интерфейс [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetExtendedStyle](../Topic/CToolBarCtrl::GetExtendedStyle.md)|Получает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md)|Извлекает список образа, элемент управления " Панель инструментов "активном состоянии" используется для отображения кнопки.  Горячая кнопка отображается выбранной, когда указатель мыши над ним.|  
|[CToolBarCtrl::GetHotItem](../Topic/CToolBarCtrl::GetHotItem.md)|Извлекает индекс горячего элемента на панели инструментов.|  
|[CToolBarCtrl::GetImageList](../Topic/CToolBarCtrl::GetImageList.md)|Извлекает список образа, элемент управления " Панель инструментов используется для отображения кнопок в их состоянии по умолчанию.|  
|[CToolBarCtrl::GetInsertMark](../Topic/CToolBarCtrl::GetInsertMark.md)|Извлекает текущую знак вставки на панели инструментов.|  
|[CToolBarCtrl::GetInsertMarkColor](../Topic/CToolBarCtrl::GetInsertMarkColor.md)|Возвращает цвет, используемый для рисования знак вставки на панели инструментов.|  
|[CToolBarCtrl::GetItemRect](../Topic/CToolBarCtrl::GetItemRect.md)|Получает ограничивающий прямоугольник кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::GetMaxSize](../Topic/CToolBarCtrl::GetMaxSize.md)|Извлекает полный размер всех видимых и разделители кнопок на панели инструментов.|  
|[CToolBarCtrl::GetMaxTextRows](../Topic/CToolBarCtrl::GetMaxTextRows.md)|Получает максимальное количество строк текста, отображаемых на кнопке панели инструментов.|  
|[CToolBarCtrl::GetMetrics](../Topic/CToolBarCtrl::GetMetrics.md)|Извлекает метрики элемента управления панели инструментов.|  
|[CToolBarCtrl::GetPadding](../Topic/CToolBarCtrl::GetPadding.md)|Возвращает горизонтальную и вертикальная величина заполнения текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::GetPressedImageList](../Topic/CToolBarCtrl::GetPressedImageList.md)|Извлекает список образа, текущий элемент управления " Панель инструментов используется для представления кнопку в нажатом состоянии.|  
|[CToolBarCtrl::GetRect](../Topic/CToolBarCtrl::GetRect.md)|Возвращает ограничивающий прямоугольник для указанной кнопки панели инструментов.|  
|[CToolBarCtrl::GetRows](../Topic/CToolBarCtrl::GetRows.md)|Извлекает число строк, отображаемых в данный момент кнопок на панели инструментов.|  
|[CToolBarCtrl::GetState](../Topic/CToolBarCtrl::GetState.md)|Извлекает сведения о состоянии указанной кнопки в элементе управления " Панель инструментов, например, включен ли он, нажат или проверить.|  
|[CToolBarCtrl::GetString](../Topic/CToolBarCtrl::GetString.md)|Извлекает строку панели инструментов.|  
|[CToolBarCtrl::GetStyle](../Topic/CToolBarCtrl::GetStyle.md)|Получает стили в настоящий момент используется для элемента управления панели инструментов.|  
|[CToolBarCtrl::GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md)|Извлекает маркер управления всплывающей подсказки, если таковые имеются, связанного с элементом управления toolbar.|  
|[CToolBarCtrl::HideButton](../Topic/CToolBarCtrl::HideButton.md)|Показать или скрывает указанную кнопку в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::HitTest](../Topic/CToolBarCtrl::HitTest.md)|Указывает, где точка находится в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::Indeterminate](../Topic/CToolBarCtrl::Indeterminate.md)|Задает или снимите клиринги непредвиденное \(серое\) состояние указанной кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::InsertButton](../Topic/CToolBarCtrl::InsertButton.md)|Вставляет элемент управления кнопка на панели инструментов.|  
|[CToolBarCtrl::InsertMarkHitTest](../Topic/CToolBarCtrl::InsertMarkHitTest.md)|Извлекает сведения о знака вставки для точки на панели инструментов.|  
|[CToolBarCtrl::IsButtonChecked](../Topic/CToolBarCtrl::IsButtonChecked.md)|Указывает, является ли проверена указанную кнопку в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::IsButtonEnabled](../Topic/CToolBarCtrl::IsButtonEnabled.md)|Указывает, является ли указанная кнопка включена в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::IsButtonHidden](../Topic/CToolBarCtrl::IsButtonHidden.md)|Указывает, является ли скрыта указанную кнопку в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::IsButtonHighlighted](../Topic/CToolBarCtrl::IsButtonHighlighted.md)|Проверяет состояние выделения кнопки панели инструментов.|  
|[CToolBarCtrl::IsButtonIndeterminate](../Topic/CToolBarCtrl::IsButtonIndeterminate.md)|Указывает, является ли состояние указанной кнопки в элементе управления "Панель инструментов" неожиданно \(серый\).|  
|[CToolBarCtrl::IsButtonPressed](../Topic/CToolBarCtrl::IsButtonPressed.md)|Указывает, является ли указанная кнопка нажата в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::LoadImages](../Topic/CToolBarCtrl::LoadImages.md)|Загружает образ растровых изображений в Панель инструментов элемента управления списка.|  
|[CToolBarCtrl::MapAccelerator](../Topic/CToolBarCtrl::MapAccelerator.md)|Сопоставляет символы сочетания клавиш к кнопке панели инструментов.|  
|[CToolBarCtrl::MarkButton](../Topic/CToolBarCtrl::MarkButton.md)|Устанавливает состояние выделения данной кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::MoveButton](../Topic/CToolBarCtrl::MoveButton.md)|Перемещает кнопку из одного индекса в другой.|  
|[CToolBarCtrl::PressButton](../Topic/CToolBarCtrl::PressButton.md)|Давления или выпуски указанную кнопку в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::ReplaceBitmap](../Topic/CToolBarCtrl::ReplaceBitmap.md)|Заменяет существующий растровое изображение в текущем элементе управления " Панель инструментов с новым растровым изображением.|  
|[CToolBarCtrl::RestoreState](../Topic/CToolBarCtrl::RestoreState.md)|Извлекает состояние элемента управления панели инструментов.|  
|[CToolBarCtrl::SaveState](../Topic/CToolBarCtrl::SaveState.md)|Сохраняет состояние элемента управления панели инструментов.|  
|[CToolBarCtrl::SetAnchorHighlight](../Topic/CToolBarCtrl::SetAnchorHighlight.md)|Устанавливает параметр выделения привязки для панели инструментов.|  
|[CToolBarCtrl::SetBitmapSize](../Topic/CToolBarCtrl::SetBitmapSize.md)|Задает размер bitmapped изображений, добавляемый к элементу управления " Панель инструментов.|  
|[CToolBarCtrl::SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)|Задает сведения для существующей кнопок на панели инструментов.|  
|[CToolBarCtrl::SetButtonSize](../Topic/CToolBarCtrl::SetButtonSize.md)|Задает размер кнопок, добавляемый к элементу управления " Панель инструментов.|  
|[CToolBarCtrl::SetButtonStructSize](../Topic/CToolBarCtrl::SetButtonStructSize.md)|Задает размер структуры `TBBUTTON`.|  
|[CToolBarCtrl::SetButtonWidth](../Topic/CToolBarCtrl::SetButtonWidth.md)|Задает минимальное и максимальное ширина кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::SetCmdID](../Topic/CToolBarCtrl::SetCmdID.md)|Задает идентификатор команды, которая должна быть отправлена к окну "Владелец", если указанная кнопка нажата.|  
|[CToolBarCtrl::SetColorScheme](../Topic/CToolBarCtrl::SetColorScheme.md)|Задает цветовую схему текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md)|Задает список образа, элемент управления " Панель инструментов будет использоваться для отображения отключенных кнопок.|  
|[CToolBarCtrl::SetDrawTextFlags](../Topic/CToolBarCtrl::SetDrawTextFlags.md)|Устанавливает флаги в функции Win32 [DrawText](http://msdn.microsoft.com/library/windows/desktop/dd162498), которая используется для рисования текста в заданном прямоугольнике, отформатированное в соответствии с например флаги установлены.|  
|[CToolBarCtrl::SetExtendedStyle](../Topic/CToolBarCtrl::SetExtendedStyle.md)|Задает расширенные стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md)|Задает список образа, элемент управления " Панель инструментов "будет использоваться для отображения активном состоянии" кнопок.|  
|[CToolBarCtrl::SetHotItem](../Topic/CToolBarCtrl::SetHotItem.md)|Задает активный элемент на панели инструментов.|  
|[CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md)|Задает список образа, панель инструментов будет использоваться для отображения кнопок, в состоянии по умолчанию.|  
|[CToolBarCtrl::SetIndent](../Topic/CToolBarCtrl::SetIndent.md)|Устанавливает отступ для первой кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::SetInsertMark](../Topic/CToolBarCtrl::SetInsertMark.md)|Задает текущую метку вставки панели инструментов.|  
|[CToolBarCtrl::SetInsertMarkColor](../Topic/CToolBarCtrl::SetInsertMarkColor.md)|Устанавливает цвет, используемый для рисования знак вставки на панели инструментов.|  
|[CToolBarCtrl::SetMaxTextRows](../Topic/CToolBarCtrl::SetMaxTextRows.md)|Задает максимальное количество строк текста, отображаемых на кнопке панели инструментов.|  
|[CToolBarCtrl::SetMetrics](../Topic/CToolBarCtrl::SetMetrics.md)|Устанавливает метрики элемента управления панели инструментов.|  
|[CToolBarCtrl::SetOwner](../Topic/CToolBarCtrl::SetOwner.md)|Устанавливает флажок, чтобы получать сообщения уведомления из элемента управления " Панель инструментов.|  
|[CToolBarCtrl::SetPadding](../Topic/CToolBarCtrl::SetPadding.md)|Задает горизонтальную и вертикальную заполнения текущего элемента управления панели инструментов.|  
|[CToolBarCtrl::SetPressedImageList](../Topic/CToolBarCtrl::SetPressedImageList.md)|Задает список образа, текущий элемент управления " Панель инструментов используется для представления кнопку в нажатом состоянии.|  
|[CToolBarCtrl::SetRows](../Topic/CToolBarCtrl::SetRows.md)|Задает число строк кнопок, отображаемых на панели инструментов.|  
|[CToolBarCtrl::SetState](../Topic/CToolBarCtrl::SetState.md)|Задает состояние для указанной кнопки в элементе управления " Панель инструментов.|  
|[CToolBarCtrl::SetStyle](../Topic/CToolBarCtrl::SetStyle.md)|Задает стили для элемента управления панели инструментов.|  
|[CToolBarCtrl::SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md)|Связывает элемент управления всплывающей подсказки с элементом управления toolbar.|  
|[CToolBarCtrl::SetWindowTheme](../Topic/CToolBarCtrl::SetWindowTheme.md)|Задает визуальный стиль элемента управления панели инструментов.|  
  
## Заметки  
 Этот элемент управления \(и, следовательно, класс `CToolBarCtrl` \) доступны только для программ, выполняемых в рамках \/98 Windows версии 3.51 и Windows NT 95 и более поздних версий.  
  
 Элемент управления панели инструментов Windows общее прямоугольное дочернее окно, содержащее один или несколько кнопок.  Эти кнопки могут отображать образ растрового изображения строку или оба.  Когда пользователь выбирает кнопку, он отправляет сообщение команды в окно владельцем панели инструментов.  Как правило, кнопок на панели инструментов соответствуют элементам в меню приложения; они предоставляют более прямым способом для пользователя доступа к командам приложения.  
  
 Объекты `CToolBarCtrl` содержат несколько важных внутренних структур данных: список растровых изображений образа кнопки или список образа список строк метки кнопки и список структур `TBBUTTON`, которые связывают образ и\/или строка с позиции, вставки стилей, состояние и управляет идентификатор кнопки.  Каждый из элементов этих структур данных, на которую ссылается by в соответствии нулевой\- индексу.  Прежде чем использовать объект `CToolBarCtrl` необходимо настроить эти структуры данных.  Список строк может использоваться только для меток кнопки. невозможно получить строки из панели инструментов.  
  
 Чтобы использовать объект `CToolBarCtrl`, как правило, выполните следующие действия:  
  
1.  Создайте объект `CToolBarCtrl`.  
  
2.  Вызовите [Создание](../Topic/CToolBarCtrl::Create.md) для создания элемента управления панели инструментов Windows общее и вложить его к объекту `CToolBarCtrl`.  Укажите стиль панели инструментов с помощью стилей, как **TBSTYLE\_TRANSPARENT** для прозрачной панели инструментов или **TBSTYLE\_DROPDOWN** для кнопки панели инструментов обозреватель раскрывающиеся этого стиля.  
  
3.  Укажите способ кнопки, отображаемой на панели инструментов.  
  
    -   Для использования образов растрового изображения для кнопок, добавление растровых изображений кнопок на панели инструментов, вызвав [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md).  
  
    -   Для использования изображений, отображаемых в списке завершения образа для кнопок, укажите список образа путем вызова [SetImageList](../Topic/CToolBarCtrl::SetImageList.md), [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md) или [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md).  
  
    -   Для использования меток строк для кнопок добавить строки на панели инструментов путем вызова [AddString](../Topic/CToolBarCtrl::AddString.md) и\/или [AddStrings](../Topic/CToolBarCtrl::AddStrings.md).  
  
4.  Добавление структуры кнопки панели инструментов путем вызова [AddButtons](../Topic/CToolBarCtrl::AddButtons.md).  
  
5.  Если требуется всплывающие подсказки для кнопки панели инструментов в окне "Владелец", не является `CFrameWnd` необходимо обрабатывать сообщения **TTN\_NEEDTEXT** в поле "Владелец" панели инструментов, как описано в [Обработка уведомления всплывающей подсказки](../../mfc/handling-tool-tip-notifications.md).  Если родительское окно панели инструментов выводится из `CFrameWnd`, всплывающие подсказки отображаются без какого\-либо дополнительного автоматически, поскольку принудительное из `CFrameWnd` предоставляет используемый по умолчанию обработчик.  
  
6.  Если пользователь должен иметь возможность настраивать панели инструментов, то обработка сообщения уведомления настройки в поле "Владелец", как описано в [Обработка уведомления настройки](../Topic/Handling%20Customization%20Notifications.md).  
  
 Можно использовать [SaveState](../Topic/CToolBarCtrl::SaveState.md) чтобы сохранить текущее состояние элемента управления панели инструментов в реестре и [RestoreState](../Topic/CToolBarCtrl::RestoreState.md) для восстановления состояния ранее на основе сведений, хранящихся в реестре.  Помимо сохранения состояния панели инструментов между пользами приложения хранилища приложений обычно состояние, прежде чем пользователь начинает настраивать панели инструментов в случае, если пользователь позже нужно извлечь панели инструментов в исходное состояние.  
  
## Поддержка Internet Explorer версии 4.0 и выше  
 Для поддержки функциональных возможностей, введенную в Internet Explorer версии 4.0 и более поздние версии MFC обеспечивает поддержку списка образа и прозрачные и плоские стилей для элементов управления панели инструментов.  
  
 Прозрачная панель инструментов позволяет клиенту под панелью инструментов показать до конца.  Для создания прозрачная, используйте панель инструментов и **TBSTYLE\_FLAT** и стили **TBSTYLE\_TRANSPARENT**.  Прозрачные области элементов отличаются горячим отслеживанием; то есть когда указатель мыши перемещается над горячей кнопкой на панели инструментов, внешний вид кнопки изменяется.  Панели инструментов, созданные только с учетом **TBSTYLE\_FLAT**, которые не будут содержать кнопки прозрачный.  
  
 Поддержка списка образа позволяет элементу управления большая гибкость для расширения функциональности по умолчанию активном изображений и отключенных изображений.  Используйте [GetImageList](../Topic/CToolBarCtrl::GetImageList.md), [GetHotImageList](../Topic/CToolBarCtrl::GetHotImageList.md) и [GetDisabledImageList](../Topic/CToolBarCtrl::GetDisabledImageList.md) с прозрачным панелью инструментов для обработки образ в соответствии с его состоянием:  
  
 Дополнительные сведения об использовании `CToolBarCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CToolBarCtrl](../../mfc/using-ctoolbarctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CToolBarCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [MFC просматривает CMNCTRL1](../../top/visual-cpp-samples.md)   
 [Образец MFCIE MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)