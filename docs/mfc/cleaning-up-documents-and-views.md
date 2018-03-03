---
title: "Очистка документов и представлений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений
При закрытии документа сначала вызывается платформой его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функции-члена. Если выделить память в куче в процессе операции документа `DeleteContents` — это лучшее место для его освобождения.  
  
> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.  
  
 Можно переопределить деструктор представления для освобождения памяти, размещенных в куче.  
  
## <a name="see-also"></a>См. также  
 [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

