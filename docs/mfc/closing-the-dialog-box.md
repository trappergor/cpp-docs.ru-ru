---
title: Закрытие диалогового окна | Документация Майкрософт
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
ms.openlocfilehash: e9ad4b8af63b68912c232767bf1fd14070fda261
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409055"
---
# <a name="closing-the-dialog-box"></a>Закрытие диалогового окна

Модальное диалоговое окно закрывается, когда пользователь выбирает один из ее кнопки, обычно "ОК" или "Отмена". Нажмите кнопку "ОК" или "Отмена" приводит к Windows для отправки объекта диалогового окна **BN_CLICKED** идентификатор, сообщение уведомление элемента управления с помощью кнопки-либо **IDOK** или **IDCANCEL**. `CDialog` предоставляет функции обработчика по умолчанию для этих сообщений: `OnOK` и `OnCancel`. Вызов обработчиков по умолчанию `EndDialog` функция-член, чтобы закрыть диалоговое окно. Можно также вызвать `EndDialog` из собственного кода. Дополнительные сведения см. в разделе [EndDialog](../mfc/reference/cdialog-class.md#enddialog) функция-член класса `CDialog` в *Справочник по библиотеке MFC*.

Чтобы упорядочить для закрытия и удаления немодального диалогового окна, переопределите `PostNcDestroy` и вызвать **удалить** оператора **это** указатель. [Уничтожение диалогового окна](../mfc/destroying-the-dialog-box.md) объясняет, что будет дальше.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

