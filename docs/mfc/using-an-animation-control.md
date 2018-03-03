---
title: "С помощью управления \"анимация\" | Документы Microsoft"
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
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38523c832f4a30f247bd3e1d0b8318f44f5c47b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-animation-control"></a>Использование элемента управления "Анимация"
Типичное использование элемента управления "анимация" соответствует шаблону ниже:  
  
-   Элемент управления создается. Если элемент управления, заданный в шаблон диалогового окна, создание выполняется автоматически при создании диалоговым окном. (Вы должны иметь [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) член в класс, соответствующий управления "анимация" диалогового окна.) Кроме того, можно использовать [создать](../mfc/reference/canimatectrl-class.md#create) функции-члена для создания элемента управления как дочернего окна любого окна.  
  
-   Загрузка AVI-clip управления "анимация" путем вызова [откройте](../mfc/reference/canimatectrl-class.md#open) функции-члена. Если в диалоговом окне управления "анимация", лучше всего сделать это находится в класс диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) функции.  
  
-   Воспроизведение путем вызова [воспроизведение](../mfc/reference/canimatectrl-class.md#play) функции-члена. Если в диалоговом окне управления "анимация", лучше всего сделать это находится в класс диалогового окна **OnInitDialog** функции. Вызов **воспроизведение** не является обязательным, если для элемента управления анимации `ACS_AUTOPLAY` стиля набора.  
  
-   Если вы хотите отобразить части картинки или воспроизвести ее использование фреймов, `Seek` функции-члена. Чтобы остановить клип воспроизводимого, используйте `Stop` функции-члена.  
  
-   Если вы не собираетесь немедленно удалить элемент управления, удаляет клип из памяти посредством вызова **закрыть** функции-члена.  
  
-   Если элемент управления анимации в диалоговом окне, его и `CAnimateCtrl` объект будет удален автоматически. Если нет, необходимо убедиться, что оба элемента управления и `CAnimateCtrl` правильно удаляется объект. Уничтожение элемента управления автоматически закрывает AVI-clip.  
  
## <a name="see-also"></a>См. также  
 [Использование CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

