---
title: Доступ некомандных сообщений к обработчикам
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: f64eb97315b41a314c791e1a4c5bc7721b329fca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545462"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам

В отличие от команд стандартные сообщения Windows не будут направляться через цели цепочке управления, но обычно обрабатываются с помощью окна, к которому Windows отправляет сообщение. Окно может быть фрейма главного окна, дочерние окна интерфейса MDI, стандартного элемента управления, диалоговое окно, представление или любой другой дочернего окна.

Во время выполнения каждого окна Windows подключен на объект окна (прямо или косвенно производным `CWnd`), имеет свои собственные функции карты и обработчик соответствующее сообщение. Платформа использует схемы сообщений, как и для команды — для сопоставления входящих сообщений к обработчикам.

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

