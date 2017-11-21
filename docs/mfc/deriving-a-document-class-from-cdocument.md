---
title: "Наследование класса документов от CDocument | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8f9152384522725dc932d0ce5e1c4cc81827160b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="deriving-a-document-class-from-cdocument"></a>Наследование класса документов от CDocument
Документы содержат и управления данными приложения. Чтобы использовать класс заданное мастер приложений MFC, необходимо выполнить следующие задачи:  
  
-   Производный класс **CDocument** для каждого типа документа.  
  
-   Добавьте переменные-члены для хранения данных каждого документа.  
  
-   Переопределить **CDocument** `Serialize` функции-члена в классе документа. `Serialize`для записи и чтения данных документа на диск и обратно.  
  
## <a name="other-document-functions-often-overridden"></a>Часто переопределяемые функции других документов  
 Можно также переопределить других **CDocument** функции-члены. В частности, часто требуется переопределить [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) и [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) в инициализации членов данных документа и [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) для уничтожения динамически выделенные данные. Сведения о переопределяемые члены см. класс [CDocument](../mfc/reference/cdocument-class.md) в *Справочник по библиотеке MFC*.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

