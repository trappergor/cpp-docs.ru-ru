---
title: Очистка документов и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 940c768823d26950d9710fb1d1a52e6a1955fead
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258818"
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений

При закрытии документа, сначала вызывается метод его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функция-член. Если выделить память в куче в ходе операции с документом, `DeleteContents` лучше всего для его освобождения.

> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.

Вы можете переопределить деструктор представления для освобождения памяти, выделенных в куче.

## <a name="see-also"></a>См. также

[Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)
