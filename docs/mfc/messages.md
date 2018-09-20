---
title: Сообщения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25c9cc70cec598f975bbd242af83597311bdc7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392259"
---
# <a name="messages"></a>Сообщения

Цикл обработки сообщений в `Run` функция-член класса `CWinApp` извлекает поставлены в очередь сообщения, сформированные при возникновении различных событий. Например когда пользователь нажимает кнопку мыши, Windows отправляет несколько сообщений, связанных с мышью, например WM_LBUTTONDOWN при нажатии левой кнопки мыши и WM_LBUTTONUP при отпускании левой кнопки мыши. Реализация платформы цикл обработки сообщений приложения отправляет сообщение в соответствующем окне.

Описываются важные категории сообщений в [категории сообщений](../mfc/message-categories.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

