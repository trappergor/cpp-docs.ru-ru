---
title: "CHotKeyCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl class"
  - "hot key controls"
  - "Windows common controls [C++], CHotKeyCtrl"
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CHotKeyCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления горячей клавиш Windows общего.  
  
## Синтаксис  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHotKeyCtrl::CHotKeyCtrl](../Topic/CHotKeyCtrl::CHotKeyCtrl.md)|Создает объект `CHotKeyCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHotKeyCtrl::Create](../Topic/CHotKeyCtrl::Create.md)|Создает элемент управления горячей клавиш и вложение его к объекту `CHotKeyCtrl`.|  
|[CHotKeyCtrl::CreateEx](../Topic/CHotKeyCtrl::CreateEx.md)|Создается элемент управления клавиши работать с указанными стилей расширенными Windows и вложение его к объекту `CHotKeyCtrl`.|  
|[CHotKeyCtrl::GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)|Возвращает флаги виртуального кода клавиши и модификатора горячей клавиш из элемента управления горячей клавиш.|  
|[CHotKeyCtrl::GetHotKeyName](../Topic/CHotKeyCtrl::GetHotKeyName.md)|Возвращает имя ключа в локальном символа \- наборе, присвоенном на клавише работать.|  
|[CHotKeyCtrl::GetKeyName](../Topic/CHotKeyCtrl::GetKeyName.md)|Возвращает имя ключа в локальном символа \- наборе, присвоенном к указанному виртуальному коду клавиши.|  
|[CHotKeyCtrl::SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)|Устанавливает сочетания клавиш для управления активных активных клавиш.|  
|[CHotKeyCtrl::SetRules](../Topic/CHotKeyCtrl::SetRules.md)|Указывает недопустимые комбинации модификатора по умолчанию и сочетания клавиш для управления горячей.|  
  
## Заметки  
 Элемент управления клавиши "горячей" окно, которое позволяет пользователю создать горячая стрелка.  "Горячая клавиша" сочетание клавиш, которое пользователь может нажать выполнить действие быстро.  \(Например, пользователь может создать горячая клавиша, активировать заданного окна и приводит ее в верхней части заказа, Z\). Управление горячей клавиши указывает варианты пользователя и гарантирует, что пользователь выбирает допустимое сочетание клавиш.  
  
 Этот элемент управления \(и, следовательно, класс `CHotKeyCtrl` \) доступны только для программ, выполняемых в рамках \/98 Windows версии 3.51 и Windows NT 95 и более поздних версий.  
  
 Когда пользователь выбрал сочетание клавиш, приложение может получить сочетание заданного ключа из элемента управления и использовать сообщение **WM\_SETHOTKEY** для настройки горячую клавиши в системе.  При нажатии пользователем клавиши горячая таким образом, из любой части системы, окно, указанной в сообщении **WM\_SETHOTKEY** получает сообщение `WM_SYSCOMMAND` указав **SC\_HOTKEY**.  Это сообщение активировать окно, которое возвращает его.  Горячая клавиша остается допустимым до выхода из приложения, которое вызвало **WM\_SETHOTKEY**.  
  
 Этот механизм отличается от поддержка горячей клавиши которая зависит от сообщения **WM\_HOTKEY** и функции Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) и [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327).  
  
 Дополнительные сведения об использовании `CHotKeyCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CHotKeyCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)