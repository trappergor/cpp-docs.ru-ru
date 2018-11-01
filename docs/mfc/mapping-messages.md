---
title: Сопоставление сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], about message maps
- mappings [MFC], commands
- commands [MFC], mapping
- command mapping [MFC]
- message handling [MFC], connecting to handler functions
- commands [MFC], connecting to handler functions
- mappings [MFC], messages
- messages [MFC], mapping
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
ms.openlocfilehash: 1f31bc2e3c6af9c4b899167ba99c152a231a929d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665846"
---
# <a name="mapping-messages"></a>Сопоставление сообщений

Каждый класс framework, который может получать сообщения или команды имеет свой собственный «сопоставить сообщение». Платформа использует схемы сообщений для подключения к соответствующим функциям-обработчикам сообщения и команды. Любой класс, производный от класса `CCmdTarget` может иметь схему сообщений. Другие статьи схемы сообщений подробно объяснить и описывается их использование.

Несмотря на имя «схему сообщений,» maps обрабатывающих сообщения, сообщения и команды — все три категории сообщений, перечисленных в [категории сообщений](../mfc/message-categories.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

