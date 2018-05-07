---
title: Классы контейнера OLE | Документы Microsoft
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
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfdff6023beeedfa14d37e5b404fa3c223691b85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ole-container-classes"></a>Классы контейнера OLE
Эти классы используются приложением-контейнером. Оба `COleLinkingDoc` и `COleDocument` управления наборами `COleClientItem` объектов. Вместо того чтобы наследование класса документов от **CDocument**, вы будете сделайте его производным от `COleLinkingDoc` или `COleDocument`, в зависимости от того, поддержку для ссылок на объекты, внедренные в документе.  
  
 Используйте `COleClientItem` объекта для представления каждого элемента OLE в документе, внедряется из другого документа или ссылку на другой документ.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 Поддерживает хранение активных документов.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Используется для реализации составных документов, а также поддержка основной контейнер. Служит в качестве контейнера для классов, производный от `CDocItem`. Этот класс может использоваться как базовый класс для контейнера, документы и является базовым классом для `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Класс, производный от `COleDocument` , предоставляет инфраструктуру для связывания. Классы документов должен быть производным от этого класса, а не из контейнера приложений `COleDocument` их для поддержки ссылок на внедренные объекты.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Поддерживает список элементов клиента OLE в элемент управления форматированием. При использовании [CRichEditView](../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс для `COleClientItem` и `COleServerItem`. Объекты классов, производных от `CDocItem` представляют частей документов.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Клиентский класс элемент, представляющий подключение к внедренного или связанного элемента OLE на стороне клиента. Производные элементы клиента от этого класса.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Предоставляет клиентский доступ к объект OLE, хранимый в элементе управления rich edit, при использовании с `CRichEditView` и `CRichEditDoc`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключения, возникающие в результате ошибки во время обработки OLE. Этот класс используется, контейнеры и серверы.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

