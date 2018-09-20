---
title: Портрет архитектуры представления документов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bd07bf521e1dcfc59b1d3f213f513b1d361b8a6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409523"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Портрет архитектуры "документ-представление"

В типичном приложении MFC связаны документов и представлений. Данные хранятся в документе, но представление есть привилегированный доступ к данным. Разделение документа из представления отделяет хранения и обслуживания данных от своего отображения.

## <a name="gaining-access-to-document-data-from-the-view"></a>Доступ к данные из представления документа

Представления получает доступ к его документа данным с помощью [GetDocument](../mfc/reference/cview-class.md#getdocument) функцию, которая возвращает указатель к документу, или с помощью представления класса C++ `friend` класса документа. Представление затем использует его доступ к данным для получения данных, когда она готова к вызову draw или другой способ манипуляции.

Например, из представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член, оно использует `GetDocument` для получения указателя документа. Затем используется для доступа к этому указателю `CString` элемент данных в документе. Представление передает строку для `TextOut` функции. Код для этого примера см. в разделе [рисование в представлении](../mfc/drawing-in-a-view.md).

## <a name="user-input-to-the-view"></a>Ввод пользовательских данных в представлении

Представление также может восприниматься щелчка кнопкой мыши сам в себя как выбор или изменение данных. Аналогичным образом, он может интерпретировать нажатия клавиш как ввод данных или редактирования. Предположим, что пользователь вводит строку в представлении, управляющий текст. Представление получает указатель на документ и использует указатель для передачи новых данных документа, который сохраняет его в некоторые структуры данных.

## <a name="updating-multiple-views-of-the-same-document"></a>Обновление нескольких представлений одного документа

В приложении с несколькими представлениями одного документа, таких как окна разделителя в текстовом редакторе, представление сначала передает новые данные к документу. Затем он вызывает документа [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) функция-член, который указывает все представления документа могут выполнять обновления, отражая новые данные. Это синхронизирует представления.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Преимущества архитектуры документ/представление](../mfc/advantages-of-the-document-view-architecture.md)

- [Альтернативы для архитектуры документ/представление](../mfc/alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)

