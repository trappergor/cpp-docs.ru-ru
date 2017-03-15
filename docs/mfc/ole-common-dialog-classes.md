---
title: "Классы общих диалоговых окон OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX - классы [C++]"
  - "классы общих диалоговых окон"
  - "классы диалоговых окон [C++], OLE"
  - "классы общих диалоговых окон OLE [C++]"
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Классы общих диалоговых окон OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы отвечают OLE общие задачи путем реализации несколько стандартных OLE диалоговых окон.  Они также предоставляют согласованный интерфейс пользователя для функции OLE.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Используется средой выполнения для хранения общие реализации для всех OLE диалоговых окон.  Все классы диалогового окна в категории интерфейса пользователя являются производными от этого базового класса.  `COleDialog` нельзя использовать напрямую.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Отображает диалоговое окно объекта вставки, интерфейс обычного пользователя для вставки новых элементов OLE связанные или внедренные.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Отображает диалоговое окно для вставки, интерфейс обычного пользователя для реализации команду для вставки правки.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Отображает диалоговое окно ссылок правки, интерфейс обычного пользователя для изменения сведений о связанных элементов.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Отображает диалоговое окно Значка изменения, интерфейс обычного пользователя для изменения Значок, связанный с внедренным или OLE, связанные с элементом.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Отображает диалоговое окно преобразования, интерфейс обычного пользователя для преобразования элемент OLE из одного типа в другой.  
  
 [COlePropertiesDialog](../Topic/COlePropertiesDialog%20Class.md)  
 Инкапсулирует диалоговое окно свойств Windows общее OLE.  Общие диалоговые окна свойств OLE предоставляют простой способ отображения и изменения свойств OLE элемента документа способом последовательного стандартам Windows.  
  
 [COleUpdateDialog](../Topic/COleUpdateDialog%20Class.md)  
 Отображает диалоговое окно обновление, интерфейс обычного пользователя для обновления всех ссылок в документе.  Диалоговое окно содержит индикатор выполнения, показывающий, как закрыть процедура обновления до завершения.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Отображает диалоговое окно источника изменения, интерфейс для обычного пользователя изменить назначение или источник ссылки.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Отображает сервер Занят и сервера не отвечающий диалоговые окна, интерфейс обычного пользователя для обработки вызовы занято приложения.  Обычно отображается автоматически реализацией `COleMessageFilter`.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)