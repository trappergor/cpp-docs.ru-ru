---
title: Закрытие диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 07e4159eccde1fab89d4a5ffadee4e6d11fc20f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302589"
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна

Модальное диалоговое окно закрывается, когда пользователь выбирает один из ее кнопки, обычно "ОК" или "Отмена". Нажмите кнопку "ОК" или "Отмена" приводит к Windows для отправки объекта диалогового окна **BN_CLICKED** идентификатор, сообщение уведомление элемента управления с помощью кнопки-либо **IDOK** или **IDCANCEL**. `CDialog` предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel`. Вызов обработчиков по умолчанию `EndDialog` функция-член, чтобы закрыть диалоговое окно. Можно также вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в разделе [EndDialog](../mfc/reference/cdialog-class.md#enddialog) функция-член класса `CDialog` в *Справочник по библиотеке MFC*.

Чтобы упорядочить для закрытия и удаления немодального диалогового окна, переопределите `PostNcDestroy` и вызвать **удалить** оператора **это** указатель. [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md) объясняет, что будет дальше.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
