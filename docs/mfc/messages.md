---
title: Сообщения
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: 033edfd289ea075b89e9d44111da94b987177470
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434545"
---
# <a name="messages"></a>Сообщения

Цикл обработки сообщений в `Run` функция-член класса `CWinApp` извлекает поставлены в очередь сообщения, сформированные при возникновении различных событий. Например когда пользователь нажимает кнопку мыши, Windows отправляет несколько сообщений, связанных с мышью, например WM_LBUTTONDOWN при нажатии левой кнопки мыши и WM_LBUTTONUP при отпускании левой кнопки мыши. Реализация платформы цикл обработки сообщений приложения отправляет сообщение в соответствующем окне.

Описываются важные категории сообщений в [категории сообщений](../mfc/message-categories.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

