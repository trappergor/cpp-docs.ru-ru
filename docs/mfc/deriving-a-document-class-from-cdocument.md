---
title: Наследование класса документов от CDocument | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81f3c3a36f049e3f47401efa31b36677b3b9ba6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931753"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Наследование класса документов от CDocument
Документы содержат и управления данными приложения. Чтобы использовать класс заданное мастер приложений MFC, необходимо выполнить следующие задачи:  
  
-   Производный класс `CDocument` для каждого типа документа.  
  
-   Добавьте переменные-члены для хранения данных каждого документа.  
  
-   Переопределить `CDocument` `Serialize` функции-члена в классе документа. `Serialize` для записи и чтения данных документа на диск и обратно.  
  
## <a name="other-document-functions-often-overridden"></a>Часто переопределяемые функции других документов  
 Можно также переопределить других `CDocument` функции-члены. В частности, часто требуется переопределить [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) и [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) в инициализации членов данных документа и [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) для уничтожения динамически выделенные данные. Сведения о переопределяемые члены см. класс [CDocument](../mfc/reference/cdocument-class.md) в *Справочник по библиотеке MFC*.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

