---
title: Классы контейнера OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 61db5310637d13da2d2cc183f12f8f62aa60e328
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447655"
---
# <a name="ole-container-classes"></a>Классы контейнера OLE

Эти классы используются приложениями контейнеров. `COleLinkingDoc` и `COleDocument` управляют коллекциями `COleClientItem`ных объектов. Вместо того, чтобы создавать производный класс документа от `CDocument`, вы будете наследовать его от `COleLinkingDoc` или `COleDocument`в зависимости от того, требуется ли поддержка ссылок на объекты, внедренные в документ.

Используйте объект `COleClientItem` для представления каждого элемента OLE в документе, внедренного из другого документа, или ссылки на другой документ.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
Поддерживает включение активных документов.

[коледокумент](../mfc/reference/coledocument-class.md)<br/>
Используется для реализации составного документа, а также для поддержки базовых контейнеров. Служит контейнером для классов, производных от `CDocItem`. Этот класс может использоваться в качестве базового класса для документов контейнера и является базовым классом для `COleServerDoc`.

[колелинкингдок](../mfc/reference/colelinkingdoc-class.md)<br/>
Класс, производный от `COleDocument`, который предоставляет инфраструктуру для компоновки. Классы документов для приложений контейнера следует наследовать от этого класса, а не `COleDocument`, если требуется, чтобы они поддерживали ссылки на внедренные объекты.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Поддерживает список элементов OLE, которые находятся в элементе управления Rich Edit. Используется с [CRichEditView](../mfc/reference/cricheditview-class.md) и [кричедиткнтритем](../mfc/reference/cricheditcntritem-class.md).

[кдоЦитем](../mfc/reference/cdocitem-class.md)<br/>
Абстрактный базовый класс `COleClientItem` и `COleServerItem`. Объекты классов, производных от `CDocItem`, представляют части документов.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
Класс клиентского элемента, представляющий сторону клиента соединения с внедренным или связанным элементом OLE. Наследовать клиентские элементы от этого класса.

[кричедиткнтритем](../mfc/reference/cricheditcntritem-class.md)<br/>
Предоставляет доступ на стороне клиента к элементу OLE, хранящемуся в элементе управления Rich Edit, при использовании с `CRichEditView` и `CRichEditDoc`.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Исключение, полученное при сбое обработки OLE. Этот класс используется как контейнерами, так и серверами.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
