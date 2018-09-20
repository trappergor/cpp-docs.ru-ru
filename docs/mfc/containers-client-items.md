---
title: 'Контейнеры: Элементы клиентов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae9a37aaeb9df3241cf48d3fc62db046682a7a1b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387072"
---
# <a name="containers-client-items"></a>Контейнеры. Элементы клиентов

В этой статье объясняются клиентские элементы и из классов, что приложения должны наследовать его клиентские элементы.

Клиентские элементы являются элементами данных, принадлежащих другого приложения, которые могут быть содержащиеся в или ссылается документ приложения контейнера OLE. Внедренные элементы клиента, данные которого содержится в документе; те, данные которых хранятся в другом месте, ссылается документе-контейнере связаны.

Класс документа в приложении OLE является производным от класса [COleDocument](../mfc/reference/coledocument-class.md) , а не из `CDocument`. `COleDocument` Класс наследует от `CDocument` все функциональные возможности, необходимые для использования архитектуры document/view, на какие MFC основаны приложения. `COleDocument` также определяет интерфейс, который обрабатывает документ как коллекция `CDocItem` объектов. Несколько `COleDocument` функций-членов предоставляются для добавления, получения и удаления элементов этой коллекции.

Каждый контейнер должен быть производным по крайней мере один класс из `COleClientItem`. Объекты этого класса представляют элементы, внедренные или связанные, в документе OLE. Эти объекты существуют в течение жизненного цикла документа, содержащего их, если они не удалены из документа.

`CDocItem` является базовым классом для `COleClientItem` и `COleServerItem`. Объекты классов, производных от этих двух выступают в качестве посредников между объекта OLE и клиентские и серверные приложения, соответственно. Каждый раз, в документ добавляется новый элемент OLE платформы MFC добавляет новый объект приложения клиента `COleClientItem`-производный класс документа коллекцию `CDocItem` объектов.

## <a name="see-also"></a>См. также

[Контейнеры](../mfc/containers.md)<br/>
[Контейнеры. Составные файлы](../mfc/containers-compound-files.md)<br/>
[Контейнеры. Проблемы пользовательского интерфейса](../mfc/containers-user-interface-issues.md)<br/>
[Контейнеры. Дополнительные возможности](../mfc/containers-advanced-features.md)<br/>
[Класс COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerItem](../mfc/reference/coleserveritem-class.md)
