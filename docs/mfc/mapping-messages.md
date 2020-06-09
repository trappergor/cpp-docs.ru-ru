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
ms.openlocfilehash: 16d6d7725d82bed6c9bfc02e408b68dcf7ffe5e4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625494"
---
# <a name="mapping-messages"></a>Сопоставление сообщений

Каждый класс платформы, который может принимать сообщения или команды, имеет собственную "схему сообщений". Платформа использует схемы сообщений для соединения сообщений и команд с их функциями обработчика. Любой класс, производный от класса, `CCmdTarget` может иметь схему сообщений. В других статьях подробно описаны схемы сообщений и описано, как их использовать.

Несмотря на имя "схема сообщения", схемы сообщений обрабатывали сообщения и команды — все три категории сообщений, перечисленных в [категориях сообщений](message-categories.md).

## <a name="see-also"></a>См. также раздел

[Сообщения и команды в платформе](messages-and-commands-in-the-framework.md)
