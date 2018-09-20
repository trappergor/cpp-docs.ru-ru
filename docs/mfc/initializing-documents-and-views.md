---
title: Инициализация документов и представлений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6a6f989b8c6b19c78cf9ad508d18e9592bb9305
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417401"
---
# <a name="initializing-documents-and-views"></a>Инициализация документов и представлений

Документы создаются двумя разными способами, поэтому ваш класс документа должен поддерживать оба способа. Во-первых пользователь может создать новый, пустой документ с помощью команды создания файла. В этом случае инициализации документа в переопределении [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) функция-член класса [CDocument](../mfc/reference/cdocument-class.md). Во-вторых пользователь может использовать команду «Открыть» в меню "файл" для создания нового документа, содержимое которого считываются из файла. В этом случае инициализации документа в переопределении [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) функция-член класса `CDocument`. Если оба инициализаций совпадают, можно вызывать общие функции-члена из обоих переопределения или `OnOpenDocument` можно вызвать `OnNewDocument` для инициализации чистой документа, а затем завершить операции открытия.

Представления создаются после создания документов. Наилучшее время для инициализации представления — после .NET framework закончено создание документа, окно фрейма и представления. Вы можете инициализировать представления путем переопределения [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функцию-член [CView](../mfc/reference/cview-class.md). Если необходимо повторно инициализировать или настройки каждый раз при изменении документа, можно переопределить [OnUpdate](../mfc/reference/cview-class.md#onupdate).

## <a name="see-also"></a>См. также

[Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)

