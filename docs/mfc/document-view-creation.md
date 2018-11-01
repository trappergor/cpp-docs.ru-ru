---
title: Создание документа или представления
ms.date: 11/04/2016
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
ms.openlocfilehash: eccc65df784d000f8dccc244e295da522658b626
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633565"
---
# <a name="documentview-creation"></a>Создание документа или представления

Среда .NET framework предоставляет реализации **New** и **откройте** команд (среди прочего) на **файл** меню. Создание документа и его связанного представления и окна фрейма не координированное усилий среди объект приложения, шаблон документа, вновь созданных документах и только что созданный фрейм окна. В следующей таблице перечислены объекты, которые создать новые.

### <a name="object-creators"></a>Средства создания объектов

|Создание|Создает|
|-------------|-------------|
|Объект Application|Шаблон документа|
|Шаблон документа|Document|
|Шаблон документа|Окна фрейма|
|Окна фрейма|Просмотр|

## <a name="see-also"></a>См. также

[Шаблоны документов и процесс создания документов и представлений](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](../mfc/document-template-creation.md)<br/>
[Отношения между объектами MFC](../mfc/relationships-among-mfc-objects.md)<br/>
[Создание документов, окон и представлений](../mfc/creating-new-documents-windows-and-views.md)

