---
title: Обработка команд в документе
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: f3cce539d52bd04e97a6b5f84cbd833b05afb5bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240578"
---
# <a name="handling-commands-in-the-document"></a>Обработка команд в документе

Класс документа также может обрабатывать определенные команды, сформированные пунктов меню, кнопки панели инструментов или сочетания клавиш. По умолчанию `CDocument` обрабатывает сохранения и сохранить как команды меню «файл» с использованием сериализации. Другие команды, которые влияют на данные также могут обрабатываться функциями-членами документа. Например, в программе Scribble класса `CScribDoc` предоставляет обработчик для редактирования очистить все команды, которая удаляет все данные, в настоящее время хранятся в документе. Документы могут иметь схемы сообщений, но в отличие от представления, документов не может обрабатывать стандартные сообщения Windows — только **WM_COMMAND** сообщения, или «команды».

## <a name="see-also"></a>См. также

[Использование документов](../mfc/using-documents.md)
