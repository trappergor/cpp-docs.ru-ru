---
title: "Шаблоны документов и процесс создания представления документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd47720009449d51abadd1e5f513149a83702ea3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Шаблоны документов и процесс создания документов и представлений
Чтобы управлять сложный процесс создания документов с их связанные с ними представления и окна фрейма, платформа использует два шаблона класса документа: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) для SDI-приложения и [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) приложениях MDI. Объект `CSingleDocTemplate` можно создать и сохранить один документ одного типа одновременно. Объект `CMultiDocTemplate` хранит список во множестве открытых документов одного типа.  
  
 Некоторые приложения поддерживают несколько типов документов. Например приложение может поддерживать документов текста и графики. В приложении при выборе новой команды меню "файл", диалоговое окно со списком возможных новых типов документов, откройте. Для каждого поддерживаемого типа документа приложение использует объект шаблона документа distinct. На следующем рисунке показана конфигурация MDI-приложения, который поддерживает два типа документа и показывает несколько открытых документов.  
  
 ![Приложение MDI, имеющее два типа документов](../mfc/media/vc387h1.gif "vc387h1")  
MDI-приложения с помощью двух типов документов  
  
 Шаблоны документов созданных и сохраненных объект приложения. Одно из ключевых задач, выполняемых во время вашего приложения `InitInstance` функции — для создания одного или нескольких шаблонов документов соответствующего типа. Эта функция описана в [Создание шаблонов документов](../mfc/document-template-creation.md). Объект приложения, содержит указатель на каждый шаблон документа в списке шаблонов и предоставляет интерфейс для добавления шаблонов документов.  
  
 Если требуется поддержка двух или более типов документов, необходимо добавить дополнительного обращения [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) для каждого типа документа.  
  
 Значок регистрируется для каждого шаблона документа, основанного на его положение в списке приложений шаблонов документов. Шаблоны документов порядок определяется порядком, они добавляются с помощью вызова к `AddDocTemplate`. MFC предполагается, что первый ресурс значка в приложении отображается значок приложения следующего ресурса значок является первый значок документа и т. д.  
  
 Например шаблон документа — третий из трех файлов для приложения. Если в приложении с индексом 3 ресурс значка, этот значок используется шаблоном документа. В противном случае значок с индексом 0 используется по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Создание шаблонов документов](../mfc/document-template-creation.md)   
 [Создание документа или представления](../mfc/document-view-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

