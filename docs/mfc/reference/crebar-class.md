---
title: "CReBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar class"
  - "Internet Explorer 4.0 common controls"
  - "rebar controls, control bar"
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Панель элементов управления, предоставляющий структуру, сохраняемости, а также сведения о состоянии элементов управления " Главная панель.  
  
## Синтаксис  
  
```  
  
class CReBar : public CControlBar  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CReBar::AddBar](../Topic/CReBar::AddBar.md)|Добавляет диапазон на главной панели.|  
|[CReBar::Create](../Topic/CReBar::Create.md)|Создает элемент управления "Главная панель" и вложение его к объекту `CReBar`.|  
|[CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md)|Обеспечивает прямой доступ к общему элементу управления.|  
  
## Заметки  
 Объект главной панели может содержать множество дочерних окон, обычно другие элементы управления, включая поля ввода, панели инструментов и списки.  Объект главной панели можно отобразить его дочерние окна с указанным растровым изображением.  Приложение может автоматически размер главная панель или пользователь мог вручную размер главная панель с щелкните и перетащите его панель отслеживания.  
  
 ![Пример меню RebarMenu](../../mfc/reference/media/vc4sc61.png "vc4SC61")  
  
## Элемент управления " Главная панель  
 Объект главной панели ведет себя подобно объекту панели инструментов.  "Главная панель" использует механизм щелчок\-и\- перетаскивания размер его диапазона.  Элемент управления "Главная панель" может содержать один или несколько полосы, каждая полоса, имеющие любое сочетание панель отслеживания, растровое изображение, текстовая подпись и дочернее окно.  Однако полосы не могут содержать более чем одно дочернее окно.  
  
 **CReBar** использует класс [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) для предоставления его реализации.  Можно получить доступ к элементу управления "Главная панель" с помощью [GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) воспользоваться преимуществами параметры настройки элемента управления.  Дополнительные сведения об элементах управления "Главная панель" см. в разделе `CReBarCtrl`.  Дополнительные сведения об использовании элементов управления "Главная панель" см. в разделе [Использование CReBarCtrl](../Topic/Using%20CReBarCtrl.md).  
  
> [!CAUTION]
>  Объекты главной панели и элемента управления "Главная панель" не поддерживает закрепление панели элементов управления MFC.  Если **CRebar::EnableDocking** вызываются, приложение утвердит.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [Образец MFCIE MFC](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)