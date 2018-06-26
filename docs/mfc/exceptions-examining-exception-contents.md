---
title: 'Исключения: Анализ содержимого исключений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82c7453b92ce14fbbcd20ea0f9a8bd8a7a2b5b6d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932238"
---
# <a name="exceptions-examining-exception-contents"></a>Исключения. Анализ содержимого исключений
Несмотря на то что **перехватывать** блока аргумент может быть практически любого типа данных, типов, производных от класса исключения функции MFC `CException`. Чтобы перехватить исключение, создаваемое с помощью функции MFC, затем можно написать **перехватывать** блока, чей аргумент — указатель для `CException` объекта (или объект, производный от `CException`, такие как `CMemoryException`). В зависимости от точного типа исключения можно изучить данные элементы объекта исключения для сбора сведений о конкретной причины исключения.  
  
 Например `CFileException` тип имеет `m_cause` член данных, который содержит тип перечисления, указывающее причину исключения файлов. Некоторые примеры возможные возвращаемые значения `CFileException::fileNotFound` и `CFileException::readOnly`.  
  
 В следующем примере показано, как проверять содержимое `CFileException`. Аналогичным образом можно просмотреть другие типы исключений.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md) и [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

