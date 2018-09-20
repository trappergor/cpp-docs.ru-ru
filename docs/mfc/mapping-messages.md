---
title: Сопоставление сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7324da5eaff15d240cabbaede2c2982021361257
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410985"
---
# <a name="mapping-messages"></a>Сопоставление сообщений

Каждый класс framework, который может получать сообщения или команды имеет свой собственный «сопоставить сообщение». Платформа использует схемы сообщений для подключения к соответствующим функциям-обработчикам сообщения и команды. Любой класс, производный от класса `CCmdTarget` может иметь схему сообщений. Другие статьи схемы сообщений подробно объяснить и описывается их использование.

Несмотря на имя «схему сообщений,» maps обрабатывающих сообщения, сообщения и команды — все три категории сообщений, перечисленных в [категории сообщений](../mfc/message-categories.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

