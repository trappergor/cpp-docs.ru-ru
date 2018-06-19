---
title: Создание новых документов, окон и представлений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d929f4d7419e027a1018c4b0b33a4e42416613
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343419"
---
# <a name="creating-new-documents-windows-and-views"></a>Создание новых документов, окон и представлений
На следующих рисунках обзора процесса создания для документов, представлений и фреймов. Другие статьи, посвященные участвующие объекты указать дополнительные сведения.  
  
 После завершения этого процесса совместно объекты существуют и сохранения указателей на друг с другом. Ниже приведена последовательность, в которой создаются объекты. Вы можете использовать последовательности из рис рисунок.  
  
 ![Последовательность создания документа](../mfc/media/vc387l1.gif "vc387l1")  
Последовательность создания документа  
  
 ![Последовательность создания окна фрейма](../mfc/media/vc387l2.png "vc387l2")  
Последовательность создания окна фрейма  
  
 ![Последовательность создания представления](../mfc/media/vc387l3.gif "vc387l3")  
Последовательность создания представления  
  
 Сведения о как платформа Инициализирует новый документ, представления и окна фрейма объектов содержатся классы [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) в справочнике по библиотеке MFC. См. также [Технические заметки 22](../mfc/tn022-standard-commands-implementation.md), где рассмотрены далее процессы создания и инициализации его рассматриваются стандартные команды framework для `New` и **откройте** элементы на **Файл** меню.  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Инициализация добавления пользователя к этим классам  
 Предыдущий фигур также предложит точек, в которых можно переопределить функции-члены для инициализации объектов приложения. Переопределение `OnInitialUpdate` в представлении класса — это лучшее место для инициализации представления. `OnInitialUpdate` Вызов происходит сразу после создания окна фрейма и представления в фрейме окна вложенный документ, его. Например, если представление — это представление прокрутки (производный от `CScrollView` вместо `CView`), необходимо задать размер представления, исходя из размера документа в вашей `OnInitialUpdate` переопределения. (Этот процесс описан в описании класса [CScrollView](../mfc/reference/cscrollview-class.md).) Можно переопределить **CDocument** функции-члены `OnNewDocument` и `OnOpenDocument` для обеспечения инициализации приложения документа. Как правило и необходимо переопределить, так как документ можно создавать двумя способами.  
  
 В большинстве случаев переопределение должно вызывать версии базового класса. Дополнительные сведения см. в разделе функции-члены именованного классов [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), и [CWinApp](../mfc/reference/cwinapp-class.md) в MFC Справочник по библиотеке.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание шаблонов документов](../mfc/document-template-creation.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)

