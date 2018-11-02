---
title: Выполнение функции-члена
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: 8e6e74b8f0fd62f96d6d846bbba867f9189550ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666860"
---
# <a name="run-member-function"></a>Выполнение функции-члена

Приложение framework проводит большую часть времени, [запуска](../mfc/reference/cwinapp-class.md#run) функция-член класса [CWinApp](../mfc/reference/cwinapp-class.md). После инициализации `WinMain` вызовы `Run` обработать цикл обработки сообщений.

`Run` Циклическое переключение между цикл обработки сообщений, проверка доступных сообщений очереди сообщений. Если сообщение не станет доступным, `Run` пересылает его для действия. Часто значение равно true, если доступных сообщений нет, который `Run` вызовы `OnIdle` любой времени простоя обработку или используемой инфраструктуры может потребоваться сделать. Если нет сообщений и не обработка бездействия для выполнения, приложение ожидает, пока не происходит что-то. Когда приложение завершает работу, `Run` вызовы `ExitInstance`. Рисунок в [функция-член OnIdle](../mfc/onidle-member-function.md) показана последовательность действий в цикле обработки сообщений.

Диспетчеризации сообщений зависит от типа сообщения. Дополнительные сведения см. в разделе [сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md).

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
