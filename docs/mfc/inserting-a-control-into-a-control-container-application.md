---
title: "Контейнеры элементов управления ActiveX: Вставка элемента управления в приложение контейнера элемента управления | Документы Microsoft"
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
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1eaaf0426726f252fc4990f06faa73b0598cfbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления
Перед элемента ActiveX можно получить из приложения контейнера элемента управления ActiveX, необходимо добавить элемент управления ActiveX в контейнере приложения с помощью [Вставка элемента ActiveX](../windows/insert-activex-control-dialog-box.md) диалоговое окно.  
  
 Добавление элемента управления ActiveX в контейнере проекта элемента управления ActiveX, в разделе [для просмотра и добавление элементов управления ActiveX в диалоговое окно](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 После добавления элемента управления необходимо добавить переменную-член (для типа элемента управления ActiveX) для класса диалогового окна. Дополнительные сведения об этой процедуре см. в разделе [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md).  
  
 После добавления переменной-члена класса, называют класс-оболочку, автоматически создается и добавляется в проект. Этот класс используется в качестве интерфейса между контейнера элемента управления и внедренный элемент управления.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

