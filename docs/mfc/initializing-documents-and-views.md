---
title: "Инициализация документов и представлений | Документы Microsoft"
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
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f80d870f9804454dc652fdda00f34fcdb7a52062
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-documents-and-views"></a>Инициализация документов и представлений
Класс документа должна поддерживать оба способа двумя различными способами, создании документов. Во-первых пользователь может создавать новый, пустой документ с помощью команды создания файла. В этом случае инициализации документа в переопределении [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) функции-члена класса [CDocument](../mfc/reference/cdocument-class.md). Во-вторых пользователя можно использовать команду «Открыть» в меню «файл» для создания нового документа, содержимое которого считываются из файла. В этом случае инициализации документа в переопределении [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) функции-члена класса **CDocument**. Если оба инициализаций совпадают, можно вызывать из обеих переопределенных общие функции-члена или `OnOpenDocument` можно вызвать `OnNewDocument` для инициализации чистой документа, а затем завершить операции открытия.  
  
 Представления создаются после создания своих документов. Самое подходящее время для инициализации представления — после создания документа, окно фрейма и представления платформы. Представление можно инициализировать путем переопределения [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функцию-член [CView](../mfc/reference/cview-class.md). Если необходимо повторно инициализировать или настройки каждый раз при изменении документа, можно переопределить [OnUpdate](../mfc/reference/cview-class.md#onupdate).  
  
## <a name="see-also"></a>См. также  
 [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

