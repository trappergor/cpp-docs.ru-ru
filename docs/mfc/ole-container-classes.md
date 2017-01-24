---
title: "Классы контейнера OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX - классы [C++]"
  - "классы контейнеров [C++]"
  - "контейнеры [C++], OLE - приложения контейнера"
  - "OLE [C++], классы"
  - "классы OLE [C++]"
  - "визуальное редактирование [C++], классы"
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы контейнера OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы используются приложение\-контейнерами.  И `COleLinkingDoc` и `COleDocument` управляют коллекции объектов `COleClientItem`.  Вместо производный класс документа из **CDocument**, выведете его из `COleLinkingDoc` или `COleDocument`, в зависимости от его поддержка ссылок на объекты внедренным в документе.  
  
 Используйте объект `COleClientItem` для представления каждого элемента OLE в документе, внедренного из другого документа или ссылку на другой документ.  
  
 [COleDocObjectItem](../Topic/COleDocObjectItem%20Class.md)  
 Поддерживает контейнер активных документов.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Используется для реализации составной документа, так и базовой поддержки контейнеров.  Служит в качестве контейнера для классов, производных от `CDocItem`.  Этот класс можно использовать в качестве базового класса для документов контейнера и базовый класс для `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 В классе, производном от `COleDocument`, предоставляет инфраструктуру для компоновки.  Необходимо создать классы документа в приложение\-контейнеров от этого класса, а не из `COleDocument` при необходимости их с указателями поддержки к внедренным объекты.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Приводит список элементов OLE клиента, в элементе управления расширенного редактирования.  Используется с [CRichEditView](../mfc/reference/cricheditview-class.md) и [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Абстрактный базовый класс `COleClientItem` и `COleServerItem`.  Объекты классов, производных от `CDocItem` представляют частей документов.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Класс элемента клиента, представляющий сторону клиента подключения к, встроенному или связанный элемент OLE.  Унаследуйте нужный клиентскими от этого класса.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Предоставляет клиентский доступ к элемент OLE, хранящиеся в элементе управления расширенного редактирования при использовании с `CRichEditView` и `CRichEditDoc`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключение и в результате сбоя в OLE обработки.  Этот класс используется как контейнерами, и серверами.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)