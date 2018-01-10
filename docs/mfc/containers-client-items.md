---
title: "Контейнеры: Клиентские элементы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa80911ff14d329dc483cd6497393c6c5595ef2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-items"></a>Контейнеры. Элементы клиентов
В этой статье описаны клиентские элементы и в том, что классы приложения должны наследовать его клиентские элементы.  
  
 Клиентские элементы являются элементами данных из другого приложения, которые содержатся в или производится ссылается документ приложение контейнера OLE. Внедренные элементы клиента, данные, содержащиеся в документе; те, данные которой хранятся в другом месте ссылается документе-контейнере являются связанными.  
  
 Класс документа в приложении OLE является производным от класса [COleDocument](../mfc/reference/coledocument-class.md) , а не из **CDocument**. `COleDocument` Класс наследует от **CDocument** все функциональные возможности, необходимые для использования архитектуры document/view, на какие MFC на базе приложений. `COleDocument`также определяет интерфейс, который обрабатывает документа как коллекцию `CDocItem` объектов. Несколько `COleDocument` функций-членов предоставляются для добавления, получение и удаление элементов из этой коллекции.  
  
 Каждое приложение контейнера должны наследовать класс по крайней мере один из `COleClientItem`. Объекты этого класса представляют элементы, внедренные или связанные, в документе OLE. Эти объекты существуют в течение жизненного цикла документа, содержащего их, если они не удалены из документа.  
  
 `CDocItem`является базовым классом для `COleClientItem` и `COleServerItem`. Объекты классов, производных от этих двух выступают в качестве посредников между объекта OLE и клиентские и серверные приложения, соответственно. Каждый раз, в документ добавляется новый элемент OLE платформы MFC добавляет новый объект приложения клиента `COleClientItem`-производного класса к коллекции документа из `CDocItem` объектов.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры](../mfc/containers.md)   
 [Контейнеры: Составные файлы](../mfc/containers-compound-files.md)   
 [Контейнеры: Проблемы пользовательского интерфейса](../mfc/containers-user-interface-issues.md)   
 [Контейнеры: Дополнительные возможности](../mfc/containers-advanced-features.md)   
 [Класс COleClientItem](../mfc/reference/coleclientitem-class.md)   
 [Класс COleServerItem](../mfc/reference/coleserveritem-class.md)
