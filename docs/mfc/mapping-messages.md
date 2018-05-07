---
title: Сопоставление сообщений | Документы Microsoft
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
ms.openlocfilehash: f521145599a3d734a22dd3b2707ad4dd16df8e80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mapping-messages"></a>Сопоставление сообщений
Каждый класс framework, может получать сообщения или команды имеет свой собственный «схемы сообщений». Платформа использует схемы сообщений для подключения к их функциями обработчиков сообщений окна и команды. Любой класс, производный от класса `CCmdTarget` может иметь схему сообщений. Другие статьи схемы сообщений подробно объясняется и описано их использование.  
  
 Несмотря на имя «схему сообщений,» maps обработать сообщение сообщений и команд, все три категории сообщений, перечисленных в [категории сообщений](../mfc/message-categories.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

