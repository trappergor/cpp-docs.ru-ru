---
title: "Создание немодальных диалоговых | Документы Microsoft"
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
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0549f898a076b140e7b5bed23c1c1e8c60d6adba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон
Для немодального диалогового окна необходимо предоставить открытый конструктор в класс диалогового окна. Создание немодального диалогового окна, будет вызван открытый и затем вызвать объекта диалогового окна [создать](../mfc/reference/cdialog-class.md#create) функции-члена для загрузки ресурса диалогового окна. Можно вызвать **создать** во время или после вызова этого конструктора. Если у ресурса диалогового окна Свойства **WS_VISIBLE**, немедленно появится диалоговое окно. Если нет, следует вызвать его [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

