---
title: 'TN032: Механизм исключений MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 5b419fdcc4f20579b1a809dd8a5cf6a93f4fe835
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611411"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: Механизм исключений MFC

Предыдущие версии Visual C++ не поддерживает стандартный механизм исключений C++ и MFC предоставленный макросы **TRY/CATCH/THROW** , которые использовались. Эта версия Visual C++ полностью поддерживает исключения C++. Эта заметка рассматриваются некоторые сведения расширенной реализации предыдущего макросов, включая Практическое автоматически Очистка стека на основе объектов. Так как исключения C++ поддерживает развертывание по умолчанию стека, это техническое Примечание нет необходимости.

Ссылаться на [исключения: Использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) Дополнительные сведения о различиях между макросов MFC и новые ключевые слова C++.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
