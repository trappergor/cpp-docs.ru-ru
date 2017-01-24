---
title: "Использование документов | Microsoft Docs"
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
  - "данные [MFC], документы"
  - "данные [MFC], чтение"
  - "архитектура документа/обзора [C++], документы"
  - "документы [C++]"
  - "документы [C++], приложения C++"
  - "файлы [C++]"
  - "файлы [C++], запись в"
  - "печать [MFC], документы"
  - "чтение данных [C++], документы и представления"
  - "представления [C++], приложения C++"
  - "запись в файлы [C++]"
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование документов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Совместная работа, документы и представления.  
  
-   Хранить, управлять и показывать для конкретного приложения [данные](../mfc/managing-data-with-document-data-variables.md).  
  
-   Предоставить интерфейс, состоящий из [переменные данных документа](../mfc/managing-data-with-document-data-variables.md) для управления данными.  
  
-   Обратитесь к [чтения и записи файлов](../mfc/serializing-data-to-and-from-files.md).  
  
-   Обратитесь к [печать](../mfc/role-of-the-view-in-printing.md).  
  
-   [Дескриптор](../mfc/handling-commands-in-the-document.md) большинство команд и сообщений приложения.  
  
 Документ особенно являются управления данными.  Сохраните данные, обычно в переменных\-членах класса документа.  Представление использует эти переменные для доступа к данным для отображения и обновления.  Механизм сериализации по умолчанию документа управляет чтение и запись данных на диск и с него файлов.  Документы могут также обрабатывать команды \(но не сообщения Windows, кроме **WM\_COMMAND**\).  
  
## Дополнительные сведения  
  
-   [Производный класс из документа CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Управление данными с переменными данных документа](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Сериализовать данные на них и с них файлов](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Пропуск механизм сериализации](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Обработка команды в документе](../mfc/handling-commands-in-the-document.md)  
  
-   [Функция\-член OnNewDocument](../Topic/CDocument::OnNewDocument.md)  
  
-   [Функция\-член DeleteContents](../Topic/CDocument::DeleteContents.md)  
  
## См. также  
 [Архитектура "документ\-представление"](../Topic/Document-View%20Architecture.md)