---
title: "Использование старых панелей инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COldToolBar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [MFC], backward compatibility
- COldToolBar class [MFC]
ms.assetid: 3543257c-8547-43f0-a66a-ee641dc1cf89
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b64c1b9c5cf38337cd286a86275331f4f5f65daf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-your-old-toolbars"></a>Использование старых панелей инструментов
При использовании предыдущих версий Visual C++ для создания настраиваемые панели инструментов, новая реализация класса [CToolBar](../mfc/reference/ctoolbar-class.md) может вызвать проблемы. Чтобы не нужно было освобождать старых панелей инструментов, чтобы использовать новые функциональные возможности, старая реализация по-прежнему поддерживается.  
  
 Образец DOCKTOOL не использует старый стиль панели инструментов, а только новый стиль панели инструментов.  
  
 Старый стиль панели инструментов нельзя изменить с помощью панели инструментов редактора ресурсов.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Принципы работы инструментов](../mfc/toolbar-fundamentals.md)  
  
-   [Закрепленные и плавающие панели инструментов](../mfc/docking-and-floating-toolbars.md)  
  
-   [Всплывающие подсказки панели инструментов](../mfc/toolbar-tool-tips.md)  
  
-   [Работа с элементом управления панели инструментов](../mfc/working-with-the-toolbar-control.md)  
  
## <a name="see-also"></a>См. также  
 [Реализация панели инструментов MFC](../mfc/mfc-toolbar-implementation.md)

