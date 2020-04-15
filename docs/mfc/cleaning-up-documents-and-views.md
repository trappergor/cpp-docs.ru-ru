---
title: Очистка документов и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 06ff60a2cf6245f64e80d899c13a8444558fcf0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374618"
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений

При закрытии документа платформа сначала вызывает функцию члена [DeleteContents.](../mfc/reference/cdocument-class.md#deletecontents) Если вы выделили какую-либо память на куче `DeleteContents` в ходе работы документа, это лучшее место, чтобы разложить его.

> [!NOTE]
> Не следует распределять данные документов в деструктора документа. В случае применения SDI объект документа может быть использован повторно.

Можно переопределить деструктор представления, чтобы распределить любую память, выделенную на куче.

## <a name="see-also"></a>См. также раздел

[Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)
