---
title: Инициализация и очистка документов и представлений | Документы Microsoft
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
ms.openlocfilehash: 0f59dcfbdac4a2d5da732c5e7f8cfc78083bf843
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Инициализация и очистка документов и представлений
Для инициализации и очистки после документов и представлений, следуйте приведенным ниже рекомендациям:  
  
-   Платформа MFC инициализирует документов и представлений; можно инициализировать все данные, которые можно добавлять в них.  
  
-   Очищает платформа как документы и закройте представлений; должен освободить память, размещенных в куче из в функциях-членах этих документов и представлений.  
  
> [!NOTE]
>  Помните, что инициализация для всего приложения лучше всего выполняется в переопределении [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) функции-члена класса `CWinApp`, и лучше всего проводить очистку для всего приложения в переопределении `CWinApp`функции-члена [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).  
  
 Жизненный цикл документ (и ее окна фрейма и представления или представления) в MDI приложения выглядит следующим образом:  
  
1.  Во время динамического создания вызывается конструктор документов.  
  
2.  Для каждого нового документа, документ [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) или [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) вызывается.  
  
3.  Пользователь взаимодействует с документом во время его существования. Обычно это происходит, когда пользователь работает на данные документа через представления, выбор и изменение данных. Представление передает изменения в документ для хранения и обновления других представлений. В это время документа и представление могут обрабатывать команды.  
  
4.  Платформа вызывает [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) удалить данные, относящиеся к документу.  
  
5.  Вызывается деструктор документа.  
  
 В приложении SDI шаг 1 выполняется один раз, когда сначала создается документ. Затем шаги со 2 по 4 многократно, выполняются каждый раз при открытии документа. Новый документ повторно использует существующий объект документа. Наконец шаг 5 выполняется при завершении работы приложения.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Инициализация документов и представлений](../mfc/initializing-documents-and-views.md)  
  
-   [Очистка документов и представлений](../mfc/cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)

