---
title: Классы документов и представлений, создаваемые с помощью Мастера приложений MFC
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: 766fe4efb37c199c5babb75ce2cb08ebf676cca6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616054"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Классы документов и представлений, создаваемые с помощью Мастера приложений MFC

Мастер приложений MFC позволяет начать разработку программы, создавая скелетообразных документ и классы представлений. Затем можно [сопоставлять команды и сообщения с этими классами](reference/mapping-messages-to-functions.md) , а также использовать редактор исходного кода Visual C++ для написания своих функций элементов.

Класс документов, созданный мастером приложений MFC, является производным от класса [CDocument](reference/cdocument-class.md). Класс представления является производным от [CView](reference/cview-class.md). Имена этих классов и файлы, содержащиеся в мастере приложений, зависят от имени проекта, указываемого в диалоговом окне Мастер приложений. В мастере приложений можно использовать страницу созданные классы для изменения имен по умолчанию.

Некоторым приложениям может потребоваться несколько классов документов, классов представлений или окон фрейма. Дополнительные сведения см. в разделе [несколько типов документов, представлений и окон фрейма](multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>См. также раздел

[Архитектура документа/представления](document-view-architecture.md)
