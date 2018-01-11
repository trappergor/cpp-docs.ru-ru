---
title: "Классы документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.document
dev_langs: C++
helpviewer_keywords: document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a2436b46b7486bd30398dffc530d2adea3d2e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="document-classes"></a>Классы документов
Объекты класса документа, созданные объекты шаблон документа, управления данными приложения. Класс будет наследовать для документов из одного из этих классов.  
  
 Объекты класса документа взаимодействовать с объектами представления. Просмотр объектов представляют клиентской области окна, отображения данных документа и разрешить пользователям взаимодействовать с ним. Документы и представления создаются с помощью объекта шаблона документа.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 Базовый класс для документов конкретного приложения. Является производным класса документа или классы из **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Используется для реализации составных документов, а также поддержка основной контейнер. Служит в качестве контейнера для классов, производный от [CDocItem](../mfc/reference/cdocitem-class.md). Этот класс может использоваться как базовый класс для контейнера, документы и является базовым классом для `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Класс, производный от `COleDocument` , предоставляет инфраструктуру для связывания. Классы документов должен быть производным от этого класса, а не из контейнера приложений `COleDocument` их для поддержки ссылок на внедренные объекты.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Поддерживает список элементов клиента OLE в элемент управления форматированием. При использовании [CRichEditView](../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Используется как базовый класс для классов документа серверного приложения. `COleServerDoc`объекты предоставляют большую часть поддержка сервера при взаимодействии с [COleServerItem](../mfc/reference/coleserveritem-class.md) объектов. Возможности Visual изменения обеспечивается с помощью архитектуры document/view библиотеки классов.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Предоставляет, с [CHtmlEditView](../mfc/reference/chtmleditview-class.md), функции платформы редактирования WebBrowser HTML в контексте архитектуры представления документов MFC.  
  
## <a name="related-classes"></a>Связанные классы  
 Объекты класса документа может быть постоянным — другими словами, записать свое состояние на носителе и их чтения. MFC предоставляет `CArchive` класс для упрощения передачи данных документа на носителе.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 Взаимодействует с [CFile](../mfc/reference/cfile-class.md) объекта для реализации постоянного хранилища для объектов с помощью сериализации (см. [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 Документы могут также содержать объекты OLE. `CDocItem`является базовым классом для элементов сервера и клиента.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс для [COleClientItem](../mfc/reference/coleclientitem-class.md) и [COleServerItem](../mfc/reference/coleserveritem-class.md). Объекты классов, производных от `CDocItem` представляют частей документов.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

