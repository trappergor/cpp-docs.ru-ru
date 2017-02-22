---
title: "CPagerCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPagerCtrl class"
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPagerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CPagerCtrl` программу\-оболочку создает элемент управления страничного навигатора Windows, который можно прокручивать представление, содержащихся в окне, не адаптирует, содержащий окно.  
  
## Синтаксис  
  
```  
class CPagerCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPagerCtrl::CPagerCtrl](../Topic/CPagerCtrl::CPagerCtrl.md)|Создает объект `CPagerCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPagerCtrl::Create](../Topic/CPagerCtrl::Create.md)|Создает элемент управления страничного навигатора с указанными стилями и вложение его к текущему объекту `CPagerCtrl`.|  
|[CPagerCtrl::CreateEx](../Topic/CPagerCtrl::CreateEx.md)|Создает элемент управления страничного навигатора с указанными расширенных стилей и вложение его к текущему объекту `CPagerCtrl`.|  
|[CPagerCtrl::ForwardMouse](../Topic/CPagerCtrl::ForwardMouse.md)|Включение или отключение переадресованы сообщения [WM\_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) в окно, которое содержится в текущем элементе управления страничного навигатора.|  
|[CPagerCtrl::GetBkColor](../Topic/CPagerCtrl::GetBkColor.md)|Возвращает цвет фона текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetBorder](../Topic/CPagerCtrl::GetBorder.md)|Получает размер границы текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetButtonSize](../Topic/CPagerCtrl::GetButtonSize.md)|Получает размер кнопки текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetButtonState](../Topic/CPagerCtrl::GetButtonState.md)|Извлекает состояние указанной кнопки в текущем элементе управления страничного навигатора.|  
|[CPagerCtrl::GetDropTarget](../Topic/CPagerCtrl::GetDropTarget.md)|Извлекает интерфейс [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) для текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::GetScrollPos](../Topic/CPagerCtrl::GetScrollPos.md)|Извлекает позицию прокрутки текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::IsButtonDepressed](../Topic/CPagerCtrl::IsButtonDepressed.md)|Указывает, является ли указанная кнопка текущего элемента управления страничного навигатора в состоянии `pressed`.|  
|[CPagerCtrl::IsButtonGrayed](../Topic/CPagerCtrl::IsButtonGrayed.md)|Указывает, является ли указанная кнопка текущего элемента управления страничного навигатора в состоянии `grayed`.|  
|[CPagerCtrl::IsButtonHot](../Topic/CPagerCtrl::IsButtonHot.md)|Указывает, является ли указанная кнопка текущего элемента управления страничного навигатора в состоянии `hot`.|  
|[CPagerCtrl::IsButtonInvisible](../Topic/CPagerCtrl::IsButtonInvisible.md)|Указывает, является ли указанная кнопка текущего элемента управления страничного навигатора в состоянии `invisible`.|  
|[CPagerCtrl::IsButtonNormal](../Topic/CPagerCtrl::IsButtonNormal.md)|Указывает, является ли указанная кнопка текущего элемента управления страничного навигатора в состоянии `normal`.|  
|[CPagerCtrl::RecalcSize](../Topic/CPagerCtrl::RecalcSize.md)|Вынуждает текущий элемент управления страничного навигатора пересчитаны размер, содержащихся в окне.|  
|[CPagerCtrl::SetBkColor](../Topic/CPagerCtrl::SetBkColor.md)|Устанавливает цвет фона текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetBorder](../Topic/CPagerCtrl::SetBorder.md)|Задает размер границы текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetButtonSize](../Topic/CPagerCtrl::SetButtonSize.md)|Задает размер кнопки текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetChild](../Topic/CPagerCtrl::SetChild.md)|Устанавливает, которые содержат окно для текущего элемента управления страничного навигатора.|  
|[CPagerCtrl::SetScrollPos](../Topic/CPagerCtrl::SetScrollPos.md)|Задает позицию прокрутки текущего элемента управления страничного навигатора.|  
  
## Заметки  
 Элемент управления страничного навигатора окно, содержащее другое окно, линейное и больше, содержащий окно, и позволяет прокручивать окно, содержащихся в представление.  Элемент управления страничного навигатора отображается 2 кнопки прокрутки, которая автоматически исчезают, когда содержащийся в окно прокручено его самый далекий объем и снова отображаются, в противном случае.  Можно создать элемент управления страничного навигатора, который выполняет прокрутку или горизонтально или вертикально.  
  
 Например, если приложение содержит панель инструментов, которая не является достаточно широкой отобразить все его элементов можно присвоить панель инструментов к элементу управления страничного навигатора и пользователи смогут прокручивать панели инструментов в левого или правого для доступа ко всем элементам.  Microsoft Internet Explorer версии 4.0 commctrl.dll \(версия 4.71\) вставляет элемент управления страничного навигатора.  
  
 Класс `CPagerCtrl` является производным от класса [CWnd](../Topic/CWnd%20Class.md).  Дополнительные сведения и примеры элемента управления страничного навигатора см. в разделе [элементы управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760855).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CPagerCtrl`  
  
## Требования  
 **заголовок:** afxcmn.h  
  
## См. также  
 [CPagerCtrl Class](../../mfc/reference/cpagerctrl-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [элементы управления страничного навигатора](http://msdn.microsoft.com/library/windows/desktop/bb760855)