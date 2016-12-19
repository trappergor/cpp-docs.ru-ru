---
title: "Исключения. Анализ содержимого исключений | Microsoft Docs"
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
  - "catch - блоки, исключения функции MFC"
  - "CException - класс, исключения класса"
  - "обработка исключений, MFC - библиотека"
  - "создание исключений, содержимое исключений"
  - "обработка исключений try-catch, содержимое исключений"
  - "обработка исключений try-catch, исключения функции MFC"
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Исключения. Анализ содержимого исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Хотя аргумент блока **catch** может быть практически любого типа данных, функции MFC вызывают исключений типов, производных от класса `CException`.  Чтобы перехватить исключение, вызванное функцией MFC, затем создается блок **catch** аргумент которого указатель на объект `CException` \(или объект, производный от `CException`, например `CMemoryException`\).  В зависимости от явного типа исключения можно проверить элементы данных объекта исключения с данными о статистике по определенной причине исключения.  
  
 Например, тип `CFileException` имеет элемент данных `m_cause`, содержащий перечисляемый тип, определяющий причину исключения файла.  Некоторые примеры возможных возвращаемых значений **CFileException::fileNotFound** и **CFileException::readOnly**.  
  
 В следующем примере показано, как просмотреть содержимое `CFileException`.  Другие типы исключений можно просмотреть аналогичным образом.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/CPP/exceptions-examining-exception-contents_1.cpp)]  
  
 Дополнительные сведения см. в разделах [Исключения: Освобождение объектов в исключениях](../Topic/Exceptions:%20Freeing%20Objects%20in%20Exceptions.md) и [Исключения: Улавливающ и удаление исключения](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)