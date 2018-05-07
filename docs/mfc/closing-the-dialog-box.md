---
title: Закрытие диалогового окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c800c204fd09057585064397d459f92c9ded272d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна
Модальное диалоговое окно закроется, когда пользователь выбирает один из ее кнопок, обычно "ОК" или кнопку "Отмена". Нажмите кнопку «ОК» предписывает для отправки объекта диалогового окна **BN_CLICKED** идентификатор, либо базы данных управления уведомление с помощью кнопки **IDOK** или **IDCANCEL**. `CDialog` предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel`. Вызов обработчиков по умолчанию `EndDialog` функцию-член, чтобы закрыть диалоговое окно. Можно также вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в разделе [EndDialog](../mfc/reference/cdialog-class.md#enddialog) функции-члена класса `CDialog` в *Справочник по библиотеке MFC*.  
  
 Чтобы упорядочить для закрытия и удаление немодального диалогового окна, переопределите `PostNcDestroy` и вызова **удалить** оператора **это** указателя. [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md) объясняет дальнейший ход событий.  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

