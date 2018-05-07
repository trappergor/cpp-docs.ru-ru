---
title: 'Исключения: Исключения в конструкторах | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336700cc0137efe3bc106871ebd76b8de7a99af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-exceptions-in-constructors"></a>Исключения. Исключения в конструкторах
При создании исключения в конструкторе, очистить все объекты и выделения памяти внесенные до возникновения исключения, как описано в статье [исключения: создание исключений из свои собственные функции](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 При создании исключения в конструкторе, для самого объекта уже выделена память к моменту вызова конструктора. Таким образом компилятор автоматически будет освобождать память, занятую объекта после исключения.  
  
 Дополнительные сведения см. в разделе [исключения: освобождение объектов в исключениях](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

