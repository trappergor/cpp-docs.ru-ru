---
title: "Использование представления записей (доступ к данным MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "представления записей, настройка кода по умолчанию"
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование представления записей (доступ к данным MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе объясняется, как настроить код по умолчанию для представлений записей, создаваемых мастером для вас.  Как правило требуется ограничить выбор записей с помощью [фильтр](../data/odbc/recordset-filtering-records-odbc.md) или [параметры](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), возможно[отсортировать](../data/odbc/recordset-sorting-records-odbc.md) записи, настроить инструкцию SQL.  
  
 Эти сведения применимы как к [CRecordView](../mfc/reference/crecordview-class.md) \(ODBC\) так и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) \(DAO\).  
  
 Использование `CRecordView` или `CDaoRecordView` похоже на использование [CFormView](../mfc/reference/cformview-class.md).  Основной подход заключается в использовании представления записей для отображения и возможно, обновления записей одного определенного набора записей.  Кроме этого, может возникнуть необходимость использования других наборов записей, как описано в [Представления записей](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).[](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md "Filling a List Box from a Second Recordset  (MFC Data Access)")[Заполнение списка из второго набора записей](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)  
  
## См. также  
 [Представления записей \(доступ к данным MFC\)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)