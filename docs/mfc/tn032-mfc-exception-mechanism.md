---
title: 'TN032: Механизм исключений MFC | Документы Microsoft'
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
ms.openlocfilehash: 5256f787534ab408920f7154122ae0c5934019c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380845"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032. Механизм исключений MFC
Предыдущих версий Visual C++ не поддерживает стандартный механизм исключений C++ и MFC предоставленный макросы **TRY, CATCH и THROW** , которые использовались. Эта версия Visual C++ полностью поддерживает исключения C++. Эта заметка рассматриваются некоторые сведения расширенную реализацию предыдущих макросов включая автоматически очистки стека на основе объектов. Так как исключения C++ поддерживает развертывание по умолчанию стека, это техническое Примечание не требуется.  
  
 Ссылаться на [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) Дополнительные сведения о различиях между макросов MFC и новые ключевые слова C++.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

