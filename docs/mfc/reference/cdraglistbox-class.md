---
title: "CDragListBox Class | Microsoft Docs"
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
  - "CDragListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDragListBox class"
  - "drag list box [C++]"
  - "dragging list items"
  - "списки"
  - "Windows [C++], списки"
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDragListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В дополнение к предоставлению возможностей списка Windows, класс `CDragListBox` позволяет пользователю к элементам списка move, как имена файлов в списке.  
  
## Синтаксис  
  
```  
class CDragListBox : public CListBox  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDragListBox::CDragListBox](../Topic/CDragListBox::CDragListBox.md)|Создает объект `CDragListBox`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDragListBox::BeginDrag](../Topic/CDragListBox::BeginDrag.md)|Вызывается инфраструктурой при запуске операции перетаскивания.|  
|[CDragListBox::CancelDrag](../Topic/CDragListBox::CancelDrag.md)|Вызываемый платформой, когда операция перетаскивания будет отменена.|  
|[CDragListBox::Dragging](../Topic/CDragListBox::Dragging.md)|Вызывается средой во время операции перетаскивания.|  
|[CDragListBox::DrawInsert](../Topic/CDragListBox::DrawInsert.md)|Рисует руководство вставки списка перетаскивания.|  
|[CDragListBox::Dropped](../Topic/CDragListBox::Dropped.md)|Вызываемый средой после того, как элемент будет удален.|  
|[CDragListBox::ItemFromPt](../Topic/CDragListBox::ItemFromPt.md)|Возвращает координаты перетаскиваемый элемент.|  
  
## Заметки  
 Списки с этой возможностью позволяют пользователям сортировать элементы в списке в какой\-либо образ не является наиболее полезным.  По умолчанию список перемещает элемент в новое место в списке.  Однако объекты `CDragListBox` можно настраивать для копирования элементов, а не перемещать их.  
  
 Элемент управления списка, связанный с классом `CDragListBox` не должно иметь **LBS\_SORT** или стиль **LBS\_MULTIPLESELECT**.  Описание стилей список см. в разделе [Стили списков](../../mfc/reference/list-box-styles.md).  
  
 Для использования списка перетаскивания в диалоговом окне приложения, добавьте элемент управления списка к конкретному шаблону диалогового окна с помощью редактора диалоговых окон и затем присвойте переменной члена \(категории `Control` и переменной типа `CDragListBox`\), соответствующий элементу управления списка в шаблоне диалогового окна.  
  
 Дополнительные сведения о присвоить элементы управления к переменным члена см. в разделе [Ярлык, определение переменных\-членов для элементов управления диалогового окна](../../mfc/defining-member-variables-for-dialog-controls.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListBox](../Topic/CListBox%20Class.md)  
  
 `CDragListBox`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Образец TSTCON MFC](../../top/visual-cpp-samples.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)