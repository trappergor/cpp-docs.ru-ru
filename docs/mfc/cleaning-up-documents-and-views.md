---
title: Очистка документов и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 8cb6e9337b69daf78286f57898c9badf513c7921
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626527"
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений

При закрытии документа платформа сначала вызывает свою функцию-член [делетеконтентс](reference/cdocument-class.md#deletecontents) . Если в куче во время операции с документом выделена какая-либо память, `DeleteContents` лучше всего ее освободить.

> [!NOTE]
> Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован повторно.

Можно переопределить деструктор представления, чтобы освободить память, выделенную в куче.

## <a name="see-also"></a>См. также раздел

[Инициализация и очистка документов и представлений](initializing-and-cleaning-up-documents-and-views.md)
