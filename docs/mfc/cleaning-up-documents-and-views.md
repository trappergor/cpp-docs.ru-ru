---
title: Очистка документов и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 1357a02379a848af23a6f78dee29e5b6adc1efcc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653901"
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений

При закрытии документа, сначала вызывается метод его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функция-член. Если выделить память в куче в ходе операции с документом, `DeleteContents` лучше всего для его освобождения.

> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.

Вы можете переопределить деструктор представления для освобождения памяти, выделенных в куче.

## <a name="see-also"></a>См. также

[Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

