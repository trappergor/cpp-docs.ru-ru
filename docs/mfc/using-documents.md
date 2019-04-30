---
title: Использование документов
ms.date: 11/04/2016
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
ms.openlocfilehash: fb35d1731912b2e322bc61621f7900e0d98e1e72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411595"
---
# <a name="using-documents"></a>Использование документов

Совместная работа, документов и представлений:

- Содержат, управления и отображения конкретного приложения [данных](../mfc/managing-data-with-document-data-variables.md).

- Предоставить интерфейс, состоящий из [переменных данных документа](../mfc/managing-data-with-document-data-variables.md) для манипуляций с данными.

- Участвовать в [записи и чтения файлов](../mfc/serializing-data-to-and-from-files.md).

- Участвовать в [печати](../mfc/role-of-the-view-in-printing.md).

- [Обрабатывать](../mfc/handling-commands-in-the-document.md) большинство команд и сообщений в приложении.

Его особенно участвует в управлении данными. Store данных, как правило, в переменные-члены класса документа. В представлении используются эти переменные для доступа к данным для отображения и обновления. Механизм сериализации документа по умолчанию управляет чтением и записью данных, файлов и из нее. Документы также может обрабатывать команды (но не сообщения Windows, отличные от WM_COMMAND).

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Наследование класса документов от CDocument](../mfc/deriving-a-document-class-from-cdocument.md)

- [Управление данными с помощью переменных данных документа](../mfc/managing-data-with-document-data-variables.md)

- [Сериализация данных из файлов](../mfc/serializing-data-to-and-from-files.md)

- [Обход механизма сериализации](../mfc/bypassing-the-serialization-mechanism.md)

- [Обработка команд в документе](../mfc/handling-commands-in-the-document.md)

- [Функция-член OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)

- [Функция-член DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)
