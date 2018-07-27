---
title: Документирование и просмотреть классы, созданные с помощью мастера приложений MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b83886784970492da0c5e2a335dbe08119ecaae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349926"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Классы документов и представлений, создаваемые с помощью Мастера приложений MFC
Мастер приложений MFC позволяет начать на вашей разработки программ путем создания классы базовой документов и представлений автоматически. После этого можно [сопоставить эти классы команд и сообщений](../mfc/reference/mapping-messages-to-functions.md) и использовать редактор исходного кода Visual C++ для написания функций-членов.  
  
 Класс документа, созданные с помощью мастера приложений MFC, производный от класса [CDocument](../mfc/reference/cdocument-class.md). Класс представления является производным от [CView](../mfc/reference/cview-class.md). Имена, мастер приложений предоставляет эти классы и файлы, которые содержат основаны на имени проекта, укажите в диалоговом окне мастера приложений. В мастере приложений можно использовать классы, создаваемые страницы для изменения имен по умолчанию.  
  
 Для некоторых приложений может потребоваться более одного класса документа, представление или класс окна фрейма. Дополнительные сведения см. в разделе [несколько типов документов, представлений и фреймов](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)

