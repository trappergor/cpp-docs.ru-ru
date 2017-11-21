---
title: "Очистка документов и представлений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f9bb1cbcb58e2693b33693b390a09d3826c77cfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cleaning-up-documents-and-views"></a>Очистка документов и представлений
При закрытии документа сначала вызывается платформой его [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) функции-члена. Если выделить память в куче в процессе операции документа `DeleteContents` — это лучшее место для его освобождения.  
  
> [!NOTE]
>  Не следует освобождать данные документа в деструкторе документа. В случае приложения SDI объект документа может быть использован.  
  
 Можно переопределить деструктор представления для освобождения памяти, размещенных в куче.  
  
## <a name="see-also"></a>См. также  
 [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

