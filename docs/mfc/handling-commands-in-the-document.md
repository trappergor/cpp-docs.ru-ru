---
title: Обработка команд в документе | Документация Майкрософт
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
ms.openlocfilehash: 8845ea7c44fd5a34774db0508302f5959987cdc9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441269"
---
# <a name="handling-commands-in-the-document"></a>Обработка команд в документе

Класс документа также может обрабатывать определенные команды, сформированные пунктов меню, кнопки панели инструментов или сочетания клавиш. По умолчанию `CDocument` обрабатывает сохранения и сохранить как команды меню «файл» с использованием сериализации. Другие команды, которые влияют на данные также могут обрабатываться функциями-членами документа. Например, в программе Scribble класса `CScribDoc` предоставляет обработчик для редактирования очистить все команды, которая удаляет все данные, в настоящее время хранятся в документе. Документы могут иметь схемы сообщений, но в отличие от представления, документов не может обрабатывать стандартные сообщения Windows — только **WM_COMMAND** сообщения, или «команды».

## <a name="see-also"></a>См. также

[Использование документов](../mfc/using-documents.md)

