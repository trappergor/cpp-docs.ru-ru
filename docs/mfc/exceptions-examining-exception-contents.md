---
title: Исключения. Анализ содержимого исключений
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
ms.openlocfilehash: 4355a575f29741d0c7b9f1e12e40ca9d977219b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630081"
---
# <a name="exceptions-examining-exception-contents"></a>Исключения. Анализ содержимого исключений

Несмотря на то что **catch** блока аргумент может быть практически любого типа данных, функции MFC вызывать исключения типов, производных от класса `CException`. Для перехвата исключения, созданного с помощью функции MFC, затем можно написать **catch** блок, чей аргумент является указателем на `CException` объекта (или объекта, производного от `CException`, такие как `CMemoryException`). В зависимости от точного типа исключения можно просмотреть элементы данных объекта исключения для сбора сведений о конкретную причину исключения.

Например `CFileException` тип имеет `m_cause` элемент данных, который содержит перечисление, указывающее причину исключения «файл». Некоторые примеры возможные возвращаемые значения `CFileException::fileNotFound` и `CFileException::readOnly`.

В следующем примере показано, как изучение содержимого `CFileException`. Аналогичным образом можно проверить другие типы исключений.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md) и [исключений: исключения для перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

