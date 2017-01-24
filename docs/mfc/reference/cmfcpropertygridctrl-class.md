---
title: "CMFCPropertyGridCtrl Class | Microsoft Docs"
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
  - "CMFCPropertyGridCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridCtrl class"
  - "CMFCPropertyGridCtrl::accHitTest method"
  - "CMFCPropertyGridCtrl::accLocation method"
  - "CMFCPropertyGridCtrl::get_accChild method"
  - "CMFCPropertyGridCtrl::get_accDefaultAction method"
  - "CMFCPropertyGridCtrl::get_accDescription method"
  - "CMFCPropertyGridCtrl::get_accName method"
  - "CMFCPropertyGridCtrl::get_accRole method"
  - "CMFCPropertyGridCtrl::get_accState method"
  - "CMFCPropertyGridCtrl::get_accValue method"
  - "CMFCPropertyGridCtrl::PreTranslateMessage method"
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Поддерживает редактируемые элемент управления сетки свойств, можно отобразить свойства в алфавитном или иерархическом порядке.  
  
## Синтаксис  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](../Topic/CMFCPropertyGridCtrl::CMFCPropertyGridCtrl.md)|Создает объект `CMFCPropertyGridCtrl`.|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCPropertyGridCtrl::accHitTest`|Вызываемый платформой для получения дочернего элемента или дочерний объект в заданной точке на экране.  \(Переопределяет [CWnd::accHitTest](../Topic/CWnd::accHitTest.md)\).|  
|`CMFCPropertyGridCtrl::accLocation`|Вызываемый платформой для получения расположения экрана указанного объекта и текущий.  \(Переопределяет [CWnd::accLocation](../Topic/CWnd::accLocation.md)\).|  
|[CMFCPropertyGridCtrl::accSelect](../Topic/CMFCPropertyGridCtrl::accSelect.md)|Вызываемый платформой, чтобы изменить выделение или переместить фокус клавиатуры для указанного объекта.  \(Переопределяет [CWnd::accSelect](../Topic/CWnd::accSelect.md)\).|  
|[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)|Добавляет новое свойство в элемент управления сетки свойств.|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::AlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](../Topic/CMFCPropertyGridCtrl::CloseColorPopup.md)|Закрывает диалоговое окно выбора цвета.|  
|[CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)|Создает элемент управления сетки свойств и вложение его к объекту управления сетки свойств.|  
|[CMFCPropertyGridCtrl::DeleteProperty](../Topic/CMFCPropertyGridCtrl::DeleteProperty.md)|Удаляет указанное свойство элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](../Topic/CMFCPropertyGridCtrl::DrawControlBarColors.md)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](../Topic/CMFCPropertyGridCtrl::EnableDescriptionArea.md)|Включение или отключение область описания, которая отображается под списком свойств.|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](../Topic/CMFCPropertyGridCtrl::EnableHeaderCtrl.md)|Включение или отключение элемент управления заголовка в верхней части элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::EnsureVisible](../Topic/CMFCPropertyGridCtrl::EnsureVisible.md)|Прокручивает элемент управления сетки свойств и развернуть элементы свойства до тех пор, пока указанное свойство не будет видимо.|  
|[CMFCPropertyGridCtrl::ExpandAll](../Topic/CMFCPropertyGridCtrl::ExpandAll.md)|Развернуть или свернуть все узлы элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::FindItemByData](../Topic/CMFCPropertyGridCtrl::FindItemByData.md)|Извлекает свойство, сопоставлено с определяемыми пользователем значение `DWORD`.|  
|`CMFCPropertyGridCtrl::get_accChild`|Вызываемый платформой для получения адреса интерфейса `IDispatch` для заданного дочернего элемента.  \(Переопределяет [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md)\).|  
|[CMFCPropertyGridCtrl::get\_accChildCount](../Topic/CMFCPropertyGridCtrl::get_accChildCount.md)|Вызываемый платформой для получения число дочерних объектов, принадлежащих этому объекту.  \(Переопределяет [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md)\).|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|Вызываемый платформой для получения строку, описывающую выполняемое по умолчанию объекта.  \(Переопределяет [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md)\).|  
|`CMFCPropertyGridCtrl::get_accDescription`|Вызываемый платформой для получения строку, описывающую внешний вид указанного объекта.  \(Переопределяет [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md)\).|  
|[CMFCPropertyGridCtrl::get\_accFocus](../Topic/CMFCPropertyGridCtrl::get_accFocus.md)|Вызываемый платформой для получения объект, имеющий фокус клавиатуры.  \(Переопределяет [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md)\).|  
|[CMFCPropertyGridCtrl::get\_accHelp](../Topic/CMFCPropertyGridCtrl::get_accHelp.md)|Вызываемый платформой для получения строки свойства `Help` объекта.  \(Переопределяет [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md)\).|  
|[CMFCPropertyGridCtrl::get\_accHelpTopic](../Topic/CMFCPropertyGridCtrl::get_accHelpTopic.md)|Вызывается платформой, чтобы получить полный путь к файлу `WinHelp`, связанного с указанным объектом и идентификатором соответствующей разделы в этот файл.  \(Переопределяет [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md)\).|  
|[CMFCPropertyGridCtrl::get\_accKeyboardShortcut](../Topic/CMFCPropertyGridCtrl::get_accKeyboardShortcut.md)|Вызываемый платформой для получения сочетание клавиш или клавиша доступа для указанного объекта.  \(Переопределяет [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md)\).|  
|`CMFCPropertyGridCtrl::get_accName`|Вызываемый платформой для получения имя указанного объекта.  \(Переопределяет [CWnd::get\_accName](../Topic/CWnd::get_accName.md)\).|  
|`CMFCPropertyGridCtrl::get_accRole`|Вызываемый платформой для получения сведения, которые описывают роль указанного объекта.  \(Переопределяет [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md)\).|  
|[CMFCPropertyGridCtrl::get\_accSelection](../Topic/CMFCPropertyGridCtrl::get_accSelection.md)|Вызываемый платформой для получения выбранные дочерние элементы данного объект.  \(Переопределяет [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md)\).|  
|`CMFCPropertyGridCtrl::get_accState`|Вызываемый платформой для получения текущее состояние заданного объекта.  \(Переопределяет [CWnd::get\_accState](../Topic/CWnd::get_accState.md)\).|  
|`CMFCPropertyGridCtrl::get_accValue`|Вызываемый платформой для получения значения указанного объекта.  \(Переопределяет [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md)\).|  
|[CMFCPropertyGridCtrl::GetBkColor](../Topic/CMFCPropertyGridCtrl::GetBkColor.md)|Возвращает цвет фона текущего элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetBoldFont](../Topic/CMFCPropertyGridCtrl::GetBoldFont.md)|Получает шрифт Windows, текст в текущем элементе управления сетки свойств полужирным стиле.|  
|[CMFCPropertyGridCtrl::GetCurSel](../Topic/CMFCPropertyGridCtrl::GetCurSel.md)|Получает текущее выбранное свойство.|  
|[CMFCPropertyGridCtrl::GetCustomColors](../Topic/CMFCPropertyGridCtrl::GetCustomColors.md)|Получает цвет, в настоящее время определенных для элементов управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](../Topic/CMFCPropertyGridCtrl::GetDescriptionHeight.md)|Получает высоту области описаний, расположенной в нижней части элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](../Topic/CMFCPropertyGridCtrl::GetDescriptionRows.md)|Извлекает число строк в области описание текущего управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](../Topic/CMFCPropertyGridCtrl::GetHeaderCtrl.md)|Извлекает внутренний объект [CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl%20Class.md), инфраструктура использует для отображения текущего управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](../Topic/CMFCPropertyGridCtrl::GetHeaderHeight.md)|Получает высоту заголовка элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](../Topic/CMFCPropertyGridCtrl::GetLeftColumnWidth.md)|Возвращает ширину левого столбца текущего управления сетки свойств, содержащее имя каждого свойства.|  
|[CMFCPropertyGridCtrl::GetListRect](../Topic/CMFCPropertyGridCtrl::GetListRect.md)|Получает ограничивающий прямоугольник управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetProperty](../Topic/CMFCPropertyGridCtrl::GetProperty.md)|Извлекает указатель на объект свойства, соответствующее указанному индексу элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](../Topic/CMFCPropertyGridCtrl::GetPropertyColumnWidth.md)|Извлекает текущую ширину столбца, содержащего значения свойства.|  
|[CMFCPropertyGridCtrl::GetPropertyCount](../Topic/CMFCPropertyGridCtrl::GetPropertyCount.md)|Возвращает количество свойств в элементе управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetRowHeight](../Topic/CMFCPropertyGridCtrl::GetRowHeight.md)|Получает высоту строки в элементе управления сетки свойств.|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](../Topic/CMFCPropertyGridCtrl::GetScrollBarCtrl.md)|Извлекает указатель к элементу управления полосы прокрутки в элементе управления сетки свойств.  \(Переопределяет [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md)\).|  
|[CMFCPropertyGridCtrl::GetTextColor](../Topic/CMFCPropertyGridCtrl::GetTextColor.md)|Получает цвет текста элементов свойства в текущем элементе управления сетки свойств.|  
|`CMFCPropertyGridCtrl::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCPropertyGridCtrl::HitTest](../Topic/CMFCPropertyGridCtrl::HitTest.md)|Извлекает указатель на объект свойства, соответствующий элементу управления сетки свойств, если указанная точка находится на элементе.  Этот метод также указывает область в элементе управления сетки свойств, содержащий точку.|  
|[CMFCPropertyGridCtrl::InitHeader](../Topic/CMFCPropertyGridCtrl::InitHeader.md)|Инициализирует внутренний объект [CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl%20Class.md), инфраструктура использует для отображения текущего управления сетки свойств.|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](../Topic/CMFCPropertyGridCtrl::IsAlphabeticMode.md)|Указывает, является ли элемент управления сетки свойств в алфавитном режиме.|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](../Topic/CMFCPropertyGridCtrl::IsDescriptionArea.md)|Указывает, отображается ли область описания управления сетки свойств.|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::IsGroupNameFullWidth.md)|Указывает, отображается ли каждое имя группы свойств с помощью ширину текущего управления сетки свойств.|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](../Topic/CMFCPropertyGridCtrl::IsHeaderCtrl.md)|Указывает, отображается ли элемент управления заголовка.|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::IsMarkModifiedProperties.md)|Показывает, как элемент управления сетки свойств показывает измененные свойства.|  
|[CMFCPropertyGridCtrl::IsShowDragContext](../Topic/CMFCPropertyGridCtrl::IsShowDragContext.md)|Указывает, что границы перерисовывает столбцы name и значения текущего управления сетки свойств, когда пользователь изменяет размер столбцов.|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](../Topic/CMFCPropertyGridCtrl::IsVSDotNetLook.md)|Указывает, является ли внешний вид элемента управления сетки свойств в стиле, который используется by С .NET.|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::MarkModifiedProperties.md)|Определяет способ отображения измененных свойств.|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|Используемый классом [CWinApp](../../mfc/reference/cwinapp-class.md) для трансляции сообщения окна, прежде чем они будут передается функции [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)\).|  
|[CMFCPropertyGridCtrl::RemoveAll](../Topic/CMFCPropertyGridCtrl::RemoveAll.md)|Удаляет все объекты свойства из элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](../Topic/CMFCPropertyGridCtrl::ResetOriginalValues.md)|Получает исходное значения всех свойств.|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](../Topic/CMFCPropertyGridCtrl::SetAlphabeticMode.md)|Задает или режим возвратов алфавитный.|  
|[CMFCPropertyGridCtrl::SetBoolLabels](../Topic/CMFCPropertyGridCtrl::SetBoolLabels.md)|Указывает текст логических меток.|  
|[CMFCPropertyGridCtrl::SetCurSel](../Topic/CMFCPropertyGridCtrl::SetCurSel.md)|Выберите свойство в элементе управления сетки свойств.|  
|[CMFCPropertyGridCtrl::SetCustomColors](../Topic/CMFCPropertyGridCtrl::SetCustomColors.md)|Указывает цвет для различных элементов управления сетки свойств.|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](../Topic/CMFCPropertyGridCtrl::SetDescriptionRows.md)|Указывает количество строк для отображения в разделе описания текущего управления сетки свойств.|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::SetGroupNameFullWidth.md)|Указывает, нужно ли отображать полную ширину имя категории для группы свойств в составе в текущем элементе управления сетки свойств.|  
|[CMFCPropertyGridCtrl::SetListDelimiter](../Topic/CMFCPropertyGridCtrl::SetListDelimiter.md)|Указывает символ, который будет использоваться в качестве разделителя в списке значений свойств.|  
|[CMFCPropertyGridCtrl::SetShowDragContext](../Topic/CMFCPropertyGridCtrl::SetShowDragContext.md)|Определяет границы перерисовывает ли столбцы name и значения текущего управления сетки свойств, когда пользователь изменяет размер столбцов.|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](../Topic/CMFCPropertyGridCtrl::SetVSDotNetLook.md)|Задает внешний вид элемента управления сетки свойств к стилю, используемый в VS .NET.|  
|[CMFCPropertyGridCtrl::UpdateColor](../Topic/CMFCPropertyGridCtrl::UpdateColor.md)|Устанавливает значение цвета выделенного свойства цвета.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridCtrl::AdjustLayout](../Topic/CMFCPropertyGridCtrl::AdjustLayout.md)|Перерисовывает элемент управления сетки свойств и его свойства.|  
|[CMFCPropertyGridCtrl::CompareProps](../Topic/CMFCPropertyGridCtrl::CompareProps.md)|Называемый элементом управления сетки свойств для сортировки свойств.|  
|[CMFCPropertyGridCtrl::EditItem](../Topic/CMFCPropertyGridCtrl::EditItem.md)|Вызывается инфраструктурой при запуске пользователя для изменения свойства.|  
|[CMFCPropertyGridCtrl::EndEditItem](../Topic/CMFCPropertyGridCtrl::EndEditItem.md)|Вызываемый платформой, когда пользователь останавливает изменить свойство.|  
|[CMFCPropertyGridCtrl::Init](../Topic/CMFCPropertyGridCtrl::Init.md)|Вызываемый платформой для инициализации элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::OnChangeSelection](../Topic/CMFCPropertyGridCtrl::OnChangeSelection.md)|Вызываемый платформой, если текущее выделение будет изменен.|  
|[CMFCPropertyGridCtrl::OnClickButton](../Topic/CMFCPropertyGridCtrl::OnClickButton.md)|Вызываемый платформой, если кнопка свойства будет нажата.|  
|[CMFCPropertyGridCtrl::OnDrawBorder](../Topic/CMFCPropertyGridCtrl::OnDrawBorder.md)|Вызываемый платформой для рисования границы вокруг элемента управления сетки свойств.|  
|[CMFCPropertyGridCtrl::OnDrawDescription](../Topic/CMFCPropertyGridCtrl::OnDrawDescription.md)|Вызываемый платформой для рисования область описания и отображать текст описания.|  
|[CMFCPropertyGridCtrl::OnDrawList](../Topic/CMFCPropertyGridCtrl::OnDrawList.md)|Вызываемый платформой для отображения списка свойств в элементе управления сетки свойств.|  
|[CMFCPropertyGridCtrl::OnDrawProperty](../Topic/CMFCPropertyGridCtrl::OnDrawProperty.md)|Вызываемый платформой для отображения свойства.|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](../Topic/CMFCPropertyGridCtrl::OnPropertyChanged.md)|Вызываемый платформой, когда будет изменен значение свойства.|  
|[CMFCPropertyGridCtrl::OnSelectCombo](../Topic/CMFCPropertyGridCtrl::OnSelectCombo.md)|Вызываемый платформой, когда свойство, которое содержит элемент управления " поле со списком выделен.|  
|[CMFCPropertyGridCtrl::ValidateItemData](../Topic/CMFCPropertyGridCtrl::ValidateItemData.md)|Вызываемый платформой для проверки данных свойства.|  
  
## Заметки  
 Класс `CMFCPropertyGridCtrl` элемент управления сетки свойств, которое содержит редактируемый свойства, производные от класса [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md).  Каждое свойство может представлять тип и оно может содержать подэлементов.  Элемент управления сетки свойств поддерживает resizable область внизу, может отображать описание выбранного свойства.  
  
 Для использования элемента управления сетки свойств, создайте объект `CMFCPropertyGridCtrl` и затем вызовите метод [CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md).  Используйте метод [CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md) для добавления свойства в список.  
  
## Свойства выделения  
 Вместо представления значение элемента свойства может запустить диалоговое окно, которое позволяет пользователю выбирать цвета, файл или шрифт.  
  
 В следующей таблице перечислены 4 типа свойства выделения.  
  
|Класс|Описание|  
|-----------|--------------|  
|[CMFCPropertyGridProperty Class](../../mfc/reference/cmfcpropertygridproperty-class.md)|Свойство общего назначения, используемое для определения строк, даты, Логические значения и т д|  
|[CMFCPropertyGridColorProperty Class](../Topic/CMFCPropertyGridColorProperty%20Class.md)|Свойство, которое используется для выбора значение цвета.|  
|[CMFCPropertyGridFileProperty Class](../Topic/CMFCPropertyGridFileProperty%20Class.md)|Свойство, которое используется для выбора файла.|  
|[CMFCPropertyGridFontProperty Class](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|Свойство, которое используется для выбора шрифта.|  
  
## Рисунки  
 На следующих рисунках элемент управления сетки свойств отображаются свойства в 2 способами.  На первой иллюстрации показана свойства иерархически, а второе свойства отображаются в алфавитном порядке.  
  
 ![Список свойств “PropertySheet”](../../mfc/reference/media/proplist.png "PropList")  
  
## Пример  
 В следующем примере показано, как настроить объект управления сетки свойств с помощью различных методов в классе `CMFCPropertyGridCtrl`.  Примере показано, как включить элемент управления заголовка, включает панель описания и укажите внешнего вида элемента управления сетки свойств.  В примере также показано, как задать алфавитный режим для элемента управления, посредством которого элемент управления сортирует все свойства он содержит их именем свойства, а также задать собственные цвета для различных элементов управления сетки свойств.  Данный пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#14](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#16](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls#20](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls#21](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_4.cpp)]  
[!code-cpp[NVC_MFC_NewControls#24](../../mfc/reference/codesnippet/CPP/cmfcpropertygridctrl-class_5.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## Требования  
 **заголовок:** afxpropertygridctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)