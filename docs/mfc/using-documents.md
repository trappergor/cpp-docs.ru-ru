---
title: Использование документов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb5e6ad4cfcc1e14d3b6accc1e5adaf4037669a4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950218"
---
# <a name="using-documents"></a>Использование документов
Совместной работе, документов и представлений:  
  
-   Содержат, управления и отображения конкретного приложения [данные](../mfc/managing-data-with-document-data-variables.md).  
  
-   Предоставить интерфейс, состоящий из [переменных данных документа](../mfc/managing-data-with-document-data-variables.md) для работы с данными.  
  
-   Участвовать в [записи и чтения файлов](../mfc/serializing-data-to-and-from-files.md).  
  
-   Участвовать в [печати](../mfc/role-of-the-view-in-printing.md).  
  
-   [Обрабатывать](../mfc/handling-commands-in-the-document.md) большинство команд и сообщений приложения.  
  
 Документ особенно участвует в управлении данными. Как правило, хранения данных, в переменные-члены класса документа. В представлении эти переменные используются для доступа к данным для отображения и обновления. Механизм сериализации документа по умолчанию управляет чтение и запись данных из файлов. Документы можно также обрабатывать команды (но не сообщения Windows, отличные от WM_COMMAND).  
  
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

