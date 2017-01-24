---
title: "Обработчики команд для прокрутки записей (доступ к данным MFC)  | Microsoft Docs"
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
  - "прокрутки записей [C++]"
  - "представления записей [C++], прокрутка"
  - "прокрутка записей"
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработчики команд для прокрутки записей (доступ к данным MFC) 
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Классы [CRecordView](../mfc/reference/crecordview-class.md) и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) обеспечивают обработку по умолчанию для следующих стандартных команд :  
  
-   **ID\_RECORD\_MOVE\_FIRST**  
  
-   **ID\_RECORD\_MOVE\_LAST**  
  
-   **ID\_RECORD\_MOVE\_NEXT**  
  
-   **ID\_RECORD\_MOVE\_PREV**  
  
 Функция\-член `OnMove` классов `CRecordView` и `CDaoRecordView` предоставляет  обработку по умолчанию для всех четырех команд, при переходе от записи к записи.  Если команды даны, RFX \(или DFX\) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи.  Дополнительные сведения о RFX см. [обмен полей записей \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.  
  
## См. также  
 [Поддержка навигации в представлении записей](../Topic/Supporting%20Navigation%20in%20a%20Record%20View%20%20\(MFC%20Data%20Access\).md)