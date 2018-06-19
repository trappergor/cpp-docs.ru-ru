---
title: Модальные и немодальные диалоговые окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4f03d67e1eb9962f4303694db4850e800151404
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346565"
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

