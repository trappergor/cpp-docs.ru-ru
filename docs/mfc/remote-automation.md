---
title: "Удаленная автоматизация | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Контроллер автоматизации"
  - "объекты автоматизации"
  - "объекты автоматизации, создание"
  - "COM, Удаленная автоматизация"
  - "DCOM, Удаленная автоматизация"
  - "MFC COM, Удаленная автоматизация"
  - "MFC - библиотека, поддержка COM"
  - "Удаленная автоматизация"
ms.assetid: 363f87fb-08fa-4458-b089-b46365a6d4f2
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Удаленная автоматизация
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Рекомендуется, чтобы разработчики Visual C\+\+ .NET C используют DCOM, а не удаленной автоматизации для новых применений.  C Visual C\+\+ .NET не поддерживает Windows 95.  В некоторых случаях необходимо поддерживать удаленной автоматизации приведены в разделе [, Где выполняется удаленная автоматизации преобразованная в?](../mfc/where-does-remote-automation-fit-in-q.md).  
  
 Удаленная автоматизации тип [Автоматизация](../mfc/automation.md), позволяющий объект\-получатель интерфейса для выполнения поставщик интерфейса, находящийся на другом компьютере, например в сети.  
  
 В этой статье описывается, как создать объекты автоматизации, которые могут быть вызваны и выполнять удаленно и как создавать контроллеры автоматизации, которые могут использовать эти объекты удаленной автоматизации.  Он также проверяет параметры конфигурации и точки, основные различия между удаленной автоматизации и DCOM \(распределенной версии модели COM и OLE, позволяющей интерфейсы, отличные от связанных к автоматизации, вызываемый и исполненную удаленно\).  
  
## Содержание  
 [Журнал DCOM \(DCOM\)](../mfc/history-of-dcom.md)  
  
 [, Где выполняется удаленная автоматизации преобразованная в?](../mfc/where-does-remote-automation-fit-in-q.md)  
  
 [Что удаленной автоматизации предоставляет?](../mfc/what-does-remote-automation-provide-q.md)  
  
 [Безопасность удаленной автоматизации](../mfc/security-in-remote-automation.md)  
  
 [Потоковые модели](../mfc/remote-automation-threading-models.md)  
  
 [Установка](../Topic/Remote%20Automation%20Installation.md)  
  
 [Диспетчер автоматизации](../mfc/automation-manager-mfc.md)  
  
-   [Удаленная автоматизации диспетчер подключений](../mfc/remote-automation-connection-manager.md)  
  
-   [Компоненты пользователя удаленной автоматизации](../mfc/remote-automation-user-components.md)  
  
 [Создание программы, использующие удаленной автоматизации](../mfc/creating-programs-that-use-remote-automation.md)  
  
 [Выполнение удаленной с помощью автоматизации AUTOCLIK и AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)  
  
## См. также  
 [MFC COM](../mfc/mfc-com.md)   
 [автоматизация](../mfc/automation.md)