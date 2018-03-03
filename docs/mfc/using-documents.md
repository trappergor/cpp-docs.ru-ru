---
title: "Использование документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 691d8d00b9c4671ea4b9c318313851a7fab73f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-documents"></a>Использование документов
Совместной работе, документов и представлений:  
  
-   Содержат, управления и отображения конкретного приложения [данные](../mfc/managing-data-with-document-data-variables.md).  
  
-   Предоставить интерфейс, состоящий из [переменных данных документа](../mfc/managing-data-with-document-data-variables.md) для работы с данными.  
  
-   Участвовать в [записи и чтения файлов](../mfc/serializing-data-to-and-from-files.md).  
  
-   Участвовать в [печати](../mfc/role-of-the-view-in-printing.md).  
  
-   [Обрабатывать](../mfc/handling-commands-in-the-document.md) большинство команд и сообщений приложения.  
  
 Документ особенно участвует в управлении данными. Как правило, хранения данных, в переменные-члены класса документа. В представлении эти переменные используются для доступа к данным для отображения и обновления. Механизм сериализации документа по умолчанию управляет чтение и запись данных из файлов. Документы можно также обрабатывать команды (но не Windows сообщения, отличного от **WM_COMMAND**).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Наследование класса документов от CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Управление данными с помощью переменных данных документа](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Сериализация данных из файлов](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Обход механизма сериализации](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Обработка команд в документе](../mfc/handling-commands-in-the-document.md)  
  
-   [Функция-член OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [Функция-член DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)

