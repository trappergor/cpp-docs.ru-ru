---
title: "Серверные классы OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "компоненты COM, классы"
  - "классы компонентов"
  - "приложения сервера OLE, серверные классы"
  - "серверные документы OLE"
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Серверные классы OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы используются серверными приложениями.  Серверные документы являются производными от `COleServerDoc`, а не из **CDocument**.  Обратите внимание, что поскольку `COleServerDoc` является производным от `COleLinkingDoc`, серверные документы могут также быть контейнерами, которые поддерживают связывание.  
  
 Класс `COleServerItem` представляет документ или части документа, который может быть включен в другом документе или связана с.  
  
 `COleIPFrameWnd` и `COleResizeBar` поддерживают редактирование локально, пока объект в контейнере, и `COleTemplateServer` поддерживает создание пар документ\/представление таким образом OLE объекты из других приложений можно изменять.  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
 Используется как базовый класс для классов документа серверного приложения.  объекты `COleServerDoc` предоставляют пакетную поддержки сервера посредством взаимодействия с объектами `COleServerItem`.  Предоставляется возможность визуального редактирования с использованием архитектуры документов и представлений библиотеки классов.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс `COleClientItem` и `COleServerItem`.  Объекты классов, производных от `CDocItem` представляют частей документов.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 Используется для представления OLE интерфейс к элементам `COleServerDoc`.  Обычно один объект `COleServerDoc`, который представляет внедренную текстовую часть документа.  На серверах, поддержки указатели на части документов, существует множество объектов могут быть `COleServerItem`, каждый из которых представляет ссылку на части документа.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет фреймовое окно для представления при документа серверного редактирования на месте.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Предоставляет интерфейс для обычного пользователя на месте изменения.  Объекты этого класса всегда используются вместе с объектами `COleIPFrameWnd`.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Используется для создания документов с использованием архитектуры документов и представлений платформы.  Объект `COleTemplateServer` делегирует большинство его работы на связанный объект `CDocTemplate`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключение и в результате сбоя в OLE обработки.  Этот класс используется как контейнерами, и серверами.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)