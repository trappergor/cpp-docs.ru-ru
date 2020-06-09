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
ms.openlocfilehash: 399230446977636cc8769efe32b8f86fad466b83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616114"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Наследование класса документов от CDocument

Документы содержат данные вашего приложения и управляют ими. Чтобы использовать класс документов, предоставляемый мастером приложений MFC, необходимо выполнить следующие действия.

- Создайте класс, производный от, `CDocument` для каждого типа документа.

- Добавьте переменные члена для хранения данных каждого документа.

- Переопределение `CDocument` `Serialize` функции члена в классе документа. `Serialize`записывает и считывает данные документа на диск и обратно.

## <a name="other-document-functions-often-overridden"></a>Другие функции документов, которые часто переопределяются

Также может потребоваться переопределить другие `CDocument` функции элементов. В частности, часто требуется переопределить [онневдокумент](reference/cdocument-class.md#onnewdocument) и [OnOpenDocument](reference/cdocument-class.md#onopendocument) для инициализации элементов данных документа и [делетеконтентс](reference/cdocument-class.md#deletecontents) для уничтожения динамически выделяемых данных. Дополнительные сведения о переопределяемых членах см. в разделе класс [CDocument](reference/cdocument-class.md) в *справочнике по MFC*.

## <a name="see-also"></a>См. также раздел

[Использование документов](using-documents.md)
