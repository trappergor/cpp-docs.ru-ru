---
title: "Классы документов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.document"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы документов"
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Классы документов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объекты класса документа, создаваемые объектами шаблона документа, работают с данными приложения.  При выведете класс для создания документов из одного из этих классов.  
  
 Объекты класса документа взаимодействуют с объектами представления.  Объекты представления представляют клиентской области окна, отображают данные документа и позволяют пользователям взаимодействовать с ними.  Документы и представления создаются объектом шаблона документа.  
  
 [CDocument](../Topic/CDocument%20Class.md)  
 Базовый класс для специфичных для приложения.  Унаследуйте нужный класс документа или классы из **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Используется для реализации составной документа, так и базовой поддержки контейнеров.  Служит в качестве контейнера для классов, производных от [CDocItem](../mfc/reference/cdocitem-class.md).  Этот класс можно использовать в качестве базового класса для документов контейнера и базовый класс для `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 В классе, производном от `COleDocument`, предоставляет инфраструктуру для компоновки.  Необходимо создать классы документа в приложение\-контейнеров от этого класса, а не из `COleDocument` при необходимости их с указателями поддержки к внедренным объекты.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Приводит список элементов OLE клиента, в элементе управления расширенного редактирования.  Используется с [CRichEditView](../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
 Используется как базовый класс для классов документа серверного приложения.  объекты `COleServerDoc` предоставляют пакетную поддержки сервера посредством взаимодействия с объектами [COleServerItem](../mfc/reference/coleserveritem-class.md).  Предоставляется возможность визуального редактирования с использованием архитектуры документов и представлений библиотеки классов.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Предоставляет с [CHtmlEditView](../mfc/reference/chtmleditview-class.md), при редактировании HTML браузера платформа в контексте представления архитектуры документов MFC.  
  
## Связанные классы  
 Объекты класса документа могут быть постоянными \(другими словами, они могут записывать их состояния к носителю записи и чтения его.  MFC предоставляет классы `CArchive` для упрощения переноса данных по документа к носителю записи.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 Сотрудничает с объектом [CFile](../mfc/reference/cfile-class.md) для реализации постоянное хранилище для объектов с помощью сериализации \(см. [CObject::Serialize](../Topic/CObject::Serialize.md)\).  
  
 Документы могут также содержать объекты OLE.  `CDocItem` базовый класс элементов сервера и клиента.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс [COleClientItem](../mfc/reference/coleclientitem-class.md) и [COleServerItem](../mfc/reference/coleserveritem-class.md).  Объекты классов, производных от `CDocItem` представляют частей документов.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)