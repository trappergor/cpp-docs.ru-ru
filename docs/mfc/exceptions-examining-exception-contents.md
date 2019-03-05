---
title: 'Исключения: Анализ содержимого исключений'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
ms.openlocfilehash: f6f9bca6f6b7ca9d104cb492c760ab89f7163afd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259390"
---
# <a name="exceptions-examining-exception-contents"></a>Исключения: Анализ содержимого исключений

Несмотря на то что **catch** блока аргумент может быть практически любого типа данных, функции MFC вызывать исключения типов, производных от класса `CException`. Для перехвата исключения, созданного с помощью функции MFC, затем можно написать **catch** блок, чей аргумент является указателем на `CException` объекта (или объекта, производного от `CException`, такие как `CMemoryException`). В зависимости от точного типа исключения можно просмотреть элементы данных объекта исключения для сбора сведений о конкретную причину исключения.

Например `CFileException` тип имеет `m_cause` элемент данных, который содержит перечисление, указывающее причину исключения «файл». Некоторые примеры возможные возвращаемые значения `CFileException::fileNotFound` и `CFileException::readOnly`.

В следующем примере показано, как изучение содержимого `CFileException`. Аналогичным образом можно проверить другие типы исключений.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Дополнительные сведения см. в разделе [исключения: Высвобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md) и [исключения: Перехват и удаление исключений](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
