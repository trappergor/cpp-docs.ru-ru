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
ms.openlocfilehash: 82c55c82d6b7a3faa65906345137885555a57d08
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287288"
---
# <a name="mapping-messages"></a>Сопоставление сообщений

Каждый класс framework, который может получать сообщения или команды имеет свой собственный «сопоставить сообщение». Платформа использует схемы сообщений для подключения к соответствующим функциям-обработчикам сообщения и команды. Любой класс, производный от класса `CCmdTarget` может иметь схему сообщений. Другие статьи схемы сообщений подробно объяснить и описывается их использование.

Несмотря на имя «схему сообщений,» maps обрабатывающих сообщения, сообщения и команды — все три категории сообщений, перечисленных в [категории сообщений](../mfc/message-categories.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)
