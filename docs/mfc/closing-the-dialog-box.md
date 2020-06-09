---
title: Закрытие диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: a695a8e331eb8a4f22394deb65857bf93ecab41e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617211"
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна

Модальное диалоговое окно закрывается, когда пользователь нажимает одну из кнопок, как правило, кнопка ОК или Отмена. Нажатие кнопки ОК или Отмена приводит к тому, что Windows отправляет объект диалогового окна **BN_CLICKED** сообщение с уведомлением об управлении с идентификатором кнопки **идок** или **идканцел**. `CDialog`предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel` . Обработчики по умолчанию вызывают `EndDialog` функцию члена для закрытия диалогового окна. Вы также можете вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в описании функции элемента [EndDialog](reference/cdialog-class.md#enddialog) класса `CDialog` в *справочнике по MFC*.

Чтобы расположиться на закрытие и удаление немодального диалогового окна, переопределите `PostNcDestroy` и вызовите оператор **Delete** для **этого** указателя. [Удаление диалогового окна объясняет,](destroying-the-dialog-box.md) что происходит дальше.

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
