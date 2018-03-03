---
title: "Печать и предварительный просмотр | Документы Microsoft"
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
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bedcf1ecf851ed6d9dd396ee6a82d6d2c058930b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
