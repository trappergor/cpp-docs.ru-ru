---
title: "Классы сокетов Windows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.net"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы сокетов"
  - "Сокеты Windows [C++], классы"
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Классы сокетов Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows sockets предоставляют способ сети не зависит от 2 протокол\- обмена данными между компьютерами.  Эти сокетов могут быть синхронный \(программа ожидает до тех пор, пока сообщение не выполняется\) или асинхронный \(программа продолжает работу, пока сообщение чем причина\).  
  
 [CAsyncSocket](../Topic/CAsyncSocket%20Class.md)  
 Инкапсулирует API Windows sockets тонкой в программе\-оболочке.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Абстракция уровня, производная от `CAsyncSocket`.  Она работает одновременно.  
  
 [CSocketFile](../Topic/CSocketFile%20Class.md)  
 Предоставляет интерфейс `CFile` сокет Windows.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)