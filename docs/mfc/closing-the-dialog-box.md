---
title: Закрытие диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: ef6cdaeb4cb0d7537cda980a1d2c483c53c8dc9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217978"
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна

Модальное диалоговое окно закрывается, когда пользователь нажимает одну из кнопок, как правило, кнопка ОК или Отмена. Нажатие кнопки ОК или Отмена приводит к тому, что Windows отправляет объект диалогового окна **BN_CLICKED** сообщение с уведомлением об управлении с идентификатором кнопки **идок** или **идканцел**. `CDialog`предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel` . Обработчики по умолчанию вызывают `EndDialog` функцию члена для закрытия диалогового окна. Вы также можете вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в описании функции элемента [EndDialog](reference/cdialog-class.md#enddialog) класса `CDialog` в *справочнике по MFC*.

Чтобы расположиться на закрытие и удаление немодального диалогового окна, переопределите `PostNcDestroy` и вызовите **`delete`** оператор для **`this`** указателя. [Удаление диалогового окна объясняет,](destroying-the-dialog-box.md) что происходит дальше.

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
