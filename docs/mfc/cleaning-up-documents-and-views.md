---
title: Очистка документов и представлений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4325b0de10861fc76ee9ab816376f40ba0ba587
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437421"
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений

При закрытии документа, сначала вызывается метод его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функция-член. Если выделить память в куче в ходе операции с документом, `DeleteContents` лучше всего для его освобождения.

> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.

Вы можете переопределить деструктор представления для освобождения памяти, выделенных в куче.

## <a name="see-also"></a>См. также

[Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

