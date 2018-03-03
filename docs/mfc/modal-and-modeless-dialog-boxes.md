---
title: "Модальные и немодальные диалоговые окна | Документы Microsoft"
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
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 982bb8f195c3744246addc18d66bee953914dde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="modal-and-modeless-dialog-boxes"></a>Модальные и немодальные диалоговые окна
Можно использовать класс [CDialog](../mfc/reference/cdialog-class.md) для управления два вида диалоговые окна:  
  
-   *Модальные диалоговые окна*, который требуют от пользователя ответ перед продолжением работы программы  
  
-   *Безрежимные диалоговые окна*, который оставаться на экране и доступны для использования в любое время, но разрешить другие действия пользователя  
  
 Редактирование ресурсов и процедуры для создания шаблона диалогового окна одинаковы для модальные и немодальные диалоговые окна.  
  
 Создание диалогового окна программы необходимо выполнить следующие действия:  
  
1.  Используйте [редактор диалоговых окон](../windows/dialog-editor.md) спроектировать диалоговое окно и создать его ресурса шаблона диалогового окна.  
  
2.  Создание класса диалогового окна.  
  
3.  Подключение [ресурса диалогового окна элементы управления для обработчиков сообщений](../windows/adding-event-handlers-for-dialog-box-controls.md) в классе диалогового окна.  
  
4.  Добавьте членов данных, связанных с элементами управления в диалоговое окно «» и указать [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md) и [проверки данных диалогового окна](../mfc/dialog-data-validation.md) для элементов управления.  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

