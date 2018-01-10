---
title: "Создание представления документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6997189f23ea7599dde0a1b19ba9f0ea350378d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="documentview-creation"></a>Создание документа или представления
Платформа предоставляет реализации `New` и **откройте** команд (среди прочего) на **файл** меню. Создание нового документа и связанного представления и окна фрейма — совместной работы среди объект приложения, шаблон документа, только что созданного документа и только что созданный фрейм окна. В следующей таблице перечислены объекты создать новые.  
  
### <a name="object-creators"></a>Средства создания объектов  
  
|Создание|Создает|  
|-------------|-------------|  
|Объект Application|Шаблон документа|  
|Шаблон документа|Document|  
|Шаблон документа|Окна фрейма|  
|Окна фрейма|Просмотр|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Создание шаблонов документов](../mfc/document-template-creation.md)   
 [Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)   
 [Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

