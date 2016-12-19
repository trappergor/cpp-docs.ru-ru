---
title: "CStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar class"
  - "indicators"
  - "indicators, status bar"
  - "строки состояния"
  - "status indicators"
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Панель элементов управления со строкой текста вывела или индикаторы панели "данные".  
  
## Синтаксис  
  
```  
class CStatusBar : public CControlBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStatusBar::CStatusBar](../Topic/CStatusBar::CStatusBar.md)|Создает объект `CStatusBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStatusBar::CommandToIndex](../Topic/CStatusBar::CommandToIndex.md)|Возвращает индекс заданного идентификатора индикатора|  
|[CStatusBar::Create](../Topic/CStatusBar::Create.md)|Создает строку состояния к объекту вложение она `CStatusBar` и устанавливает исходную высоту шрифта и панели.|  
|[CStatusBar::CreateEx](../Topic/CStatusBar::CreateEx.md)|Создает объект `CStatusBar` с помощью дополнительных стилей для внедренного объекта `CStatusBarCtrl`.|  
|[CStatusBar::DrawItem](../Topic/CStatusBar::DrawItem.md)|Вызываемый, когда визуальный аспект элемента управления "Строка состояния" рисования владельцем изменяется.|  
|[CStatusBar::GetItemID](../Topic/CStatusBar::GetItemID.md)|Получает идентификатор индикатора для заданного индекса.|  
|[CStatusBar::GetItemRect](../Topic/CStatusBar::GetItemRect.md)|Возвращает прямоугольник для заданного индекса.|  
|[CStatusBar::GetPaneInfo](../Topic/CStatusBar::GetPaneInfo.md)|Возвращает идентификатор, стиль и ширину индикатора для заданного индекса.|  
|[CStatusBar::GetPaneStyle](../Topic/CStatusBar::GetPaneStyle.md)|Возвращает стиль индикатора для заданного индекса.|  
|[CStatusBar::GetPaneText](../Topic/CStatusBar::GetPaneText.md)|Получает текст индикатора для заданного индекса.|  
|[CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)|Обеспечивает прямой доступ к общему элементу управления.|  
|[CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)|Задает идентификаторы индикатора.|  
|[CStatusBar::SetPaneInfo](../Topic/CStatusBar::SetPaneInfo.md)|Устанавливает идентификатор, стиль и ширину индикатора для заданного индекса.|  
|[CStatusBar::SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)|Задает стиль индикатора для заданного индекса.|  
|[CStatusBar::SetPaneText](../Topic/CStatusBar::SetPaneText.md)|Устанавливает текст индикатора для заданного индекса.|  
  
## Заметки  
 Панель вывода сообщений часто используются в виде линий, а также индикаторы состояния.  Примеры включают линии Справка\- сообщения меню, кратко объясняются выбранной команды меню и индикаторов, указывающие состояние БЛОКИРОВКИ ПРОКРУТКИ, NUM LOCK, а также других ключей.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), функция\-член новый с MFC 4.0 позволяет воспользоваться преимуществами поддержки управления Windows общим для настройки строки состояния и дополнительными функциональными возможностями.  Функции\-члены необходимо `CStatusBar` дают большую часть возможностей управления Windows общих; однако при вызове `GetStatusBarCtrl`, можно предоставить пользовательским строки состояния даже несколько характеристик Windows 95 \/98 строки состояния.  При вызове `GetStatusBarCtrl`, он возвращает ссылку на объект `CStatusBarCtrl`.  См. раздел [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) дополнительные сведения о конструировании панели инструментов с помощью управления Windows общие.  Общие сведения о стандартных элементах управления см. в разделе [общие элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Границы хранят данные индикатора в массиве, с левейшим индикатором в позиции 0.  При создании строки состояния, используется массив идентификаторов строки, которые связаны с соответствующей границы индикаторами.  Затем можно использовать либо идентификатор строки или индекс для доступа к индикатор.  
  
 По умолчанию индикатор эластик" первый ". он принимает длину строки состояния вверх, используемую другими областями индикатора не так, что другие панели будут выровненным по правому краю.  
  
 Для создания строки состояния выполните следующие действия:  
  
1.  Создайте объект `CStatusBar`.  
  
2.  Вызовите функцию [Создание](../Topic/CStatusBar::Create.md) \(или [CreateEx](../Topic/CStatusBar::CreateEx.md)\) для создания окна строки состояния и вложить его к объекту `CStatusBar`.  
  
3.  Вызовите [SetIndicators](../Topic/CStatusBar::SetIndicators.md) чтобы связать идентификатор строки с каждым индикатором.  
  
 3 Способа обновления текста на панели строки состояния.  
  
1.  Вызов [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md) для обновления текста в области 0.  
  
2.  Вызов [CCmdUI::SetText](../Topic/CCmdUI::SetText.md) в обработчике `ON_UPDATE_COMMAND_UI` строки состояния.  
  
3.  Вызов [SetPaneText](../Topic/CStatusBar::SetPaneText.md) для обновления текста для любой области.  
  
 Вызов [SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md) для обновления стиль панели строки состояния.  
  
 Дополнительные сведения об использовании `CStatusBar` см. в статье [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Техническая примечание 31. Панель элементов управления](../../mfc/tn031-control-bars.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [MFC просматривает CTRLBARS](../../top/visual-cpp-samples.md)   
 [Образец DLGCBR32 MFC](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)   
 [CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)