---
title: Создание шаблона документа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1a9067929e96c6d3fd851168af079e7e825dcb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443637"
---
# <a name="document-template-creation"></a>Создание шаблонов документов

При создании нового документа в ответ на **New** или **откройте** команду **файл** меню шаблона документа также создает новый объект окна до которой необходимо просмотреть документ.

Конструктор шаблонов документов указывает, какие типы документов, окон и представлений, шаблон будет иметь возможность создавать. Это определяется параметром аргументы, передаваемые в конструктор шаблонов документов. В следующем коде показано создание [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) пример приложения:

[!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]

Указатель на новый `CMultiDocTemplate` объект используется в качестве аргумента [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate). Аргументы для `CMultiDocTemplate` конструктор включают идентификатор ресурса, связанный с меню и ускорителями тип документа, и использует три из [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) макрос. `RUNTIME_CLASS` Возвращает [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) объекта для класса C++, с именем в качестве аргумента. Три `CRuntimeClass` объектов, передаваемых в конструктор шаблонов документов предоставить сведения, необходимые для создания новых объектов, указанных классов в процессе создания документа. В примере показано создание шаблона документа, который создает `CScribDoc` объекты с `CScribView` объектов, присоединенных. Представления являются обрамлена стандартный MDI дочерних фреймов.

## <a name="see-also"></a>См. также

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание документа или представления](../mfc/document-view-creation.md)<br/>
[Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)<br/>
[Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

