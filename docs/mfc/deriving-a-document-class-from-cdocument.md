---
title: Наследование класса документов от CDocument
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 5998d5707eb741be0e8ac270f6ac5ce77a9ff8d8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272065"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Наследование класса документов от CDocument

Документы содержат данные и управляйте ими приложения. Использование класса документа, предоставляемую мастер приложений MFC, выполните следующие действия.

- Наследуйте класс от `CDocument` для каждого типа документа.

- Добавьте переменные-члены для хранения данных каждого документа.

- Переопределить `CDocument`в `Serialize` функции-члена в классе документа. `Serialize` Записывает и читает данные документа и с диска.

## <a name="other-document-functions-often-overridden"></a>Часто переопределяемые функции других документов

Можно также переопределить другие `CDocument` функций-членов. В частности, часто требуется переопределить [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) и [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) в инициализации членов данных документа и [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) для уничтожения динамически выделенные данные. Сведения о переопределяемые члены, см. в разделе класса [CDocument](../mfc/reference/cdocument-class.md) в *Справочник по библиотеке MFC*.

## <a name="see-also"></a>См. также

[Использование документов](../mfc/using-documents.md)
