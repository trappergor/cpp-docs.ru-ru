---
title: "Функциональные возможности классов представления записей (доступ к данным MFC) | Microsoft Docs"
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
  - "классы представления записей"
  - "представления записей, классы"
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функциональные возможности классов представления записей (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это можно сделать программированием доступа к данным на основе формы с помощью класса [CFormView](../mfc/reference/cformview-class.md), но [CRecordView](../mfc/reference/crecordview-class.md)и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)являются более подходящими классами для извлечения.  В дополнение к их функциям `CFormView`, `CRecordView` и `CDaoRecordView`:  
  
-   Обеспечивают обмен данными диалоговых окон \(DDX\) между элементами управления формы и ассоциированным объектом набора записей.  
  
-   Задействуйте команды Переместить первый, переместить следующий, переместить предыдущий и переместить последний для перемещения по записям в связанном объекте набора записей.  
  
-   Обновление изменений в текущей записи при переходе к другой записи.  
  
 Для дополнительной информации по навигации, см. [Представления записей:](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)[](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)[Поддержка навигации в представлении записей](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)  
  
## См. также  
 [Представления записей \(доступ к данным MFC\)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)