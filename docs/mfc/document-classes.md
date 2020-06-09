---
title: Классы документов
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: 012d107d7bcc630c4bc02a9dc697172080787eac
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615807"
---
# <a name="document-classes"></a>Классы документов

Объекты классов документов, созданные объектами шаблонов документов, управляют данными приложения. Класс для ваших документов будет производным от одного из этих классов.

Объекты класса Document взаимодействуют с объектами представления. Объекты представления представляют собой клиентскую область окна, отображают данные документа и позволяют пользователям взаимодействовать с ним. Документы и представления создаются объектом шаблона документа.

[CDocument](reference/cdocument-class.md)<br/>
Базовый класс для документов конкретного приложения. Создайте класс документа или классы из `CDocument` .

[COleDocument](reference/coledocument-class.md)<br/>
Используется для реализации составного документа, а также для поддержки базовых контейнеров. Служит контейнером для классов, производных от [кдоЦитем](reference/cdocitem-class.md). Этот класс может использоваться в качестве базового класса для документов контейнера и является базовым классом для `COleServerDoc` .

[COleLinkingDoc](reference/colelinkingdoc-class.md)<br/>
Класс, производный от `COleDocument` , который предоставляет инфраструктуру для компоновки. Классы документов для приложений контейнера следует наследовать от этого класса, а не от `COleDocument` , если требуется, чтобы они поддерживали ссылки на внедренные объекты.

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
Поддерживает список элементов OLE, которые находятся в элементе управления Rich Edit. Используется с [CRichEditView](reference/cricheditview-class.md) и [кричедиткнтритем](reference/cricheditcntritem-class.md).

[COleServerDoc](reference/coleserverdoc-class.md)<br/>
Используется в качестве базового класса для классов документов серверного приложения. `COleServerDoc`объекты обеспечивают большую часть поддержки сервера за счет взаимодействия с объектами [COleServerItem](reference/coleserveritem-class.md) . Возможность визуального редактирования предоставляется с помощью архитектуры "документ-представление" библиотеки классов.

[CHtmlEditDoc](reference/chtmleditdoc-class.md)<br/>
Предоставляет с помощью [CHtmlEditView](reference/chtmleditview-class.md)функциональные возможности платформы редактирования HTML WebBrowser в контексте архитектуры представления документов MFC.

## <a name="related-classes"></a>Связанные классы

Объекты классов документов могут быть постоянными — иными словами, они могут записывать свое состояние на носитель и считывать их. MFC предоставляет `CArchive` класс для упрощения передачи данных документа в среду хранения.

[CArchive](reference/carchive-class.md)<br/>
Взаимодействует с объектом [кфиле](reference/cfile-class.md) для реализации постоянного хранилища объектов с помощью сериализации (см. [CObject:: Serialize](reference/cobject-class.md#serialize)).

Документы также могут содержать объекты OLE. `CDocItem`является базовым классом для серверных и клиентских элементов.

[CDocItem](reference/cdocitem-class.md)<br/>
Абстрактный базовый класс [COleClientItem](reference/coleclientitem-class.md) и [COleServerItem](reference/coleserveritem-class.md). Объекты классов, производных от, `CDocItem` представляют части документов.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
