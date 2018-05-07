---
title: 'Исключения: Исключения OLE | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991848e9b5b78ad960fb8ed0bdf09dd56db47e2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-ole-exceptions"></a>Исключения. Исключения OLE
Методы и средства для обработки исключений в OLE совпадают для обработки других исключений. Дополнительные сведения об обработке исключений см. в статье [обработку исключений C++](../cpp/cpp-exception-handling.md).  
  
 Все объекты исключений являются производными от абстрактного базового класса `CException`. Для обработки исключения OLE, MFC предоставляет два класса:  
  
-   [COleException](../mfc/reference/coleexception-class.md) для обработки исключений, общие OLE.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) для создания и обработки OLE отправки исключения (автоматизация).  
  
 Различие между этими двумя классами представляет объем информации, они предоставляют и где они используются. `COleException` имеет это открытый элемент данных, содержащее код состояния OLE для исключения. `COleDispatchException` предоставляет дополнительные сведения, включая следующие:  
  
-   Код ошибки для конкретного приложения  
  
-   Описание ошибки, например «Диск заполнен»  
  
-   Контекст справки, приложение может использовать для предоставления дополнительных сведений для пользователя  
  
-   Имя файла справки приложения  
  
-   Имя приложения, создавшего исключение  
  
 `COleDispatchException` предоставляет дополнительные сведения, чтобы он может использоваться с продуктами, такие как Microsoft Visual Basic. Описание устные ошибки можно использовать в окне сообщения или другие уведомления; Справочные сведения можно использовать для пользователя, который отвечает условиям, вызвавшего исключение.  
  
 Два класса исключения OLE соответствуют двух глобальных функций: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) и [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Их следует используйте для вызова общие исключения OLE и диспетчеризации исключения OLE, соответственно.  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

