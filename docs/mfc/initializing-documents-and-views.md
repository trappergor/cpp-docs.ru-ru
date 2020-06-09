---
title: Инициализация документов и представлений
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: 0e970d6e8a166283f82575b309cf023f48899403
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626357"
---
# <a name="initializing-documents-and-views"></a>Инициализация документов и представлений

Документы создаются двумя разными способами, поэтому класс документа должен поддерживать оба способа. Во-первых, пользователь может создать новый пустой документ с помощью команды File New. В этом случае инициализируйте документ в переопределении функции члена [онневдокумент](reference/cdocument-class.md#onnewdocument) класса [CDocument](reference/cdocument-class.md). Во-вторых, пользователь может использовать команду Открыть в меню файл для создания нового документа, содержимое которого считывается из файла. В этом случае инициализируйте документ в переопределении функции членства в классе в формате [OpenDocument](reference/cdocument-class.md#onopendocument) `CDocument` . Если обе инициализации одинаковы, можно вызвать общую функцию-член из обоих переопределений или `OnOpenDocument` вызвать `OnNewDocument` для инициализации очистки документа, а затем завершить операцию открытия.

Представления создаются после создания документов. Самое лучшее время инициализировать представление — после того, как платформа завершит создание документа, окна фрейма и представления. Можно инициализировать представление, переопределив функцию члена [онинитиалупдате](reference/cview-class.md#oninitialupdate) класса [CView](reference/cview-class.md). Если необходимо выполнить повторную инициализацию или корректировку содержимого при каждом изменении документа, можно переопределить [OnUpdate](reference/cview-class.md#onupdate).

## <a name="see-also"></a>См. также раздел

[Инициализация и очистка документов и представлений](initializing-and-cleaning-up-documents-and-views.md)
