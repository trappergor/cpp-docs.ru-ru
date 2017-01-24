---
title: "CButton Class | Microsoft Docs"
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
  - "CButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "button control [MFC]"
  - "button objects (CButton)"
  - "CButton class"
  - "флажки, button controls"
  - "checkbox buttons"
  - "pushbuttons"
  - "переключатели, CButton class"
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность элемент управления "Кнопка" Windows.  
  
## Синтаксис  
  
```  
class CButton : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CButton::CButton](../Topic/CButton::CButton.md)|Создает объект `CButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CButton::Create](../Topic/CButton::Create.md)|Создает элемент управления "Кнопка" Windows и вложение его к объекту `CButton`.|  
|[CButton::DrawItem](../Topic/CButton::DrawItem.md)|Переопределение для рисования определяемый пользователем объект `CButton`.|  
|[CButton::GetBitmap](../Topic/CButton::GetBitmap.md)|Извлекает маркер растрового изображения ранее установленного с [SetBitmap](../Topic/CButton::SetBitmap.md).|  
|[CButton::GetButtonStyle](../Topic/CButton::GetButtonStyle.md)|Извлекает сведения о стиле элемента управления "Кнопка".|  
|[CButton::GetCheck](../Topic/CButton::GetCheck.md)|Извлекает состояние проверки элемента управления "Кнопка".|  
|[CButton::GetCursor](../Topic/CButton::GetCursor.md)|Извлекает маркер образа курсора ранее установленного с [SetCursor](../Topic/CButton::SetCursor.md).|  
|[CButton::GetIcon](../Topic/CButton::GetIcon.md)|Получает дескриптор значка ранее установленного с [SetIcon](../Topic/CButton::SetIcon.md).|  
|[CButton::GetIdealSize](../Topic/CButton::GetIdealSize.md)|Возвращает оптимальный размер элемента управления "Кнопка".|  
|[CButton::GetImageList](../Topic/CButton::GetImageList.md)|Извлекает список образа элемент управления "Кнопка".|  
|[CButton::GetNote](../Topic/CButton::GetNote.md)|Получает компонент заметки текущего управления command link.|  
|[CButton::GetNoteLength](../Topic/CButton::GetNoteLength.md)|Извлекает длина текста заметки для текущего элемента управления command link.|  
|[CButton::GetSplitGlyph](../Topic/CButton::GetSplitGlyph.md)|Извлекает глиф, связанный с текущим элементом управления разворачивающейся кнопки.|  
|[CButton::GetSplitImageList](../Topic/CButton::GetSplitImageList.md)|Извлекает список завершения образа для текущего элемента управления разворачивающейся кнопки.|  
|[CButton::GetSplitInfo](../Topic/CButton::GetSplitInfo.md)|Получает сведения, указывающее текущий элемент управления разворачивающейся кнопки.|  
|[CButton::GetSplitSize](../Topic/CButton::GetSplitSize.md)|Получает ограничивающий прямоугольник компонента раскрывающегося списка для текущего элемента управления разворачивающейся кнопки.|  
|[CButton::GetSplitStyle](../Topic/CButton::GetSplitStyle.md)|Получает стили разворачивающаяся кнопка, указывающие текущее управление разворачивающейся кнопки.|  
|[CButton::GetState](../Topic/CButton::GetState.md)|Извлекает состояние проверки, состояние выделения и состояние фокуса элемент управления "Кнопка".|  
|[CButton::GetTextMargin](../Topic/CButton::GetTextMargin.md)|Извлекает поля текст элемента управления "Кнопка".|  
|[CButton::SetBitmap](../Topic/CButton::SetBitmap.md)|Задает растровое изображение, отображаемый на кнопке.|  
|[CButton::SetButtonStyle](../Topic/CButton::SetButtonStyle.md)|Изменяет стиль кнопки.|  
|[CButton::SetCheck](../Topic/CButton::SetCheck.md)|Задает состояние проверки элемента управления "Кнопка".|  
|[CButton::SetCursor](../Topic/CButton::SetCursor.md)|Определяет способ курсора, отображаемый на кнопке.|  
|[CButton::SetDropDownState](../Topic/CButton::SetDropDownState.md)|Устанавливает состояние текущего управления раскрывающемся списке разворачивающейся кнопки.|  
|[CButton::SetIcon](../Topic/CButton::SetIcon.md)|Задает значок, отображаемый на кнопке.|  
|[CButton::SetImageList](../Topic/CButton::SetImageList.md)|Задает список образа элемент управления "Кнопка".|  
|[CButton::SetNote](../Topic/CButton::SetNote.md)|Задает заметку на текущем элементе управления command link.|  
|[CButton::SetSplitGlyph](../Topic/CButton::SetSplitGlyph.md)|Связывает указанный глиф с текущим элементом управления разворачивающейся кнопки.|  
|[CButton::SetSplitImageList](../Topic/CButton::SetSplitImageList.md)|Связывает список образа с текущим элементом управления разворачивающейся кнопки.|  
|[CButton::SetSplitInfo](../Topic/CButton::SetSplitInfo.md)|Определяет сведения, указывающее текущий элемент управления разворачивающейся кнопки.|  
|[CButton::SetSplitSize](../Topic/CButton::SetSplitSize.md)|Задает прямоугольник компонента раскрывающегося списка для текущего элемента управления разворачивающейся кнопки.|  
|[CButton::SetSplitStyle](../Topic/CButton::SetSplitStyle.md)|Задает стиль текущего управления разворачивающейся кнопки.|  
|[CButton::SetState](../Topic/CButton::SetState.md)|Устанавливает выделение состояние элемента управления "Кнопка".|  
|[CButton::SetTextMargin](../Topic/CButton::SetTextMargin.md)|Устанавливает поля текст элемента управления "Кнопка".|  
  
