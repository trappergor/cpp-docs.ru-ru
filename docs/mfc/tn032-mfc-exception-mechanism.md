---
title: 'TN032: Механизм исключений MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aee8ce02af874e1c3c30243a35e8f36acfce63f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414762"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032. Механизм исключений MFC

Предыдущие версии Visual C++ не поддерживает стандартный механизм исключений C++ и MFC предоставленный макросы **TRY/CATCH/THROW** , которые использовались. Эта версия Visual C++ полностью поддерживает исключения C++. Эта заметка рассматриваются некоторые сведения расширенной реализации предыдущего макросов, включая Практическое автоматически Очистка стека на основе объектов. Так как исключения C++ поддерживает развертывание по умолчанию стека, это техническое Примечание нет необходимости.

Ссылаться на [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) Дополнительные сведения о различиях между макросов MFC и новые ключевые слова C++.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)

