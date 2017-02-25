---
title: "Закрытие диалогового окна | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "диалоговые окна, закрытие"
  - "диалоговые окна MFC, закрытие"
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Закрытие диалогового окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Модальное диалоговое окно, когда пользователь закрывает его выбрать одну из кнопок, обычно кнопки " ОК " или Отмены.  Выбор " ОК " или " отмена " приводит к Windows отправить объект диалогового окна элемента управления сообщение уведомления с идентификатором кнопки **BN\_CLICKED**, **IDOK** или **IDCANCEL**.  `CDialog` предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel`.  Обработчики по умолчанию вызывает функцию\-член `EndDialog`, чтобы закрыть окно диалогового окна.  Можно также вызвать `EndDialog` из собственного кода.  Дополнительные сведения см. в функцию\-член [EndDialog](../Topic/CDialog::EndDialog.md) класса `CDialog` в *справочнике по MFC*.  
  
 Расположение для закрыть и удаление безрежимное диалоговое окно, переопределение `PostNcDestroy` и вызвать оператор **удалить** на указатель **this**.  [Удалить диалоговое окно](../Topic/Destroying%20the%20Dialog%20Box.md) объясняет, что произойдет далее.  
  
## См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)