## Заметки  
 Элемент управления "Кнопка" маленькое, прямоугольное дочернее окно, которое можно щелкнуть и.  Кнопки можно использовать по отдельности или в группы и могут быть обозначены или появиться без текста.  Кнопка обычно изменяет внешний вид, когда пользователь щелкает его.  
  
 Стандартные кнопки флажок, переключатель и кнопкой.  Объект `CButton` может стать любой из них, в соответствии с [стиль кнопки](../../mfc/reference/button-styles.md) указанный в своей инициализации функцией\-членом [Создание](../Topic/CButton::Create.md).  
  
 Кроме того, класс [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), унаследованный от создания `CButton` поддерживает элемент управления "Кнопка" обозначенных с образами растрового изображения, а не текста.  `CBitmapButton` может иметь отдельные растровые изображения для кнопки вверх, вниз, с фокусом ввода и запрещенных состояний.  
  
 Можно создать элемент управления "Кнопка" или из шаблона диалогового окна или непосредственно в коде.  В обоих случаях сначала вызвать конструктор `CButton` для создания объекта `CButton`; затем вызовите функцию\-член **Создать** для создания элемента управления "Кнопка" Windows и вложить его к объекту `CButton`.  
  
 Конструкция может быть одношаговым процессом в классе, производном от `CButton`.  Создание конструктора производного класса и вызовите **Создать** из конструктора.  
  
 Если нужно обрабатывать сообщения уведомлений Windows, отправленные элемент управления "Кнопка" с родительским элементом \(обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)\), то добавление функции\-члена записи и обработчика сообщений сообщение\- сопоставления в родительский класс для каждого сообщения.  
  
 Каждая запись сообщение\-сопоставления принимает следующую форму:  
  
 Уведомление **\(**`id`**ON\_**, `memberFxn`**\)**  
  
 где `id` задает идентификатор дочернего окна элемента управления, отправляющее уведомление и `memberFxn` имя родительского функции\-члена был написан для обработки уведомления.  
  
 Родительский прототип функции следующим образом:  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Потенциальных записей сообщение\- сопоставления следующим образом:  
  
|Запись сопоставления|Отправленный к родительскому элементу, когда…|  
|--------------------------|---------------------------------------------------|  
|**ON\_BN\_CLICKED**|Пользователь нажимает кнопку.|  
|**ON\_BN\_DOUBLECLICKED**|Пользователь дважды щелкает кнопку.|  
  
 При создании объекта `CButton` из ресурса диалогового окна, то объект `CButton` автоматически уничтожается, когда пользователь закрывает диалоговое окно.  
  
 При создании объекта `CButton` в окне, можно удалить его.  При создании объекта `CButton` в куче с помощью функции **новый**, необходимо вызвать метод **удалить** в объекте, чтобы удалить его, когда пользователь закрывает элемент управления "Кнопка" Windows.  При создании объекта `CButton` в стеке или он внедрен в родительском объекте диалогового окна, он удален автоматически.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CButton`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../Topic/CEdit%20Class.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../Topic/CStatic%20Class.md)   
 [CBitmapButton Class](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)