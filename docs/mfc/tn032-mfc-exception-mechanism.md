---
title: "TN032: Механизм исключений MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf82d4b158cedd2d8f6916dfb01d26db6c62d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032. Механизм исключений MFC
Предыдущих версий Visual C++ не поддерживает стандартный механизм исключений C++ и MFC предоставленный макросы **TRY, CATCH и THROW** , которые использовались. Эта версия Visual C++ полностью поддерживает исключения C++. Эта заметка рассматриваются некоторые сведения расширенную реализацию предыдущих макросов включая автоматически очистки стека на основе объектов. Так как исключения C++ поддерживает развертывание по умолчанию стека, это техническое Примечание не требуется.  
  
 Ссылаться на [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) Дополнительные сведения о различиях между макросов MFC и новые ключевые слова C++.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

