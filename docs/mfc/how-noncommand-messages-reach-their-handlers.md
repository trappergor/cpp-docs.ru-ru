---
title: Доступ Некомандных сообщений к обработчикам | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5c38a1d4294993170cfeff64be6a83700fa7497
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373442"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам

В отличие от команд стандартные сообщения Windows не будут направляться через цели цепочке управления, но обычно обрабатываются с помощью окна, к которому Windows отправляет сообщение. Окно может быть фрейма главного окна, дочерние окна интерфейса MDI, стандартного элемента управления, диалоговое окно, представление или любой другой дочернего окна.

Во время выполнения каждого окна Windows подключен на объект окна (прямо или косвенно производным `CWnd`), имеет свои собственные функции карты и обработчик соответствующее сообщение. Платформа использует схемы сообщений, как и для команды — для сопоставления входящих сообщений к обработчикам.

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

