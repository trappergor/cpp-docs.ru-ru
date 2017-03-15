---
title: "Представления записей (доступ к данным MFC) | Microsoft Docs"
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
  - "DAO [C++], представления записей"
  - "базы данных [C++], представления записей"
  - "формы [C++], задачи доступа к данным"
  - "MFC [C++], представления записей"
  - "наборы записей ODBC [C++], представления записей"
  - "представления записей [C++]"
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Представления записей (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот раздел относится только к классам MFC ODBC и DAO.  Дополнительные сведения о представлениях записей OLE DB см. [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) и [представления записей OLE DB](../data/oledb/using-ole-db-record-views.md).  
  
 Для поддержки приложений доступа к данным на основе формы, библиотека классов предоставляет классы [CRecordView](../mfc/reference/crecordview-class.md) и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  Представление записей — это сформированный объект представления, элементы управления которого напрямую сопоставлены с элементами данных полей [набор записей](../data/odbc/recordset-odbc.md) объекта \(и косвенно сопоставляются соответствующим столбцам в результате запроса или в таблице из источника данных\).  Как и базовый класс [CFormView](../mfc/reference/cformview-class.md), `CRecordView` и `CDaoRecordView` основаны на ресурсе шаблона диалогового окна.  
  
## Использование форм  
 Формы полезны для различных задач доступа к данным:  
  
-   Ввод данных  
  
-   Выполнение анализа данных только для чтения  
  
-   Обновление данных  
  
## Дополнительные сведения о представлениях записей  
 Материалы в следующих разделах относятся к классам и на основе ODBC и на основе DAO .  Использование `CRecordView` для ODBC и `CDaoRecordView` для DAO.  
  
 Ниже приведен список разделов.  
  
-   [Функции классов представлений записей](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [Обмен данными в представлениях записей](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [Роль пользователя в работе с представлением записи](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [Разработка и создание представления записей](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)  
  
## См. также  
 [Программирование доступа к данным \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)