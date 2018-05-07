---
title: Очистка документов и представлений | Документы Microsoft
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
ms.openlocfilehash: 2dfe54c13db6f44bc70289380ae5f50d99c3722b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений
При закрытии документа сначала вызывается платформой его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функции-члена. Если выделить память в куче в процессе операции документа `DeleteContents` — это лучшее место для его освобождения.  
  
> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.  
  
 Можно переопределить деструктор представления для освобождения памяти, размещенных в куче.  
  
## <a name="see-also"></a>См. также  
 [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

