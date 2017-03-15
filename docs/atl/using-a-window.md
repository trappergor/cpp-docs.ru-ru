---
title: "Using a Window | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, окна"
  - "CWindow class, about CWindow class"
  - "windows [C++], ATL - библиотека"
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using a Window
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс [CWindow](../atl/reference/cwindow-class.md) позволяет использовать окна.  Как только к объекту вложение окно `CWindow`, затем можно вызывать методы `CWindow` управлять окно.  `CWindow` также содержит оператор `HWND` для преобразования объекта `CWindow` к `HWND`.  Таким образом можно передать объект `CWindow` к любой функции, для которой необходим дескриптора окна.  Вызовы метода `CWindow` смешивания можно легко и вызовы функций Win32, без создания все временные объекты.  
  
 Поскольку `CWindow` имеет член данных только 2 \(дескриптор окна и измерения по умолчанию\), он не накладывает дополнительные издержки на коде.  Кроме того, многие методы `CWindow` просто программу\-оболочку создают соответствующие функции api\-интерфейса Win32.  С помощью `CWindow` участник `HWND` автоматически передается функции Win32.  
  
 Помимо использования непосредственно `CWindow` также можно наследовать от него, чтобы добавить данные или код к классу.  Библиотеки ATL является производным от класса `CWindow`: 3 [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md) и [CContainedWindowT](../Topic/Using%20Contained%20Windows.md).  
  
## См. также  
 [Классы окон](../Topic/ATL%20Window%20Classes.md)