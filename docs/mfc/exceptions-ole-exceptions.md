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
ms.openlocfilehash: 7bd0b0cb2c9eb6fe49356ae8fd4602676d54fa66
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622785"
---
# <a name="exceptions-ole-exceptions"></a>Исключения. Исключения OLE

Методы и средства обработки исключений в OLE одинаковы для обработки других исключений. Дополнительные сведения об обработке исключений см. в статье [современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

Все объекты исключений являются производными от абстрактного базового класса `CException` . MFC предоставляет два класса для обработки исключений OLE:

- [COleException](reference/coleexception-class.md) Для обработки общих исключений OLE.

- [COleDispatchException](reference/coledispatchexception-class.md) Для создания и обработки исключений OLE-диспетчеризации (Automation).

Разница между этими двумя классами — это объем информации, которую они предоставляют и где они используются. `COleException`содержит открытый элемент данных, содержащий код состояния OLE для исключения. `COleDispatchException`предоставляет дополнительные сведения, включая следующие:

- Код ошибки, относящийся к приложению

- Описание ошибки, например "диск полон"

- Контекст справки, который приложение может использовать для предоставления дополнительных сведений пользователю.

- Имя файла справки приложения

- Имя приложения, создавшего исключение

`COleDispatchException`предоставляет дополнительные сведения, которые можно использовать с такими продуктами, как Microsoft Visual Basic. Описание ошибки текстовом можно использовать в окне сообщения или в другом уведомлении. Справочные сведения можно использовать, чтобы помочь пользователю реагировать на условия, вызвавшие исключение.

Две глобальные функции соответствуют двум классам исключений OLE: [афкссроволиксцептион](reference/exception-processing.md#afxthrowoleexception) и [афкссроволедиспатчексцептион](reference/exception-processing.md#afxthrowoledispatchexception). Используйте их для создания общих исключений OLE и исключений OLE диспетчеризации соответственно.

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
