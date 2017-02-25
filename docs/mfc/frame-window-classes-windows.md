---
title: "Классы окна фрейма (Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы окна фрейма, справочник"
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Классы окна фрейма (Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Фреймовые окна кадр, приложение или частью приложения.  Фреймовые окна обычно содержат другие окна, как представления, панели инструментов и строки состояния.  В случае `CMDIFrameWnd`, они могут содержать объекты `CMDIChildWnd` косвенно.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Базовый класс для фреймового окна приложения SDI главного.  Также базовый класс для всех других классов фреймового окна.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Базовый класс для фреймового окна приложения MDI главного.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Базовый класс для фреймов окна документов приложения MDI.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Снижение фреймовое окно, в случае раза\- высоты обычно изначально объявленного как вокруг инструментов с плавающей запятой.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет фреймовое окно для представления при документа серверного редактирования на месте.  
  
## Класс Related  
 Класс `CMenu` предоставляет интерфейс, с помощью которого для доступа к меню приложения.  Используется для управления меню динамически во время выполнения; например, добавление или удаление пунктов меню в зависимости от контекста.  Хотя меню чаще всего используются с фреймовыми окнами, их можно также использовать с диалоговыми окнами и другими окнами nonchild.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Инкапсулирует дескриптор `HMENU` в строке меню и всплывающим меню приложения.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)