---
title: Закрытие диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 48ea954552b3ea9aa7193a47fc2a66d731312d77
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685379"
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна

Модальное диалоговое окно закрывается, когда пользователь нажимает одну из кнопок, как правило, кнопка ОК или Отмена. Нажатие кнопки ОК или Отмена приводит к тому, что Windows отправляет объект диалогового окна **BN_CLICKED** сообщение с уведомлением об управлении с идентификатором кнопки **идок** или **идканцел**. `CDialog` предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel`. Обработчики по умолчанию вызывают функцию члена `EndDialog`, чтобы закрыть диалоговое окно. Можно также вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в разделе функция члена [EndDialog](../mfc/reference/cdialog-class.md#enddialog) класса `CDialog` в *справочнике по MFC*.

Чтобы расположиться на закрытие и удаление немодального диалогового окна, переопределите `PostNcDestroy` и вызовите оператор **Delete** для **этого** указателя. [Удаление диалогового окна объясняет,](../mfc/destroying-the-dialog-box.md) что происходит дальше.

## <a name="see-also"></a>См. также:

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
