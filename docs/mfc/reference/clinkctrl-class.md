---
title: "CLinkCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinkCtrl class"
  - "элементы управления [MFC], связи"
  - "ссылки [C++], link control"
  - "SysLink control"
  - "веб-страницы, link control"
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CLinkCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления Windows общего SysLink.  
  
## Синтаксис  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinkCtrl::CLinkCtrl](../Topic/CLinkCtrl::CLinkCtrl.md)|Создает объект `CLinkCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLinkCtrl::Create](../Topic/CLinkCtrl::Create.md)|Создает элемент управления ссылки и вложение его к объекту `CLinkCtrl`.|  
|[CLinkCtrl::CreateEx](../Topic/CLinkCtrl::CreateEx.md)|Создает элемент управления связи с расширенных стилей и вложение его к объекту `CLinkCtrl`.|  
|[CLinkCtrl::GetIdealHeight](../Topic/CLinkCtrl::GetIdealHeight.md)|Извлекает идеальная высота элемента управления ссылками.|  
|[CLinkCtrl::GetIdealSize](../Topic/CLinkCtrl::GetIdealSize.md)|Вычисляет желаемую высоту текста ссылки для текущего элемента управления, в зависимости от указанной ширины ссылки.|  
|[CLinkCtrl::GetItem](../Topic/CLinkCtrl::GetItem.md)|Извлекает состояние и атрибуты элемента управления ссылками.|  
|[CLinkCtrl::GetItemID](../Topic/CLinkCtrl::GetItemID.md)|Извлекает идентификатор элемента управления ссылками.|  
|[CLinkCtrl::GetItemState](../Topic/CLinkCtrl::GetItemState.md)|Извлекает состояние элемента управления ссылками.|  
|[CLinkCtrl::GetItemUrl](../Topic/CLinkCtrl::GetItemUrl.md)|Получает URL\-адрес, представленное элементом управления связи.|  
|[CLinkCtrl::HitTest](../Topic/CLinkCtrl::HitTest.md)|Указывает, щелкнул ли пользователь указанная ссылка.|  
|[CLinkCtrl::SetItem](../Topic/CLinkCtrl::SetItem.md)|Устанавливает для состояния и атрибуты элемента управления ссылками.|  
|[CLinkCtrl::SetItemID](../Topic/CLinkCtrl::SetItemID.md)|Задает идентификатор элемента управления ссылками.|  
|[CLinkCtrl::SetItemState](../Topic/CLinkCtrl::SetItemState.md)|Устанавливает состояние элемента управления ссылками.|  
|[CLinkCtrl::SetItemUrl](../Topic/CLinkCtrl::SetItemUrl.md)|Задает URL\-адрес, представленный элементом управления связи.|  
  
## Заметки  
 Элемент управления "ссылки" предоставляет удобный способ внедрение связи гипертекста в окне.  Фактический элемент управления является окном, текст выполняет визуализацию признаком \- вверх и запускает соответствующую приложения, когда пользователь щелкает вложенной связи.  Несколько связей поддерживаются в пределах одного элемента управления и могут быть получить доступ на нулевой\- индексу.  
  
 Этот элемент управления \(и, следовательно, класс `CLinkCtrl` \) доступны только для программ, выполняемых в рамках Windows XP или более поздних версиях.  
  
 Дополнительные сведения см. в разделе [Элемент управления SysLink](http://msdn.microsoft.com/library/windows/desktop/bb760706) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CLinkCtrl`  
  
## Требования  
 **Header:** afxcmn.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)