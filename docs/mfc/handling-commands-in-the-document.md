---
title: Обработка команд в документе | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c20ff02b2d72f1dfa6afab5a0d547b46aa55b18c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="handling-commands-in-the-document"></a>Обработка команд в документе
Класс документа также может обрабатывать определенные команды, созданные элементы меню, кнопки панели инструментов или сочетания клавиш. По умолчанию **CDocument** обрабатывает сохранения и сохранить как команды меню «файл» с помощью сериализации. Другие команды, которые влияют на данные также могут обрабатываться функциями-членами документа. Например, в программе Scribble класс `CScribDoc` предоставляет обработчик для изменения очистить все команды, которая удаляет все данные, которые в настоящее время хранятся в документе. Документы могут иметь схемы сообщений, но в отличие от представления, документы, не может обрабатывать стандартные сообщения Windows — только **WM_COMMAND** сообщения или «команды».  
  
## <a name="see-also"></a>См. также  
 [Использование документов](../mfc/using-documents.md)

