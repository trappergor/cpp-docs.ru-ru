---
title: "Разработка и создание представления записей (доступ к данным MFC) | Microsoft Docs"
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
  - "мастера приложений [C++], создание классов представления записей"
  - "конструирование форм"
  - "конструирование представлений записей"
  - "формы [C++], разработка"
  - "представления записей, создание"
  - "представления записей, разработка"
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Разработка и создание представления записей (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно создать класс представления записей с [мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md).  При использовании мастера приложений он создает класс представления записей и ресурс шаблона диалоговых окон для него \(без элементов управления\).  Для добавления элементов управления в ресурс шаблона диалоговых окон необходимо использовать редактор диалоговых окон Visual C\+\+.  С другой стороны, при использовании **Добавить класс**, необходимо сначала создать ресурс шаблона диалоговых окон в Редакторе диалоговых окон и затем создать класс представления записей.  
  
 Эти сведения применимы к обоим `CRecordView` и `CDaoRecordView`.  
  
#### Для создание представления записей с помощью мастера приложений MFC  
  
1.  Смотрите [Поддержка базы данных, мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md).  
  
#### Разработка формы  
  
1.  Смотрите [Редактор диалоговых окон](../mfc/dialog-editor.md).  
  
#### Чтобы создать класс представления записей  
  
1.  Смотрите [Добавление потребителя ODBC MFC](../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 В следующих разделах представлены дополнительные сведения об использовании представления записей:  
  
-   [Представления записей Поддержка навигации в представлении записей](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)  
  
-   [Представления записей Использование представления записей](../data/using-a-record-view-mfc-data-access.md)  
  
-   [Представления записей Заполнение списка из второго набора записей](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)  
  
## См. также  
 [Представления записей \(доступ к данным MFC\)](../data/record-views-mfc-data-access.md)   
 [Набор записей \(ODBC\)](../data/odbc/recordset-odbc.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)