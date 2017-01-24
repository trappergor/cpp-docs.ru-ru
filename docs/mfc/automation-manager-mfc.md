---
title: "Диспетчер автоматизации (MFC) | Microsoft Docs"
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
  - "AUTMGR32.exe"
  - "Клиенты автоматизации, Диспетчер автоматизации"
  - "Диспетчер автоматизации"
  - "Серверы автоматизации, Диспетчер автоматизации"
  - "автоматизация, Диспетчер автоматизации"
  - "Удаленная автоматизация, Диспетчер автоматизации"
ms.assetid: 6bf3429e-1946-41c5-86d0-ad7f5b8585b8
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Диспетчер автоматизации (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

AUTMGR32.EXE должно быть скопировано в системный каталог Windows каждого компьютера, который планирует предоставить объекты удаленной автоматизации.  Для Windows 95 и Windows 98 этот каталог, как правило, C: \\WINDOWS\\SYSTEM.  Для Windows NT и Windows 2000 обычно это C: \\WINNT\\SYSTEM32.  
  
 Если необходимо включить обратные вызовы от сервера клиенту, этот исполняемый файл должен быть скопирован в системный каталог каждого клиентского компьютера.  
  
 Когда диспетчер автоматизации выполнения отображается небольшое окно на компьютере сервера, который содержит краткое сведения о состоянии.  Если необходимо скрывать его, см. раздел Q138067 в Базе знаний Майкрософт.  
  
## См. также  
 [Диспетчер подключений удаленной автоматизации](../mfc/remote-automation-connection-manager.md)   
 [Пользовательские компоненты удаленной автоматизации](../mfc/remote-automation-user-components.md)   
 [Установка удаленной автоматизации](../Topic/Remote%20Automation%20Installation.md)