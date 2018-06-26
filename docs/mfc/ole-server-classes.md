---
title: Серверные классы OLE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9d0c75325c62a92f65c56f2c76350bf752228fd
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932225"
---
# <a name="ole-server-classes"></a>Серверные классы OLE
Эти классы используются серверными приложениями. Серверные документы являются производными от `COleServerDoc` , а не из `CDocument`. Обратите внимание, что поскольку `COleServerDoc` является производным от `COleLinkingDoc`, документы сервера также могут быть контейнеры, которые поддерживают связывание.  
  
 `COleServerItem` Класс представляет документ или фрагмент документа, могут быть внедрены в другом документе или связанные.  
  
 `COleIPFrameWnd` и `COleResizeBar` поддерживает редактирование на месте, пока объект находится в контейнере, и `COleTemplateServer` поддерживает создание пары "документ представление", можно изменить OLE-объекты из других приложений.  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Используется как базовый класс для классов документа серверного приложения. `COleServerDoc` объекты предоставляют большую часть поддержка сервера при взаимодействии с `COleServerItem` объектов. Возможности Visual изменения обеспечивается с помощью архитектуры document/view библиотеки классов.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс для `COleClientItem` и `COleServerItem`. Объекты классов, производных от `CDocItem` представляют частей документов.  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 Используется для представления интерфейса OLE `COleServerDoc` элементов. Он обычно `COleServerDoc` объект, представляющий внедренный части документа. На серверах, поддерживающих ссылки на части документов, может быть много `COleServerItem` объектов, каждый из которых представляет ссылку на часть документа.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Предоставляет окна фрейма для представления, когда серверный документ изменяется на месте.  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 Предоставляет стандартный пользовательский интерфейс для изменения размера на месте. Объекты этого класса всегда используются совместно с `COleIPFrameWnd` объектов.  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 Используется для создания документов с помощью архитектуры document/view framework. Объект `COleTemplateServer` объект делегирует большая часть его работы для связанных `CDocTemplate` объекта.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключения, возникающие в результате ошибки во время обработки OLE. Этот класс используется, контейнеры и серверы.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

