---
title: "Функция-член OnIdle | Microsoft Docs"
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
  - "OnIdle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp - класс, OnIdle - метод"
  - "обработка пустых циклов"
  - "обработка сообщений, OnIdle - метод"
  - "OnIdle - метод"
  - "обработка сообщений"
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция-член OnIdle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При отсутствии сообщений Windows не обрабатываются, платформа вызывает функцию\-член [OnIdle](../Topic/CWinApp::OnIdle.md)[CWinApp](../mfc/reference/cwinapp-class.md) \(описанный в справочнике библиотеки MFC\).  
  
 Переопределение `OnIdle` для выполнения фоновых задач.  Версия по умолчанию обновляет состояние объектов пользовательского интерфейса, такие как кнопки панели инструментов и выполняет очистку временных объектов, созданных средой в процессе его операций.  На следующем рисунке показано, как цикл обработки сообщений вызывает `OnIdle` при сообщений в очереди.  
  
 ![Процесс цикла сообщений](../mfc/media/vc387c1.png "vc387C1")  
Цикл обработки сообщений  
  
 Дополнительные сведения о том, что можно сделать в циклом бездействия, см. в разделе [Обработка пустых циклов](../Topic/Idle%20Loop%20Processing.md).  
  
## См. также  
 [CWinApp: класс приложений](../Topic/CWinApp:%20The%20Application%20Class.md)