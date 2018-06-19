---
title: Создание представления документов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb89180db8e1a6cce2c40bbb4bae0965b972afa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343529"
---
# <a name="documentview-creation"></a>Создание документа или представления
Платформа предоставляет реализации `New` и **откройте** команд (среди прочего) на **файл** меню. Создание нового документа и связанного представления и окна фрейма — совместной работы среди объект приложения, шаблон документа, только что созданного документа и только что созданный фрейм окна. В следующей таблице перечислены объекты создать новые.  
  
### <a name="object-creators"></a>Средства создания объектов  
  
|Создание|Создает|  
|-------------|-------------|  
|Объект Application|Шаблон документа|  
|Шаблон документа|Документ|  
|Шаблон документа|Окна фрейма|  
|Окна фрейма|Просмотр|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание шаблонов документов](../mfc/document-template-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

