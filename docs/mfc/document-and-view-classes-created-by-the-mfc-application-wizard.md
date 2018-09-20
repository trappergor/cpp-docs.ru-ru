---
title: Документирование и просмотра классов, созданные с помощью мастера приложений MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb1a1fc6c35bfb9589e827d798cb112640fa9b2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417622"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Классы документов и представлений, создаваемые с помощью Мастера приложений MFC

Мастер приложений MFC позволяет начать на разработки программы, создавая классы показана структура документов и представлений автоматически. После этого можно [сопоставляются эти классы команд и сообщений](../mfc/reference/mapping-messages-to-functions.md) и использование редактора исходного кода Visual C++ для записи их функции-члены.

Класс документа, созданные с помощью мастера приложений MFC является производным от класса [CDocument](../mfc/reference/cdocument-class.md). Класс представления является производным от [CView](../mfc/reference/cview-class.md). Имена, мастер приложений дает эти классы и файлы, содержащие их основаны на имени проекта, укажите в диалоговом окне мастера приложений. В мастере приложений можно использовать классы, создаваемые страницы для изменения имен по умолчанию.

Некоторым приложениям может потребоваться более одного класса документа, класс представления или класс окна фрейма. Дополнительные сведения см. в разделе [несколько типов документов, представлений и фрейма Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>См. также

[Архитектура документа/обзора](../mfc/document-view-architecture.md)

