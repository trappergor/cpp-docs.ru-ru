---
title: "Исключения: Анализ содержимого исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 953dd61247f7d14ad04d5d5f85529c89f3aaad9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-examining-exception-contents"></a>Исключения. Анализ содержимого исключений
Несмотря на то что **перехватывать** блока аргумент может быть практически любого типа данных, типов, производных от класса исключения функции MFC `CException`. Чтобы перехватить исключение, создаваемое с помощью функции MFC, затем можно написать **перехватывать** блока, чей аргумент — указатель для `CException` объекта (или объект, производный от `CException`, такие как `CMemoryException`). В зависимости от точного типа исключения можно изучить данные элементы объекта исключения для сбора сведений о конкретной причины исключения.  
  
 Например `CFileException` тип имеет `m_cause` член данных, который содержит тип перечисления, указывающее причину исключения файлов. Некоторые примеры возможные возвращаемые значения **CFileException::fileNotFound** и **CFileException::readOnly**.  
  
 В следующем примере показано, как проверять содержимое `CFileException`. Аналогичным образом можно просмотреть другие типы исключений.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md) и [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

