---
title: Создание представления документа
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
ms.openlocfilehash: 5441827188f5bff98638cc85cd29e2efd79f8ae8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620344"
---
# <a name="documentview-creation"></a>Создание документа или представления

Платформа предоставляет реализации команд **New** и **Open** (из других) в меню **файл** . Создание нового документа и связанного с ним представления и окна фрейма — это совместная работа между объектом приложения, шаблоном документа, вновь созданным документом и вновь созданным окном фрейма. В следующей таблице приводятся сводные сведения о том, какие объекты создают.

### <a name="object-creators"></a>Создатели объектов

|Автор|Приводит|
|-------------|-------------|
|Объект приложения|Шаблон документа|
|Шаблон документа|Document|
|Шаблон документа|Окно фрейма|
|Окно фрейма|Просмотр|

## <a name="see-also"></a>См. также раздел

[Шаблоны документов и процесс создания документа/представления](document-templates-and-the-document-view-creation-process.md)<br/>
[Создание шаблонов документов](document-template-creation.md)<br/>
[Связи между объектами MFC](relationships-among-mfc-objects.md)<br/>
[Создание новых документов, окон и представлений](creating-new-documents-windows-and-views.md)
