---
title: "Создание модальных диалоговых | Документы Microsoft"
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
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 815db891514eb03169dac2ad29e50469d74dcfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон
Создание модального диалогового окна, вызовите один из двух общих конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md). Затем вызовите объекта диалогового окна [DoModal](../mfc/reference/cdialog-class.md#domodal) функции-члена для отображения диалогового окна и управления взаимодействием с его, пока пользователь нажимает кнопку ОК или отменить. Такое управление по `DoModal` придает модальное диалоговое окно. Для модальные диалоговые окна `DoModal` загружает ресурс диалогового окна.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

