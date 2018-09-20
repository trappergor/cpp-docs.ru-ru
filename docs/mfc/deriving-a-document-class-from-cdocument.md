---
title: Наследование класса документов от CDocument | Документация Майкрософт
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
ms.openlocfilehash: b45dadbc062bbba61cdcb4c883f91943b1b18ba8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429829"
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

