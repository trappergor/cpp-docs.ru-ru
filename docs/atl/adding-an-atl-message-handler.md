---
title: Добавление обработчика сообщений ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 712f1b725afd52057deca8f05047c91bfc4affce
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753414"
---
# <a name="adding-an-atl-message-handler"></a>Добавление обработчика сообщений ATL

Чтобы добавить обработчик сообщений (член функции, который обрабатывает сообщения Windows) к элементу управления, выберите элемент управления в окне просмотра классов. Затем откройте **свойства** выберите **сообщений** и пункт в раскрывающемся списке элемента управления в поле противоположной требуется сообщение. Это добавит объявление для обработчик сообщений в файл заголовка элемента управления и схему реализации обработчика в CPP-файл элемента управления. Он также добавить схему сообщений и добавьте запись для обработчика.

Добавление обработчика сообщений в ATL сходно с добавлением обработчика сообщений для класса MFC. См. в разделе [Добавление обработчика сообщения MFC](../mfc/reference/adding-an-mfc-message-handler.md) Дополнительные сведения.

Только для добавления обработчика сообщений ATL применяются следующие условия:

- Обработчики сообщений следовать общему соглашению об именовании MFC.

- В сопоставление основного сообщения добавляются новые записи схемы сообщений. Мастер не распознает схемы альтернативный сообщений и создание цепочки.

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)

