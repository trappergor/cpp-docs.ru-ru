---
title: Инициализация и очистка документов и представлений
ms.date: 11/04/2016
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
ms.openlocfilehash: 3c92d60941cd6542bd0d6c27e8a879dc85e3a3d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377206"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Инициализация и очистка документов и представлений

Используйте следующие рекомендации для инициализации и очистки после документов и представлений:

- Рамки МФЦ инициализируют документы и мнения; вы инициализируете любые данные, которые вы добавляете к ним.

- Рамки очищается по мере закрытия документов и представлений; вы должны распределить любую память, которую вы выделили на куче, из функций членов этих документов и представлений.

> [!NOTE]
> Напомним, что инициализация для всего приложения лучше всего сделать в переопределение функции члена [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) `CWinApp`класса, `CWinApp` и очистка для всего приложения лучше всего сделать в переопределение функции участника [ExitInstance.](../mfc/reference/cwinapp-class.md#exitinstance)

Срок службы документа (и его окна кадра, представления или представления) в приложении MDI следующий:

1. При создании динамического документа называется конструктор документа.

1. Для каждого нового документа вызывается [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) или [OnOpenDocument.](../mfc/reference/cdocument-class.md#onopendocument)

1. Пользователь взаимодействует с документом на протяжении всего срока его службы. Обычно это происходит, когда пользователь работает над данными документа через представление, выбирая и редактируя данные. Представление передает изменения в документ для хранения и обновления других представлений. За это время как документ, так и представление могут обрабатывать команды.

1. Платформа призывает [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) удалять данные, специфичные для документа.

1. Вызывается деструктор документа.

В приложении SDI шаг 1 выполняется один раз, когда документ впервые создается. Затем шаги 2 к 4 выполняются неоднократно каждый раз при открытии нового документа. Новый документ повторно использует существующий объект документа. Наконец, шаг 5 выполняется по окончании приложения.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Инициализация документов и представлений](../mfc/initializing-documents-and-views.md)

- [Очистка документов и представлений](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>См. также раздел

[Архитектура документов/просмотра](../mfc/document-view-architecture.md)
