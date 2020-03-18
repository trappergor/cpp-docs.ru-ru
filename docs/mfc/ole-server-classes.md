---
title: Серверные классы OLE
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
ms.openlocfilehash: 92dec514611dcce7d6c666fdd271843e69561637
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447589"
---
# <a name="ole-server-classes"></a>Серверные классы OLE

Эти классы используются серверными приложениями. Серверные документы являются производными от `COleServerDoc`, а не от `CDocument`. Обратите внимание, что поскольку `COleServerDoc` является производной от `COleLinkingDoc`, серверные документы также могут быть контейнерами, поддерживающими компоновку.

Класс `COleServerItem` представляет документ или часть документа, который можно внедрить в другой документ или связать с.

`COleIPFrameWnd` и `COleResizeBar` поддерживают редактирование на месте, пока объект находится в контейнере, и `COleTemplateServer` поддерживает создание пар "документ-представление", чтобы можно было изменять объекты OLE из других приложений.

[колесервердок](../mfc/reference/coleserverdoc-class.md)<br/>
Используется в качестве базового класса для классов документов серверного приложения. `COleServerDoc` объекты обеспечивают большую часть поддержки сервера за счет взаимодействия с `COleServerItem` объектами. Возможность визуального редактирования предоставляется с помощью архитектуры "документ-представление" библиотеки классов.

[кдоЦитем](../mfc/reference/cdocitem-class.md)<br/>
Абстрактный базовый класс `COleClientItem` и `COleServerItem`. Объекты классов, производных от `CDocItem`, представляют части документов.

[COleServerItem](../mfc/reference/coleserveritem-class.md)<br/>
Используется для представления интерфейса OLE для `COleServerDoc` элементов. Обычно существует один объект `COleServerDoc`, представляющий внедренную часть документа. В серверах, поддерживающих ссылки на части документов, может быть несколько `COleServerItem` объектов, каждый из которых представляет ссылку на часть документа.

[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)<br/>
Предоставляет окно фрейма для представления, когда серверный документ редактируется на месте.

[колересизебар](../mfc/reference/coleresizebar-class.md)<br/>
Предоставляет стандартный пользовательский интерфейс для изменения размера на месте. Объекты этого класса всегда используются вместе с объектами `COleIPFrameWnd`.

[COleTemplateServer](../mfc/reference/coletemplateserver-class.md)<br/>
Используется для создания документов с использованием архитектуры "документ-представление" платформы. Объект `COleTemplateServer` делегирует большую часть работы связанному объекту `CDocTemplate`.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Исключение, полученное при сбое обработки OLE. Этот класс используется как контейнерами, так и серверами.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
