---
title: "Верхние и нижние колонтитулы | Документы Microsoft"
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
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7525cba7d05c4d04f0548bd2dc774503b284c220
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="headers-and-footers"></a>Верхние и нижние колонтитулы
В этой статье объясняется, как добавление верхних и нижних колонтитулов в печатном документе.  
  
 При просмотре документа на экране, в строку заголовка и строку состояния обычно отображается имя документа и текущего расположения в документе. При просмотре печатной копии документа, полезно иметь имя и номер страницы в верхнем или нижнем колонтитуле. Это чаще всего, в которой WYSIWYG даже программы отличаются в том, как выполнять печать и отображения на экране.  
  
 [OnPrint](../mfc/reference/cview-class.md#onprint) функция-член является лучшее место для печати верхние и нижние колонтитулы, так как он вызывается для каждой страницы, а так как он вызывается только для печати, а не для отображения на экране. Можно определить отдельную функцию, чтобы распечатать верхний или нижний колонтитул и передать его в контекст устройства принтера из `OnPrint`. Может потребоваться внести корректировки в окне источника или экстент перед вызовом [OnDraw](../mfc/reference/cview-class.md#ondraw) избежать текст страницы перекрытие верхний или нижний колонтитул. Может потребоваться изменить `OnDraw` так, как объем документа, который отвечает на странице могла быть уменьшена.  
  
 Один из способов компенсации для области, занятые верхний или нижний колонтитул является использование **m_rectDraw** членом [CPrintInfo](../mfc/reference/cprintinfo-structure.md). Каждый раз, когда печати страницы, этот член инициализируется можно использовать области страницы. Если печать верхний или нижний колонтитул перед печатью основной области страницы, можно уменьшить размер прямоугольника, хранящиеся в **m_rectDraw** с учетом области, занятые верхний или нижний колонтитул. Затем `OnPrint` могут ссылаться на **m_rectDraw** чтобы узнать, сколько область остается для печати основной области страницы.  
  
 Не удается выполнить печать заголовка и любые другие элементы, из [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc), так как он вызывается перед `StartPage` функцию-член [CDC](../mfc/reference/cdc-class.md) был вызван. На этом этапе контекста принтера считается по границе страницы. Можно выполнять печать только из `OnPrint` функции-члена.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Печать многостраничных документов](../mfc/multipage-documents.md)  
  
-   [Выделение ресурсов GDI для печати](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>См. также  
 [Печать](../mfc/printing.md)

