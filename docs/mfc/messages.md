---
title: Сообщения
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: f36dab679a2e41910b2445a7dab36f5786081563
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624283"
---
# <a name="messages"></a>Сообщения

Цикл обработки сообщений в `Run` функции члена класса `CWinApp` получает сообщения в очереди, созданные различными событиями. Например, когда пользователь нажимает кнопку мыши, Windows отправляет несколько сообщений, связанных с мышью, например WM_LBUTTONDOWN при нажатии левой кнопки мыши и WM_LBUTTONUP при отпускании левой кнопки мыши. Реализация цикла сообщений приложения в инфраструктуре отправляет сообщение в соответствующее окно.

Важные категории сообщений описаны в разделе [категории сообщений](message-categories.md).

## <a name="see-also"></a>См. также раздел

[Сообщения и команды в платформе](messages-and-commands-in-the-framework.md)
