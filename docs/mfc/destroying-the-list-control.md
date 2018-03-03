---
title: "Уничтожение элемента управления списка | Документы Microsoft"
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
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdaafb8a6951050dac0022e0e6e8874b48d688e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-list-control"></a>Уничтожение элемента управления "Список"
При внедрении вашей [CListCtrl](../mfc/reference/clistctrl-class.md) объекта как элемент данных, представления или диалогового окна класса, он уничтожается при уничтожении его владельца. Если вы используете [CListView](../mfc/reference/clistview-class.md), платформа уничтожает элемента управления, если она окончательно удаляет представления.  
  
 Если упорядочить для некоторых данных списка должен храниться в приложения, а не элемент управления списка, необходимо упорядочить для его освобождения. Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](http://msdn.microsoft.com/library/windows/desktop/bb774736) в Windows SDK.  
  
 Кроме того вы отвечаете за освобождение все списки изображений создана и связана с объект списка элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

