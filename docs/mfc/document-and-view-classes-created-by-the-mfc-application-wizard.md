---
title: Классы документов и представлений, создаваемые с помощью Мастера приложений MFC
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: 95b50e34d612c3b8f5dea2f8b469bd6c65182d41
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271454"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Классы документов и представлений, создаваемые с помощью Мастера приложений MFC

Мастер приложений MFC позволяет начать на разработки программы, создавая классы показана структура документов и представлений автоматически. После этого можно [сопоставляются эти классы команд и сообщений](../mfc/reference/mapping-messages-to-functions.md) и использование редактора исходного кода Visual C++ для записи их функции-члены.

Класс документа, созданные с помощью мастера приложений MFC является производным от класса [CDocument](../mfc/reference/cdocument-class.md). Класс представления является производным от [CView](../mfc/reference/cview-class.md). Имена, мастер приложений дает эти классы и файлы, содержащие их основаны на имени проекта, укажите в диалоговом окне мастера приложений. В мастере приложений можно использовать классы, создаваемые страницы для изменения имен по умолчанию.

Некоторым приложениям может потребоваться более одного класса документа, класс представления или класс окна фрейма. Дополнительные сведения см. в разделе [несколько типов документов, представлений и фрейма Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)
