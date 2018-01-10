---
title: "Обработка команд в документе | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8d27698d573e1dee539f93ab88015285648fa77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handling-commands-in-the-document"></a>Обработка команд в документе
Класс документа также может обрабатывать определенные команды, созданные элементы меню, кнопки панели инструментов или сочетания клавиш. По умолчанию **CDocument** обрабатывает сохранения и сохранить как команды меню «файл» с помощью сериализации. Другие команды, которые влияют на данные также могут обрабатываться функциями-членами документа. Например, в программе Scribble класс `CScribDoc` предоставляет обработчик для изменения очистить все команды, которая удаляет все данные, которые в настоящее время хранятся в документе. Документы могут иметь схемы сообщений, но в отличие от представления, документы, не может обрабатывать стандартные сообщения Windows — только **WM_COMMAND** сообщения или «команды».  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

