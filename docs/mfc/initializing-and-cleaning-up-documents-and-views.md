---
title: Инициализация и очистка документов и представлений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdc1efa9d2284a48e4f906a326efcd62dd6c61b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412955"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Инициализация и очистка документов и представлений

Следуйте приведенным ниже рекомендациям для инициализации и очистки после документов и представлений:

- Платформа MFC инициализирует документов и представлений; можно инициализировать все данные, которые можно добавлять в них.

- Очищает платформы, как документы и закройте представлений; необходимо освободить память, размещенный в куче из внутри функции-члены этих документов и представлений.

> [!NOTE]
>  Отозвать инициализации для всего приложения лучше всего сделать в переопределении [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) функция-член класса `CWinApp`, и очистки для всего приложения лучше всего сделать в переопределении `CWinApp`функция-член [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).

Срок жизни документа (и его окно фрейма и представления или представления) в MDI приложения выглядит следующим образом:

1. Во время динамического создания вызывается конструктор документов.

1. Для каждого нового документа, документ [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) или [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) вызывается.

1. Пользователь взаимодействует с документом на протяжении всего времени его существования. Обычно это происходит, когда вы работаете на данные документа через представления, выбора и редактирования данных. Представление передает изменения в документ для хранения и обновления других представлений. В течение этого времени документа и представление могут обрабатывать команды.

1. Платформа вызывает [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) удалить данные, относящиеся к документу.

1. Вызывается деструктор документа.

В приложении SDI шаг 1 выполняется один раз, при первом создании документа. Затем шаги 2 – 4 несколько раз, выполняются каждый раз при открытии документа. Новый документ повторно использует существующий объект документа. Наконец при завершении приложения, будет выполнен шаг 5.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Инициализация документов и представлений](../mfc/initializing-documents-and-views.md)

- [Очистка документов и представлений](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)

