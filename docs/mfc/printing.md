---
title: "Печать | Документы Microsoft"
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
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01ee396a7866179bd140f203192d1bdcbfb4681e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="printing"></a>Печать
Microsoft Windows реализует аппаратно независимые отображения. В MFC, это означает, что же вызовов рисования, в `OnDraw` функции-члена класса представления, отвечают за рисования на экране и на других устройствах, таких как принтеры. Для предварительного просмотра целевое устройство является имитацию печати с отображением.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>Роль в печати и роль платформы  
 Представление класса должен выполнить следующие действия:  
  
-   Сообщите платформе, сколько страниц в документе.  
  
-   При запросе на печать указанную страницу, нарисуйте часть документа.  
  
-   Выделять и освобождать все шрифты, или другие графики устройства интерфейс (GDI) ресурсы, необходимые для печати.  
  
-   При необходимости отправлять все escape-кодами изменить режим принтера перед печатью данной странице, например, изменение ориентации на уровне страниц.  
  
 Обязанности framework выглядят следующим образом:  
  
-   Отображение **печати** диалоговое окно.  
  
-   Создание [CDC](../mfc/reference/cdc-class.md) объекта для принтера.  
  
-   Вызовите [StartDoc](../mfc/reference/cdc-class.md#startdoc) и [EndDoc](../mfc/reference/cdc-class.md#enddoc) функциями-членами `CDC` объекта.  
  
-   Несколько раз вызвать [StartPage](../mfc/reference/cdc-class.md#startpage) функцию-член `CDC` объекта информирования класс представления, какие страницы следует печатать, а также вызвать [EndPage](../mfc/reference/cdc-class.md#endpage) функцию-член `CDC` объекта.  
  
-   Вызов переопределяемые функции в представлении в нужное время.  
  
 Следующие статьи описывается, как платформа поддерживает печать и предварительный просмотр.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [По умолчанию печать](../mfc/how-default-printing-is-done.md)  
  
-   [Многостраничные документы](../mfc/multipage-documents.md)  
  
-   [Верхние и нижние колонтитулы](../mfc/headers-and-footers.md)  
  
-   [Выделение ресурсов GDI для печати](../mfc/allocating-gdi-resources.md)  
  
-   [Предварительный просмотр](../mfc/print-preview-architecture.md)  
  
## <a name="see-also"></a>См. также  
 [Печать и предварительный просмотр печати](../mfc/printing-and-print-preview.md)

