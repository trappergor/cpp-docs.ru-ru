---
title: "CCheckListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCheckListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckListBox class"
  - "checklist boxes"
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CCheckListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность окно контрольного списка Windows.  
  
## Синтаксис  
  
```  
  
class CCheckListBox : public CListBox  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCheckListBox::CCheckListBox](../Topic/CCheckListBox::CCheckListBox.md)|Создает объект `CCheckListBox`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCheckListBox::Create](../Topic/CCheckListBox::Create.md)|Создает окно контрольного списка Windows и вложение его к объекту `CCheckListBox`.|  
|[CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md)|Вызываемый платформой, когда визуальный аспект списка рисования владельцем изменяется.|  
|[CCheckListBox::Enable](../Topic/CCheckListBox::Enable.md)|Включение или отключение элемент окно контрольного списка.|  
|[CCheckListBox::GetCheck](../Topic/CCheckListBox::GetCheck.md)|Получает состояние флажка элемента.|  
|[CCheckListBox::GetCheckStyle](../Topic/CCheckListBox::GetCheckStyle.md)|Возвращает стиль флажков элемента управления.|  
|[CCheckListBox::IsEnabled](../Topic/CCheckListBox::IsEnabled.md)|Указывает, включен ли элемент.|  
|[CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)|Вызываемый платформой, когда будет создать список с учетом рисования владельцем.|  
|[CCheckListBox::OnGetCheckPosition](../Topic/CCheckListBox::OnGetCheckPosition.md)|Вызываемый платформой для получения положения флажка элемента.|  
|[CCheckListBox::SetCheck](../Topic/CCheckListBox::SetCheck.md)|Устанавливает состояние флажка элемента.|  
|[CCheckListBox::SetCheckStyle](../Topic/CCheckListBox::SetCheckStyle.md)|Задает стиль флажков элемента управления.|  
  
## Заметки  
 "Окно контрольного списка" отображает список элементов, таких как имена файлов.  Каждый элемент списка есть флажок рядом с ним, что пользователь может проверять или удалить.  
  
 `CCheckListBox` только для определяемых пользователем элементов управления, поскольку список содержит более текстовые строки.  В самом простом окно контрольного списка содержит текстовые строки и флажков, но нет необходимости иметь текста.  Например, можно создать список с небольшими растровых изображений флажок рядом с каждым элементом.  
  
 Чтобы создать собственное окно контрольного списка, необходимо создать собственный класс, производный от `CCheckListBox`.  Чтобы создать собственный класс, разработайте конструктор для производного класса, а затем вызовите **Создать**.  
  
 Если нужно обрабатывать сообщения уведомлений Windows, отправленные списком с родительским элементом \(обычно класс, производный от [CDialog](../../mfc/reference/cdialog-class.md)\), то добавление функции\-члена записи и обработчика сообщений сообщение\- сопоставления в родительский класс для каждого сообщения.  
  
 Каждая запись сообщение\-сопоставления принимает следующую форму:  
  
 Уведомление **\(**`id`**ON\_**, `memberFxn`**\)**  
  
 где `id` задает идентификатор дочернего окна элемента управления, отправляющее уведомление и `memberFxn` имя родительского функции\-члена был написан для обработки уведомления.  
  
 Родительский прототип функции следующим образом:  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 Только одна запись сообщение\- сопоставления, относящиеся именно к **CCheckListBox** \(но см. также записи сообщение\- сопоставления для [CListBox](../Topic/CListBox%20Class.md)\):  
  
-   **ON\_CLBN\_CHKCHANGE** Пользователя изменилось состояние флажка элемента.  
  
 Если окно контрольного списка по умолчанию окно контрольного списка \(список строк с заданным значением по умолчанию\- размер флажками слева от каждого\), можно использовать значение по умолчанию [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) для рисования окно контрольного списка.  В противном случае необходимо переопределить функцию [CListBox::CompareItem](../Topic/CListBox::CompareItem.md) и функции [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) и [CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md).  
  
 Можно создать окно контрольного списка или из шаблона диалогового окна или непосредственно в коде.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListBox](../Topic/CListBox%20Class.md)  
  
 `CCheckListBox`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Образец TSTCON MFC](../../top/visual-cpp-samples.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)