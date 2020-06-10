---
title: Серверные классы OLE
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 06f5cf0985756506e42c7ad9fde24641b5a0ce93
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619855"
---
# <a name="ole-server-classes"></a>Серверные классы OLE

Эти классы используются серверными приложениями. Серверные документы являются производными от `COleServerDoc` , а не от `CDocument` . Обратите внимание, что, поскольку `COleServerDoc` является производным от `COleLinkingDoc` , серверные документы также могут быть контейнерами, поддерживающими компоновку.

`COleServerItem`Класс представляет документ или часть документа, который может быть внедрен в другой документ или связан с.

`COleIPFrameWnd`и `COleResizeBar` поддерживают редактирование на месте, пока объект находится в контейнере, и `COleTemplateServer` поддерживает создание пар "документ-представление", чтобы можно было изменять объекты OLE из других приложений.

[COleServerDoc](reference/coleserverdoc-class.md)<br/>
Используется в качестве базового класса для классов документов серверного приложения. `COleServerDoc`объекты обеспечивают большую часть поддержки сервера за счет взаимодействия с `COleServerItem` объектами. Возможность визуального редактирования предоставляется с помощью архитектуры "документ-представление" библиотеки классов.

[CDocItem](reference/cdocitem-class.md)<br/>
Абстрактный базовый класс для `COleClientItem` и `COleServerItem` . Объекты классов, производных от, `CDocItem` представляют части документов.

[COleServerItem](reference/coleserveritem-class.md)<br/>
Используется для представления интерфейса OLE `COleServerDoc` элементам. Обычно существует один `COleServerDoc` объект, представляющий внедренную часть документа. В серверах, поддерживающих ссылки на части документов, может быть много `COleServerItem` объектов, каждый из которых представляет ссылку на часть документа.

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
Предоставляет окно фрейма для представления, когда серверный документ редактируется на месте.

[COleResizeBar](reference/coleresizebar-class.md)<br/>
Предоставляет стандартный пользовательский интерфейс для изменения размера на месте. Объекты этого класса всегда используются вместе с `COleIPFrameWnd` объектами.

[COleTemplateServer](reference/coletemplateserver-class.md)<br/>
Используется для создания документов с использованием архитектуры "документ-представление" платформы. `COleTemplateServer`Объект делегирует большую часть своей работы связанному `CDocTemplate` объекту.

[COleException](reference/coleexception-class.md)<br/>
Исключение, полученное при сбое обработки OLE. Этот класс используется как контейнерами, так и серверами.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
