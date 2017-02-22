---
title: "Программирование доступа к данным (MFC/ATL) | Microsoft Docs"
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
  - "данные [C++], технологии доступа к данным"
  - "доступ к данным [C++], библиотеки классов для баз данных"
  - "базы данных [C++], MFC"
  - "MFC [C++], приложения доступа к данным"
  - "OLE DB [C++], технологии доступа к данным"
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Программирование доступа к данным (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ предоставляет несколько способов работы с базами данных.  Предпочтительным способом является использование одной из библиотек классов, например Active Template Class Library \(ATL\) или библиотеки Microsoft Foundation Class \(MFC\), которые упрощают работу с API базы данных.  
  
> [!NOTE]
>  В этом разделе рассматриваются более старые технологии, которые можно использовать для программирования в Visual C\+\+.  Сведения о программировании доступа к данным на языке Visual C\+\+ и SQL Server 2005 см [Доступ к данным](../dotnet/data-access-using-adonet-cpp-cli.md), [Доступ к данным в Visual Studio](../Topic/Accessing%20data%20in%20Visual%20Studio.md), и [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ru-ru/5358a825-e19b-49aa-8214-674ce5fed1da).  
  
 Классы библиотек поддерживают следующие виды доступа к данным:  
  
-   Библиотека ATL предоставляет шаблоны OLE DB и атрибуты базы данных.  
  
-   MFC предоставляет подключения Open Database Connectivity \(ODBC\) и драйвер ODBC.  
  
 Эти библиотеки содержат абстракции, которые упрощают работу с базами данных, сочетая скорость, мощность и гибкость C\+\+.  Они интегрируют работу по доступу к данным с платформой приложения библиотеки.  
  
 Кроме того, можно напрямую вызвать API\-функции базы данных  из комплектов разработки программного обеспечения \(SDK\) COM, ODBC или DAO.  Сведения о программировании с непосредственным использованием функций COM, DAO см. в COM SDK, DAO SDK, или ODBC SDK.  
  
 Если необходимо получить доступ к данным независимо от формы, в которой они хранятся, используется ATL OLE DB.  Используйте классы MFC ODBC, если не используются базы данных Microsoft Jet \(.mdb\)  и требуется работа с интерфейсом API ODBC для полной независимости от источника данных.  Используйте классы DAO библиотеки MFC для работы с базами данных Microsoft Jet \(.mdb\) или внешними базами данных, такими как источники данных ODBC.  
  
> [!NOTE]
>  Корпорация Майкрософт рекомендует использовать OLE DB или ODBC для новых проектов.  DAO следует использовать только для поддержки существующих приложений.  
  
 Помимо написания автономных приложений баз данных, часто можно использовать базу данных эффективно в других типах программ, как удобную среду хранения и извлечения данных.  
  
|Для получения дополнительных сведений о|См.|  
|---------------------------------------------|---------|  
|**Выбор технологии базы данных**||  
|ODBC против  DAO|[Использовать DAO или ODBC?](../data/should-i-use-dao-or-odbc-q.md)|  
|Использование базы знаний Майкрософт для поиска дополнительных статей по базам данных, написанных специалистами службы поддержки продукта|[База знаний Майкрософт](../data/where-can-i-find-microsoft-knowledge-base-articles-on-database-topics-q.md)|  
|**Поддержка баз данных ATL \(OLE DB\)**||  
|Программирования в OLE DB \(основные разделы\)|[Общие сведения о программировании OLE DB](../data/oledb/ole-db-programming-overview.md)|  
|Использование пользовательских шаблонов OLE DB \(основные разделы\)|[шаблоны потребителя OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md)|  
|Атрибуты пользователя OLE DB|[Атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md)|  
|Использование шаблонов поставщика OLE DB \(основные разделы\)|[Шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-cpp.md)|  
|Добавление в проект MFC пользователя OLE DB|[Создание объекта\-получателя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)|  
|**Поддержка базы данных  MFC \(ODBC и DAO\)**||  
|Что такое DAO и ODBC|[Что такое DAO и ODBC?](../data/what-are-dao-and-odbc-q.md)|  
|Когда следует использовать классы баз данных MFC|[В каких случаях следует использовать классы баз данных?](../data/when-should-i-use-the-database-classes-q.md)|  
|Дополнительные сведения о модели программирования базы данных MFC|[Модель программирования базы данных MFC](../data/what-is-the-mfc-database-programming-model-q.md)|  
|Выбор между классами MFC DAO и классам ODBC библиотеки MFC|[Использовать DAO или ODBC?](../data/should-i-use-dao-or-odbc-q.md)|  
|Источники данных, доступные через DAO и ODBC|[Источники данных, которые можно подключить к DAO и ODBC](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)|  
|Интерфейс ODBC \(ODBC\)|[ODBC и MFC](../data/odbc/odbc-and-mfc.md)|  
|Можно ли вызвать DAO или ODBC API напрямую при использовании классов|[Допустимость непосредственного вызова объектов DAO или ODBC](../data/can-i-call-dao-or-odbc-directly-q.md)|  
|Какие драйверы ODBC предоставляются|[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)|  
|Как работают классы базы данных с архитектурой документ\/представление MFC|[MFC. Использование классов базы данных с документами и представлениями](../data/mfc-using-database-classes-with-documents-and-views.md)|  
|Установка поддержки базы данных MFC ; какие драйверы ODBC установлены в Visual C\+\+ по умолчанию; какие установлены компонентов ODBC и DAO SDK|[Установка поддержки баз данных MFC](../data/installing-mfc-database-support.md)|  
|**Элементы управления, связанные с данными \(ADO и RDO\)**||  
|Написание программы, которая использует элементы управления с привязкой к данным|[Элементы управления, связанные с данными \(ADO и RDO\)](../Topic/Data-Bound%20Controls%20\(ADO%20and%20RDO\).md)|  
|Привязка данных с помощью элементов управления ActiveX|[Элементы управления ActiveX в MFC. Использование привязки данных в элементе управления ActiveX](../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)|  
|Распространение элементов управления ActiveX|[Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX](../mfc/mfc-activex-controls-distributing-activex-controls.md)|  
  
## См. также  
 [Доступ к данным](../Topic/Data%20Access%20in%20Visual%20C++.md)