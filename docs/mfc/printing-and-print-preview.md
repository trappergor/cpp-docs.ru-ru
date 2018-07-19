---
title: Печать и предварительный просмотр | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a26bac196dbddc6c05df5850225d05f432bc566
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346260"
---
# <a name="printing-and-print-preview"></a>Печать и предварительный просмотр печати
MFC поддерживает печать и предварительный просмотр для документов программы через класс [CView](../mfc/reference/cview-class.md). Для основных печати и предварительного просмотра, просто переопределить класс представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функции-члена, которого необходимо выполнить в любом случае. Этой функции можно создать представление на экране на контекст устройства принтера для фактического принтера или контекста устройства, имитирует принтера на экране.  
  
 Кроме того, можно добавить код для управления печать многостраничных документов и предварительного просмотра, разбиения по страницам, печатаемых документов и добавлять в них верхние и нижние колонтитулы.  
  
 Этот сборник статей описание реализации библиотеки классов Microsoft Foundation (MFC) печати и использовать преимущества архитектуры печати уже встроены в платформу. Статьи также объясняется, как MFC поддерживает простая реализация функции предварительного просмотра и как можно использовать и изменять эти функциональные возможности.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Печать](../mfc/printing.md)  
  
-   [Архитектура предварительного просмотра](../mfc/print-preview-architecture.md)  
  
-   [Пример](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
