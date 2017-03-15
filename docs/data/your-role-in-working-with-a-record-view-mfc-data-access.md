---
title: "Роль пользователя в работе с представлением записи (доступ к данным MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, представления записей"
  - "представления записей, настройка кода по умолчанию"
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Роль пользователя в работе с представлением записи (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующая таблица показывает, что обычно необходимо сделать, чтобы работать с представлением записи и что платформа делает за вас.  
  
### Работа с представлением записи: Вы и платформа  
  
|Вы|Платформа|  
|--------|---------------|  
|Используйте редактор диалоговых окон Visual C\+\+ для разработки формы.|Создает ресурс шаблона диалоговых окон с элементами управления.|  
|Используйте [мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) для создания классов, производных из класса [CRecordset](../mfc/reference/crecordview-class.md)и [CRecordView](../mfc/reference/crecordview-class.md) или из [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) и [CDaoRecordset](../mfc/reference/cdaorecordset-class.md).|Создает классы за вас.|  
|Сопоставление элементов управления представления записи с элементами данных полей набора записей.|Обеспечивает обмен данных между элементами управления и полями набора записей.|  
||Предоставляет обработчиков команд по умолчанию для команд **Переместить первый**, **переместить последний**, **переместить следующий** и **переместить предыдущий**из меню или кнопок панели инструментов.|  
||Сохраняет изменения в источнике данных|  
|\[Дополнительно\] Напишите код для заполнения списка или поля со списком или других элементов управления данными из второго набора записей.||  
|\[Дополнительно\] Написание кода необязательно.||  
|\[Дополнительно\] Напишите код для добавления и удаления записей.||  
  
 Программирование на основе формы является только одним подходом в работе с базой данных.  Для информации о приложениях, использующих другие интерфейсы пользователя, или без интерфейса пользователя, см. [MFC:](../data/mfc-using-database-classes-with-documents-and-views.md)[](../data/mfc-using-database-classes-with-documents-and-views.md "MFC: Using Database Classes with Documents and Views")[Использование классов базы данных с документами и представлениями](../data/mfc-using-database-classes-with-documents-and-views.md) и [MFC](../data/mfc-using-database-classes-without-documents-and-views.md). [](../data/mfc-using-database-classes-without-documents-and-views.md "MFC: Using Database Classes Without Documents and Views")[Использование классов базы данных без документов и представлений](../data/mfc-using-database-classes-without-documents-and-views.md) Об альтернативных подходах к отображению записей базы данных см. классы [CListView](../mfc/reference/clistview-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md).  
  
## См. также  
 [Представления записей \(доступ к данным MFC\)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)