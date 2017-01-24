---
title: "Наследование класса документов от CDocument | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocument - класс, производное из"
  - "классы [C++], производное из CDocument"
  - "производные классы, часто переопределяемые функции"
  - "классы документов, часто переопределяемые функции"
  - "объекты документа, производные"
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Наследование класса документов от CDocument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит документы и управляют данные приложения.  Для использования приложения MFC мастером поставил класс документа необходимо выполнить следующие действия:  
  
-   Унаследуйте класс от **CDocument** для каждого типа документа.  
  
-   Добавьте переменные\-члены для хранения данных каждого документа.  
  
-   Функцию\-член **CDocument**`Serialize` переопределения в классе документа.  `Serialize` записи и считывает данные документа на диск и с диска.  
  
## Другие часто переопределяемые функции документа  
 Кроме того, можно переопределить другие функции\-члены **CDocument**.  В частности, зачастую требуется переопределить [OnNewDocument](../Topic/CDocument::OnNewDocument.md) и [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) для инициализации элементов данных и [DeleteContents](../Topic/CDocument::DeleteContents.md) документа для удаления динамически размещенные данные.  Сведения о членах переопределяемого метода см. в описании класса [CDocument](../Topic/CDocument%20Class.md) в *справочнике по MFC*.  
  
## См. также  
 [Использование документов](../mfc/using-documents.md)