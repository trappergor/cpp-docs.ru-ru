---
title: 'Исключения: Исключения OLE | Документация Майкрософт'
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
ms.openlocfilehash: 6013caa79e21a305ba5ff8ad6266e960bb21504a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395249"
---
# <a name="exceptions-ole-exceptions"></a>Исключения. Исключения OLE

Методы и средства для обработки исключений в OLE одинаковы как для обработки других исключений. Дополнительные сведения об обработке исключений см. в статье [обработка исключений C++](../cpp/cpp-exception-handling.md).

Все исключения объекты являются производными от абстрактного базового класса `CException`. Для обработки исключения OLE в MFC предоставляет два класса:

- [COleException](../mfc/reference/coleexception-class.md) для обработки общего исключения OLE.

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) для создания и обработки OLE диспетчеризации исключения (автоматизация).

Различие между этими двумя классами является объем сведений, они предоставляют и где они используются. `COleException` имеет открытых членов данных, содержащий код состояния OLE для исключения. `COleDispatchException` предоставляет дополнительные сведения, включая следующие:

- Код ошибки, относящиеся к приложению

- Описание ошибки, например «Диск заполнен»

- Контекст справки, который приложение может использовать для предоставления дополнительных сведений для пользователя

- Имя файла справки в приложении

- Имя приложения, создавшего исключение

`COleDispatchException` предоставляет дополнительные сведения, чтобы он может использоваться с продуктами, такие как Microsoft Visual Basic. Описание устные ошибки можно использовать в окне сообщения или другие уведомления; Справочные сведения можно использовать чтобы помочь пользователю реакции на условия, вызвавшего исключение.

Две глобальные функции соответствуют классам два исключения OLE: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) и [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Их следует используйте для создания общего исключения OLE и диспетчеризации исключения OLE, соответственно.

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

