---
title: "Классы общих диалоговых окон OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0617354337e75e2c2431df894c054722349e2306
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-common-dialog-classes"></a>Классы общих диалоговых окон OLE
Эти классы обрабатывают общие задачи OLE путем реализации ряд стандартных диалоговых окон OLE. Они также обеспечивают функциональные возможности OLE единый пользовательский интерфейс.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Используется платформой для хранения типичные реализации всех диалоговых окон OLE. Все классы диалоговых окон в категории пользовательского интерфейса являются производными от этого базового класса. `COleDialog`нельзя использовать напрямую.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Отображает диалоговое окно «Вставить объект», стандартный пользовательский интерфейс для вставки новых OLE связанных или внедренных элементов.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Отображает диалоговое окно Специальная вставка стандартный пользовательский интерфейс для реализации команду Специальная вставка.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Отображает диалоговое окно «Изменить ссылки», стандартный пользовательский интерфейс для изменения сведений о связанных элементах.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Отображает диалоговое окно Изменение значка, стандартный пользовательский интерфейс для изменения значок, связанный с OLE-внедренные или связанный элемент.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Отображает диалоговое окно Convert, стандартный пользовательский интерфейс для преобразования OLE-элементы из одного типа в другой.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Инкапсулирует общих свойств OLE диалоговым окном Windows. Общие диалоговые окна свойств OLE предоставляют простой способ отображения и изменения свойств элемента документа OLE в соответствии со стандартами Windows.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Отображает диалоговое окно обновления, стандартный пользовательский интерфейс для обновления всех ссылок в документе. Диалоговое окно содержит индикатор выполнения указывает, насколько близко процедуру обновления для завершения.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Отображает диалоговое окно Изменение источника, стандартный пользовательский интерфейс для изменения назначения и источника связи.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Отображает сервер занят диалоговые окна и сервер не отвечает, стандартный пользовательский интерфейс для обработки вызовов занят приложений. Обычно отображается автоматически `COleMessageFilter` реализации.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

