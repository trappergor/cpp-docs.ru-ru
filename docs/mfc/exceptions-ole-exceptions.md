---
title: Исключения. Исключения OLE
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: 1606a0f5a86996345e12024cf6416afdf6bdc82b
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246712"
---
# <a name="exceptions-ole-exceptions"></a>Исключения. Исключения OLE

Методы и средства обработки исключений в OLE одинаковы для обработки других исключений. Дополнительные сведения об обработке исключений см. в статье [современные C++ рекомендации по исключениям и обработке ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

Все объекты исключений являются производными от абстрактного базового класса `CException`. MFC предоставляет два класса для обработки исключений OLE:

- [COleException](../mfc/reference/coleexception-class.md) Для обработки общих исключений OLE.

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) Для создания и обработки исключений OLE-диспетчеризации (Automation).

Разница между этими двумя классами — это объем информации, которую они предоставляют и где они используются. `COleException` имеет открытый элемент данных, содержащий код состояния OLE для исключения. `COleDispatchException` предоставляет дополнительные сведения, включая следующие:

- Код ошибки, относящийся к приложению

- Описание ошибки, например "диск полон"

- Контекст справки, который приложение может использовать для предоставления дополнительных сведений пользователю.

- Имя файла справки приложения

- Имя приложения, создавшего исключение

`COleDispatchException` предоставляет дополнительные сведения, которые можно использовать с такими продуктами, как Microsoft Visual Basic. Описание ошибки текстовом можно использовать в окне сообщения или в другом уведомлении. Справочные сведения можно использовать, чтобы помочь пользователю реагировать на условия, вызвавшие исключение.

Две глобальные функции соответствуют двум классам исключений OLE: [афкссроволиксцептион](../mfc/reference/exception-processing.md#afxthrowoleexception) и [афкссроволедиспатчексцептион](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Используйте их для создания общих исключений OLE и исключений OLE диспетчеризации соответственно.

## <a name="see-also"></a>См. также:

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
