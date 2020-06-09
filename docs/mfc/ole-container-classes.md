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
ms.openlocfilehash: 596b94e7fdbb5d9dc1862867001f6c01c1aea7b2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617808"
---
# <a name="ole-container-classes"></a>Классы контейнера OLE

Эти классы используются приложениями контейнеров. `COleLinkingDoc`И `COleDocument` Управление коллекциями `COleClientItem` объектов. Вместо того, чтобы создавать производный класс документа от, вы наследуете `CDocument` его от `COleLinkingDoc` или `COleDocument` , в зависимости от того, требуется ли поддержка ссылок на объекты, внедренные в документ.

Используйте `COleClientItem` объект для представления каждого элемента OLE в документе, внедренного из другого документа, или ссылки на другой документ.

[COleDocObjectItem](reference/coledocobjectitem-class.md)<br/>
Поддерживает включение активных документов.

[COleDocument](reference/coledocument-class.md)<br/>
Используется для реализации составного документа, а также для поддержки базовых контейнеров. Служит контейнером для классов, производных от `CDocItem` . Этот класс может использоваться в качестве базового класса для документов контейнера и является базовым классом для `COleServerDoc` .

[COleLinkingDoc](reference/colelinkingdoc-class.md)<br/>
Класс, производный от `COleDocument` , который предоставляет инфраструктуру для компоновки. Классы документов для приложений контейнера следует наследовать от этого класса, а не от `COleDocument` , если требуется, чтобы они поддерживали ссылки на внедренные объекты.

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
Поддерживает список элементов OLE, которые находятся в элементе управления Rich Edit. Используется с [CRichEditView](reference/cricheditview-class.md) и [кричедиткнтритем](reference/cricheditcntritem-class.md).

[CDocItem](reference/cdocitem-class.md)<br/>
Абстрактный базовый класс для `COleClientItem` и `COleServerItem` . Объекты классов, производных от, `CDocItem` представляют части документов.

[COleClientItem](reference/coleclientitem-class.md)<br/>
Класс клиентского элемента, представляющий сторону клиента соединения с внедренным или связанным элементом OLE. Наследовать клиентские элементы от этого класса.

[CRichEditCntrItem](reference/cricheditcntritem-class.md)<br/>
Предоставляет доступ на стороне клиента к элементу OLE, хранящемуся в элементе управления Rich Edit при использовании с `CRichEditView` и `CRichEditDoc` .

[COleException](reference/coleexception-class.md)<br/>
Исключение, полученное при сбое обработки OLE. Этот класс используется как контейнерами, так и серверами.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
