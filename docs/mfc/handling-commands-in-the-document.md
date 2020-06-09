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
ms.openlocfilehash: ed2ef635437408cacfd600d6cdba4b3731d575b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625743"
---
# <a name="handling-commands-in-the-document"></a>Обработка команд в документе

Класс документов также может работать с определенными командами, созданными элементами меню, кнопками панели инструментов или сочетаниями клавиш. По умолчанию `CDocument` обрабатывает команды Сохранить и сохранить как в меню файл с помощью сериализации. Другие команды, влияющие на данные, могут также обрабатываться функциями элементов документа. Например, в программе Scribble класс `CScribDoc` предоставляет обработчик для команды «изменить очистить все», которая удаляет все данные, хранящиеся в настоящий момент в документе. Документы могут иметь схемы сообщений, но в отличие от представлений, документы не могут работать со стандартными сообщениями Windows — только **WM_COMMAND** сообщениями или «командами».

## <a name="see-also"></a>См. также раздел

[Использование документов](using-documents.md)
