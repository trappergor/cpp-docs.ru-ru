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
ms.openlocfilehash: 698957d4e307ad1f099d5aef7de131c538ee4871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342622"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Наследование класса документов от CDocument
Документы содержат и управления данными приложения. Чтобы использовать класс заданное мастер приложений MFC, необходимо выполнить следующие задачи:  
  
-   Производный класс **CDocument** для каждого типа документа.  
  
-   Добавьте переменные-члены для хранения данных каждого документа.  
  
-   Переопределить **CDocument** `Serialize` функции-члена в классе документа. `Serialize` для записи и чтения данных документа на диск и обратно.  
  
## <a name="other-document-functions-often-overridden"></a>Часто переопределяемые функции других документов  
 Можно также переопределить других **CDocument** функции-члены. В частности, часто требуется переопределить [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) и [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) в инициализации членов данных документа и [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) для уничтожения динамически выделенные данные. Сведения о переопределяемые члены см. класс [CDocument](../mfc/reference/cdocument-class.md) в *Справочник по библиотеке MFC*.  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

