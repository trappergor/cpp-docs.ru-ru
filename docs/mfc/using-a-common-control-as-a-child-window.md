---
title: "С помощью стандартного элемента управления как дочернего окна | Документы Microsoft"
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
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475c769bf09c0693c04780712b85884ae7c48862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-common-control-as-a-child-window"></a>Использование общего элемента управления как дочернего окна
Общие элементы управления Windows можно использовать как дочернего окна из других окон. Следующая процедура описывает, как для динамического создания стандартного элемента управления и затем работать с ними.  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>Для использования стандартного элемента управления как дочернего окна  
  
1.  Определение элемента управления в связанный класс или обработчик.  
  
2.  Используйте элемент управления переопределением [CWnd::Create](../mfc/reference/cwnd-class.md#create) метод для создания элемента управления Windows.  
  
3.  После создания элемента управления (уже в `OnCreate` обработчик Если подкласса элемента управления), можно управлять с помощью функции-члены элемента управления. См. в описаниях отдельных элементов управления в [элементов управления](../mfc/controls-mfc.md) подробные сведения о методах.  
  
4.  По окончании работы с элементом управления использовать [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) уничтожение элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Создание и использование элементов управления](../mfc/making-and-using-controls.md)   
 [Элементы управления](../mfc/controls-mfc.md)

