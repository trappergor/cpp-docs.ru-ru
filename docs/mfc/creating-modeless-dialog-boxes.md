---
title: Создание немодальных диалоговых | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2055312c7418b14c9b274649db8faa297554257e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340997"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон
Для немодального диалогового окна необходимо предоставить открытый конструктор в класс диалогового окна. Создание немодального диалогового окна, будет вызван открытый и затем вызвать объекта диалогового окна [создать](../mfc/reference/cdialog-class.md#create) функции-члена для загрузки ресурса диалогового окна. Можно вызвать **создать** во время или после вызова этого конструктора. Если у ресурса диалогового окна Свойства **WS_VISIBLE**, немедленно появится диалоговое окно. Если нет, следует вызвать его [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

