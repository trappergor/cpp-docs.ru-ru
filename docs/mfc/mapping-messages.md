---
title: "Сопоставление сообщений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c415b12b22c19a5e1f2d19fd9c808a98485eb7ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-messages"></a>Сопоставление сообщений
Каждый класс framework, может получать сообщения или команды имеет свой собственный «схемы сообщений». Платформа использует схемы сообщений для подключения к их функциями обработчиков сообщений окна и команды. Любой класс, производный от класса `CCmdTarget` может иметь схему сообщений. Другие статьи схемы сообщений подробно объясняется и описано их использование.  
  
 Несмотря на имя «схему сообщений,» maps обработать сообщение сообщений и команд, все три категории сообщений, перечисленных в [категории сообщений](../mfc/message-categories.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

