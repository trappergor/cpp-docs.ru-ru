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
ms.openlocfilehash: 7500db2a29f9d4ccef37b9265f5f2968c2d07993
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217952"
---
# <a name="exceptions-examining-exception-contents"></a>Исключения. Анализ содержимого исключений

Хотя **`catch`** аргумент блока может быть практически любого типа данных, функции MFC создают исключения типов, производных от класса `CException` . Чтобы перехватить исключение, вызванное функцией MFC, необходимо написать блок, **`catch`** аргумент которого является указателем на `CException` объект (или объект, производный от `CException` , например `CMemoryException` ). В зависимости от конкретного типа исключения можно изучить элементы данных объекта исключения, чтобы собрать сведения о конкретной причине исключения.

Например, `CFileException` тип имеет `m_cause` элемент Data, который содержит перечислимый тип, указывающий причину исключения файла. Примеры возможных возвращаемых значений: `CFileException::fileNotFound` и `CFileException::readOnly` .

В следующем примере показано, как проверить содержимое объекта `CFileException` . Другие типы исключений можно проверить аналогичным образом.

[!code-cpp[NVC_MFCExceptions#13](codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Дополнительные сведения см. [в разделе исключения: освобождение объектов в исключениях](exceptions-freeing-objects-in-exceptions.md) и [исключениях: перехват и удаление исключений](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
