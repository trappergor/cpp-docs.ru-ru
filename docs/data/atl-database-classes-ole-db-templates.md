---
title: "Классы баз данных библиотеки ATL (шаблоны OLE DB) | Microsoft Docs"
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
  - "классы баз данных [C++], ATL - библиотека"
  - "классы баз данных [C++], OLE DB"
  - "шаблоны OLE DB [C++], ATL-классы баз данных"
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Классы баз данных библиотеки ATL (шаблоны OLE DB)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Майкрософт предоставляет несколько реализаций OLE DB — набора COM\-интерфейсов, обеспечивающих единообразный доступ к данным в разных форматах из разнообразных информационных источников.  
  
 Шаблоны OLE DB являются шаблонами C\+\+ библиотеки ATL, упрощающими использование высокопроизводительной технологии баз данных OLE DB путем предоставления классов, реализующих многие наиболее часто используемые интерфейсы OLE DB.  
  
 Библиотека шаблонов состоит из двух частей:  
  
-   [Шаблоны потребителей OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) Предназначены для реализации клиентских приложений OLE DB \(потребителей\).  
  
-   [Шаблоны поставщиков OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) Предназначены для реализации серверных приложений OLE DB \(поставщиков\).  
  
 Кроме того, [атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md) предоставляют удобный механизм создания потребителей OLE DB.  С помощью атрибутов OLE DB в программу вводится основанный на шаблонах потребителей OLE DB код, который используется для создания рабочих потребителей OLE DB.  
  
 Обратите внимание, что библиотека MFC содержит класс [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), который предназначен для отображения записей базы данных в элементах управления.  Отображение реализуется с помощью формы, которая непосредственно связана с объектом `CRowset` и отображает поля объекта `CRowset` в элементах управления шаблона диалогового окна.  
  
 Дополнительные сведения см. в разделе [Программирование OLE DB](../data/oledb/ole-db-programming.md) и [Руководство программиста OLE DB](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## См. также  
 [Создание объекта\-получателя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)   
 [Создание поставщика OLE DB](../data/oledb/creating-an-ole-db-provider.md)   
 [Ссылка на шаблоны потребителя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)   
 [Ссылка на шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Templates Samples](http://msdn.microsoft.com/ru-ru/08958863-0b5f-41ad-ae99-fca7440c553c)