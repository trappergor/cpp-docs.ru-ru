---
title: "CMFCPropertyGridProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridProperty class"
ms.assetid: 36f3fabe-0efe-468b-8a0b-5a7956db38a2
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertyGridProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект `CMFCPropertyGridProperty` представляет элемент списка в элементе управления "Список" свойства.  
  
## Синтаксис  
  
```  
class CMFCPropertyGridProperty : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridProperty::CMFCPropertyGridProperty](../Topic/CMFCPropertyGridProperty::CMFCPropertyGridProperty.md)|Создает объект `CMFCPropertyGridProperty`.|  
|`CMFCPropertyGridProperty::~CMFCPropertyGridProperty`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridProperty::AddOption](../Topic/CMFCPropertyGridProperty::AddOption.md)|Добавляет новый элемент списка к элементу управления "Список" свойства.|  
|[CMFCPropertyGridProperty::AddSubItem](../Topic/CMFCPropertyGridProperty::AddSubItem.md)|Добавляет дочерний элемент к свойству.|  
|[CMFCPropertyGridProperty::AdjustButtonRect](../Topic/CMFCPropertyGridProperty::AdjustButtonRect.md)|Называемый родительским элементом управления "Список" свойства, чтобы указать, что изменении свойства размер ограничивающий прямоугольник внедренной кнопки.|  
|[CMFCPropertyGridProperty::AdjustInPlaceEditRect](../Topic/CMFCPropertyGridProperty::AdjustInPlaceEditRect.md)|Извлекает границы текстового поля и дополнительного элемента управления "Кнопка" прокруток, которые используются для установки значения свойства.|  
|[CMFCPropertyGridProperty::AllowEdit](../Topic/CMFCPropertyGridProperty::AllowEdit.md)|Делает свойство или редактируемые или только для чтения.|  
|[CMFCPropertyGridProperty::CreateInPlaceEdit](../Topic/CMFCPropertyGridProperty::CreateInPlaceEdit.md)|Вызываемый платформой, чтобы создать редактируемый элемент управления для свойства.|  
|[CMFCPropertyGridProperty::CreateSpinControl](../Topic/CMFCPropertyGridProperty::CreateSpinControl.md)|Вызываемый платформой, чтобы создать редактируемый элемент управления "Кнопка", "счетчик".|  
|[CMFCPropertyGridProperty::Enable](../Topic/CMFCPropertyGridProperty::Enable.md)|Позволяет включить или отключить свойство.|  
|[CMFCPropertyGridProperty::EnableSpinControl](../Topic/CMFCPropertyGridProperty::EnableSpinControl.md)|Включение или отключение элемент управления "Кнопка", "счетчик", которое используется для изменения значения свойства.|  
|[CMFCPropertyGridProperty::Expand](../Topic/CMFCPropertyGridProperty::Expand.md)|Развернуть или свернуть свойство, содержащее sub\- свойства.|  
|[CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)|Форматирует текстовое представление значения свойства.|  
|[CMFCPropertyGridProperty::GetData](../Topic/CMFCPropertyGridProperty::GetData.md)|Извлекает значение `DWORD`, сопоставлено со свойством.|  
|[CMFCPropertyGridProperty::GetDescription](../Topic/CMFCPropertyGridProperty::GetDescription.md)|Извлекает описание свойства.|  
|[CMFCPropertyGridProperty::GetExpandedSubItems](../Topic/CMFCPropertyGridProperty::GetExpandedSubItems.md)|Возвращает число развернутых sub\- элементов.|  
|[CMFCPropertyGridProperty::GetHierarchyLevel](../Topic/CMFCPropertyGridProperty::GetHierarchyLevel.md)|Извлекает нулевой\- основан индекс уровня иерархии свойств.|  
|[CMFCPropertyGridProperty::GetName](../Topic/CMFCPropertyGridProperty::GetName.md)|Извлекает имя свойства.|  
|[CMFCPropertyGridProperty::GetNameTooltip](../Topic/CMFCPropertyGridProperty::GetNameTooltip.md)|Вызываемый платформой для отображения имени свойства в подсказке.|  
|[CMFCPropertyGridProperty::GetOption](../Topic/CMFCPropertyGridProperty::GetOption.md)|Извлекает текст параметра, заданного индексом.|  
|[CMFCPropertyGridProperty::GetOptionCount](../Topic/CMFCPropertyGridProperty::GetOptionCount.md)|Извлекает число параметров, относящихся к свойству.|  
|[CMFCPropertyGridProperty::GetOriginalValue](../Topic/CMFCPropertyGridProperty::GetOriginalValue.md)|Получает начальное значение текущего свойства.|  
|[CMFCPropertyGridProperty::GetParent](../Topic/CMFCPropertyGridProperty::GetParent.md)|Извлекает указатель к родительскому свойству.|  
|[CMFCPropertyGridProperty::GetRect](../Topic/CMFCPropertyGridProperty::GetRect.md)|Получает ограничивающий прямоугольник свойства.|  
|[CMFCPropertyGridProperty::GetSubItem](../Topic/CMFCPropertyGridProperty::GetSubItem.md)|Извлекает sub\- свойство, определенное на нулевой\- индексу.|  
|[CMFCPropertyGridProperty::GetSubItemsCount](../Topic/CMFCPropertyGridProperty::GetSubItemsCount.md)|Извлекает число sub\- элементов.|  
|`CMFCPropertyGridProperty::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCPropertyGridProperty::GetValue](../Topic/CMFCPropertyGridProperty::GetValue.md)|Получает значение свойства.|  
|[CMFCPropertyGridProperty::GetValueTooltip](../Topic/CMFCPropertyGridProperty::GetValueTooltip.md)|Вызываемый платформой, для которого извлекается текстовое представление значения свойств, затем отображается во всплывающей подсказке.|  
|[CMFCPropertyGridProperty::HitTest](../Topic/CMFCPropertyGridProperty::HitTest.md)|Указывает на свойство объект, соответствующий элементу списка свойств, соответствующий точке.|  
|[CMFCPropertyGridProperty::IsAllowEdit](../Topic/CMFCPropertyGridProperty::IsAllowEdit.md)|Указывает, является ли свойство можно изменять.|  
|[CMFCPropertyGridProperty::IsEnabled](../Topic/CMFCPropertyGridProperty::IsEnabled.md)|Указывает, включено ли свойство или отключен.|  
|[CMFCPropertyGridProperty::IsExpanded](../Topic/CMFCPropertyGridProperty::IsExpanded.md)|Указывает, будет ли свойство развернуто или свернуто.|  
|[CMFCPropertyGridProperty::IsGroup](../Topic/CMFCPropertyGridProperty::IsGroup.md)|Указывает, представляет ли текущее свойство группу.|  
|[CMFCPropertyGridProperty::IsInPlaceEditing](../Topic/CMFCPropertyGridProperty::IsInPlaceEditing.md)|Указывает, является ли текущее свойство можно изменять.|  
|[CMFCPropertyGridProperty::IsModified](../Topic/CMFCPropertyGridProperty::IsModified.md)|Показывает, изменяется ли текущее свойство.|  
|[CMFCPropertyGridProperty::IsParentExpanded](../Topic/CMFCPropertyGridProperty::IsParentExpanded.md)|Указывает, является ли развернуты родительские элементы текущего свойства.|  
|[CMFCPropertyGridProperty::IsSelected](../Topic/CMFCPropertyGridProperty::IsSelected.md)|Указывает выделен, является ли текущее свойство.|  
|[CMFCPropertyGridProperty::IsVisible](../Topic/CMFCPropertyGridProperty::IsVisible.md)|Указывает, является ли текущее свойство видимым.|  
|[CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)|Вызываемый платформой, когда пользователь нажимает кнопку, которая содержится в свойстве.|  
|[CMFCPropertyGridProperty::OnClickName](../Topic/CMFCPropertyGridProperty::OnClickName.md)|Называемый родительским элементом управления Список свойств, когда пользователь щелкает поле имени свойства.|  
|[CMFCPropertyGridProperty::OnClickValue](../Topic/CMFCPropertyGridProperty::OnClickValue.md)|Называемый родительским элементом управления Список свойств, когда пользователь щелкает поле значения свойства.|  
|[CMFCPropertyGridProperty::OnCloseCombo](../Topic/CMFCPropertyGridProperty::OnCloseCombo.md)|Вызываемый платформой, если поле со списком, которое содержится в свойстве закрыто.|  
|[CMFCPropertyGridProperty::OnDblClk](../Topic/CMFCPropertyGridProperty::OnDblClk.md)|Вызываемый платформой, когда пользователь щелкает свойство типа double.|  
|[CMFCPropertyGridProperty::OnDrawButton](../Topic/CMFCPropertyGridProperty::OnDrawButton.md)|Вызываемый платформой для рисования кнопки, которая содержится в свойстве.|  
|[CMFCPropertyGridProperty::OnDrawDescription](../Topic/CMFCPropertyGridProperty::OnDrawDescription.md)|Вызываемый платформой для отображения описания свойства.|  
|[CMFCPropertyGridProperty::OnDrawExpandBox](../Topic/CMFCPropertyGridProperty::OnDrawExpandBox.md)|Вызываемый платформой для рисования управление окнами развернуть около свойства, содержащего sub\- свойства.|  
|[CMFCPropertyGridProperty::OnDrawName](../Topic/CMFCPropertyGridProperty::OnDrawName.md)|Вызываемый платформой для отображения имени свойства.|  
|[CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)|Вызываемый платформой для отображения значения свойства.|  
|[CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)|Вызываемый платформой, когда пользователь собирается изменения значения свойства.|  
|[CMFCPropertyGridProperty::OnEndEdit](../Topic/CMFCPropertyGridProperty::OnEndEdit.md)|Вызываемый платформой, когда пользователь завершил работу изменение значения свойства.|  
|[CMFCPropertyGridProperty::OnKillSelection](../Topic/CMFCPropertyGridProperty::OnKillSelection.md)||  
|[CMFCPropertyGridProperty::OnPosSizeChanged](../Topic/CMFCPropertyGridProperty::OnPosSizeChanged.md)||  
|[CMFCPropertyGridProperty::OnRClickName](../Topic/CMFCPropertyGridProperty::OnRClickName.md)|Вызываемый платформой, когда пользователь щелкает правой кнопкой мыши в области имени свойства.|  
|[CMFCPropertyGridProperty::OnRClickValue](../Topic/CMFCPropertyGridProperty::OnRClickValue.md)|Вызываемый платформой, когда пользователь щелкает правой кнопкой мыши в области значения свойства.|  
|[CMFCPropertyGridProperty::OnSelectCombo](../Topic/CMFCPropertyGridProperty::OnSelectCombo.md)|Вызываемый платформой, когда пользователь выбирает элемент из редактируемые поля со списком.|  
|[CMFCPropertyGridProperty::OnSetCursor](../Topic/CMFCPropertyGridProperty::OnSetCursor.md)|Вызываемый платформой, когда указатель мыши перемещается в элемент свойства.|  
|[CMFCPropertyGridProperty::OnSetSelection](../Topic/CMFCPropertyGridProperty::OnSetSelection.md)||  
|[CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)|Вызываемый платформой, когда значение редактируемых свойств изменится.|  
|[CMFCPropertyGridProperty::PushChar](../Topic/CMFCPropertyGridProperty::PushChar.md)|Вызванный из элемента управления "Список" свойства, если свойство выделен и пользователя вставляет новый символ.|  
|[CMFCPropertyGridProperty::Redraw](../Topic/CMFCPropertyGridProperty::Redraw.md)|Перерисовывает свойство.|  
|[CMFCPropertyGridProperty::RemoveAllOptions](../Topic/CMFCPropertyGridProperty::RemoveAllOptions.md)|Удаляет все параметры из свойства \(элементы\).|  
|[CMFCPropertyGridProperty::RemoveSubItem](../Topic/CMFCPropertyGridProperty::RemoveSubItem.md)|Удаляет указанный элемент sub\-.|  
|[CMFCPropertyGridProperty::ResetOriginalValue](../Topic/CMFCPropertyGridProperty::ResetOriginalValue.md)|Возвращает исходное значение редактируемого свойства.|  
|[CMFCPropertyGridProperty::SetData](../Topic/CMFCPropertyGridProperty::SetData.md)|Связывает значение `DWORD` со свойством.|  
|[CMFCPropertyGridProperty::SetDescription](../Topic/CMFCPropertyGridProperty::SetDescription.md)|Задает текст, который описывает текущее свойство.|  
|[CMFCPropertyGridProperty::SetName](../Topic/CMFCPropertyGridProperty::SetName.md)|Задает имя свойства.|  
|[CMFCPropertyGridProperty::SetOriginalValue](../Topic/CMFCPropertyGridProperty::SetOriginalValue.md)|Задает исходной величине редактируемого свойства.|  
|[CMFCPropertyGridProperty::SetValue](../Topic/CMFCPropertyGridProperty::SetValue.md)|Задает значение свойства в сетке свойств.|  
|[CMFCPropertyGridProperty::Show](../Topic/CMFCPropertyGridProperty::Show.md)|Свойство отображать или скрывать.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridProperty::CreateCombo](../Topic/CMFCPropertyGridProperty::CreateCombo.md)|Вызываемый платформой, чтобы добавить поле со списком к свойству.|  
|[CMFCPropertyGridProperty::HasButton](../Topic/CMFCPropertyGridProperty::HasButton.md)|Указывает, содержит ли свойство кнопку.|  
|[CMFCPropertyGridProperty::Init](../Topic/CMFCPropertyGridProperty::Init.md)|Вызываемый платформой для инициализации объекта свойства.|  
|[CMFCPropertyGridProperty::IsSubItem](../Topic/CMFCPropertyGridProperty::IsSubItem.md)|Показывает, является ли указанное свойство sub\- элемент текущего свойства.|  
|[CMFCPropertyGridProperty::IsValueChanged](../Topic/CMFCPropertyGridProperty::IsValueChanged.md)|Указывает, было ли изменено значение текущего свойства.|  
|[CMFCPropertyGridProperty::OnCtlColor](../Topic/CMFCPropertyGridProperty::OnCtlColor.md)|Вызываемый платформой, когда он должен получать кисть для заполнения цвет фона свойства.|  
|[CMFCPropertyGridProperty::OnDestroyWindow](../Topic/CMFCPropertyGridProperty::OnDestroyWindow.md)|Вызывается инфраструктурой при уничтожении или завершении редактирования свойства.|  
|[CMFCPropertyGridProperty::OnKillFocus](../Topic/CMFCPropertyGridProperty::OnKillFocus.md)|Вызываемый платформой, когда свойство теряет фокус ввода.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCPropertyGridProperty::m\_strFormatDouble](../Topic/CMFCPropertyGridProperty::m_strFormatDouble.md)|Строка формата для значения типа double.|  
|[CMFCPropertyGridProperty::m\_strFormatFloat](../Topic/CMFCPropertyGridProperty::m_strFormatFloat.md)|Строка форматирования для значений с плавающей запятой типа.|  
|[CMFCPropertyGridProperty::m\_strFormatLong](../Topic/CMFCPropertyGridProperty::m_strFormatLong.md)|Строка форматирования для значений типа long.|  
|[CMFCPropertyGridProperty::m\_strFormatShort](../Topic/CMFCPropertyGridProperty::m_strFormatShort.md)|Строка форматирования для значений типа короткого.|  
  
## Заметки  
 Используйте объект `CMFCPropertyGridProperty` для представления свойства, затем добавляется к элементу управления "Список" свойства.  Дополнительные сведения см. в разделе [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
 Объект свойства может представлять типы данных, такие как строки, даты и логическое или целочисленные значения.  Он может содержать свойства дочерних элементов или он может содержать элемент управления в поле со списком или элемент управления "Кнопка".  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCPropertyGridProperty`.  В примере также показано, как использовать различные методы класса `CMFCPropertyGridProperty` чтобы добавить параметр, чтобы добавить sub\- элемент, чтобы включить свойство и отобразить свойство.  Данный пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#27](../../mfc/reference/codesnippet/CPP/cmfcpropertygridproperty-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
## Требования  
 **заголовок:** afxpropertygridctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md)