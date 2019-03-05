---
title: Переопределение стандартной маршрутизации команд
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 5383c1053894d44e23baf51b19ac3df4e60158e5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277954"
---
# <a name="overriding-the-standard-command-routing"></a>Переопределение стандартной маршрутизации команд

В редких случаях при необходимо реализовать некоторую вариацию маршрутизации платформу standard, можно переопределить его. Суть в том для изменения маршрута в один или несколько классов, переопределив `OnCmdMsg` в этих классах. Сделать это:

- В классе, который нарушает порядок для передачи объекта не по умолчанию.

- В новый объект не по умолчанию или целевые объекты команд его в свою очередь может передать команды.

При вставке некоторых новый объект в маршруте, его класс должен быть классом цели команды. В используемой версии переопределения `OnCmdMsg`, не забудьте вызвать версию, которая переопределение. См. в разделе [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) функция-член класса `CCmdTarget` в *Справочник по библиотеке MFC* и версии в такие классы как `CView` и `CDocument` в предоставленный исходный код для примеров.

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)
