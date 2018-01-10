---
title: "Использование ползунков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fdab6a7fae25845da81ee7263e045e50951f557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-slider-controls"></a>Использование ползунков
Типичное использование элемента управления "ползунок" соответствует шаблону ниже:  
  
-   Элемент управления создается. Если элемент управления, заданный в шаблон диалогового окна, создание выполняется автоматически при создании диалоговым окном. (Вы должны иметь [CSliderCtrl](../mfc/reference/csliderctrl-class.md) члена в классе диалоговое окно, соответствующее элементу управления "ползунок".) Кроме того, можно использовать [создать](../mfc/reference/csliderctrl-class.md#create) функции-члена для создания элемента управления как дочернего окна любого окна.  
  
-   Вызывайте различные функции-члены набор для установки значений для элемента управления. Изменения, выполненные включают Задание минимального и максимального позиции для ползунок, рисование делений, задание диапазон выбора и положения ползунка. Для элементов управления в диалоговом окне — подходящее время для этого в диалоговом окне [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) функции.  
  
-   Как пользователь взаимодействует с элементом управления, он передает различные сообщения уведомления. Можно извлечь значение ползунка из элемента управления путем вызова [GetPos](../mfc/reference/csliderctrl-class.md#getpos) функции-члена.  
  
-   После завершения с помощью элемента управления необходимо убедитесь в том, что он правильно удален. Если элемент управления "ползунок" в диалоговом окне, его и `CSliderCtrl` объект будет удален автоматически. Если нет, необходимо убедиться, что оба элемента управления и `CSliderCtrl` правильно удаляется объект.  
  
## <a name="see-also"></a>См. также  
 [Использование CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

