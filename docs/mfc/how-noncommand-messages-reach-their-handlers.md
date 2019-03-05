---
title: Доступ некомандных сообщений к обработчикам
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: 4b9fb0a72b330380f0207db9968199a7e4c3d9b3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295062"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам

В отличие от команд стандартные сообщения Windows не будут направляться через цели цепочке управления, но обычно обрабатываются с помощью окна, к которому Windows отправляет сообщение. Окно может быть фрейма главного окна, дочерние окна интерфейса MDI, стандартного элемента управления, диалоговое окно, представление или любой другой дочернего окна.

Во время выполнения каждого окна Windows подключен на объект окна (прямо или косвенно производным `CWnd`), имеет свои собственные функции карты и обработчик соответствующее сообщение. Платформа использует схемы сообщений, как и для команды — для сопоставления входящих сообщений к обработчикам.

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)
