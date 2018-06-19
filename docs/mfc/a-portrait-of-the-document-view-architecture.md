---
title: Портрет архитектуры представления документов | Документы Microsoft
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
ms.openlocfilehash: d366cf7c9aee6988d715edbe30e3938c30557e2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329820"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Портрет архитектуры "документ-представление"
В типичном приложении MFC объединены документов и представлений. Данные хранятся в документе, но представление есть привилегированный доступ к данным. Разделение документа из представления отделяет хранения и обслуживания данных от своего отображения.  
  
## <a name="gaining-access-to-document-data-from-the-view"></a>При получении доступа к данным из представления документа  
 Представление обращается к данным его документа с помощью [GetDocument](../mfc/reference/cview-class.md#getdocument) функция, возвращающая указатель на документ, или с помощью представления класса C++ `friend` класса документа. Затем представление использует его доступ к данным для получения данных, когда она готова к вызову draw или управлять ими в противном случае.  
  
 Например, из представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функции-члена в представлении используется **GetDocument** для получения указателя документа. Затем этот указатель используется для доступа к `CString` член данных в документе. Представление передает строку, `TextOut` функции. Код для этого примера см. в разделе [рисование в представлении](../mfc/drawing-in-a-view.md).  
  
## <a name="user-input-to-the-view"></a>Ввод пользовательских данных в представлении  
 Представление также может интерпретировать щелчка кнопкой мыши внутри себя как выбор или изменение данных. Аналогичным образом, он может интерпретировать нажатия клавиш, как ввод данных или изменения. Предположим, что пользователь вводит строку в представлении, управляющий текст. Получает указатель на документ, представление и использует указатель для передачи новых данных в документ, сохраняет его в определенную структуру данных.  
  
## <a name="updating-multiple-views-of-the-same-document"></a>Обновление нескольких представлений одного документа  
 В приложении с несколькими представлениями одного документа, таких как окна-разделителя в текстовом редакторе — представление сначала передает данные нового документа. Затем он вызывает документа [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) функция-член, который сообщает все представления документа, чтобы обновляются, отражая новые данные. Это синхронизирует представления.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Преимущества архитектуры "документ представление"](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Альтернативы для архитектуры "документ представление"](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)

