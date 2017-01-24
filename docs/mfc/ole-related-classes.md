---
title: "Классы, связанные с OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "ActiveX - классы [C++]"
  - "OLE [C++], классы"
  - "классы OLE [C++]"
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы, связанные с OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы предоставляют несколько различных служб, — от исключений ввод и вывод файла.  
  
 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)  
 Используется для создания элементов исключение из других контейнеров.  Этот класс служит базовым классом для более определенных типов фабрик, включая `COleTemplateServer`.  
  
 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md)  
 Используется для управления параллелизмом с OLE облегченными удаленными вызовами процедур \(RPC\) \(LRPC\).  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
 Использует интерфейс `IStream` модели COM для предоставления доступа `CFile` с составным файлы.  Этот класс \(производный от `CFile`\) позволяет использовать хранилище структурного сериализация MFC OLE.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Используется, чтобы разрешить перемещать, изменять и переориентация на месте элементов.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)