---
title: "CMyProviderSession (MyProviderSess.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyprovidersession"
  - ""myprovidersess.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSession - класс (MyProviderSess.H)"
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSession (MyProviderSess.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MyProviderSess.H содержит объявление и реализацию объекта сеанса OLE DB.  Объект источника данных создает объект сеанса и представляет собой своеобразный "диалог" между потребителем и поставщиком.  Для одного источника данных можно открыть несколько одновременных сеансов.  Список наследования для сеанса `CMyProviderSession` приведен ниже.  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 Объект сеанса наследует от источника **IGetDataSource**, набора строк `IOpenRowset`, свойств **ISessionProperties** и команды **IDBCreateCommand**.  Интерфейс **IGetDataSource** позволяет сеансу извлекать создавший его источник данных.  Это очень удобно, когда требуется получить свойства из созданного источника данных или другую информацию, которую может предоставить этот источник.  Интерфейс **ISessionProperties** обрабатывает все свойства сеанса.  Интерфейсы `IOpenRowset` и **IDBCreateCommand** служат для работы с базами данных.  Если поставщик поддерживает команды, в нем реализуется интерфейс **IDBCreateCommand**.  Он создает объект команды, способный выполнять команды.  Поставщик всегда реализует объект `IOpenRowset`.  Он используется для создания простого набора строк из поставщика.  Это стандартный набор строк \(например, `"select * from mytable"`\) из поставщика.  
  
 Кроме того, мастер создает три класса сеансов: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema` и `CMyProviderSessionTRSchema`.  Эти сеансы используются для наборов строк схемы.  Наборы строк схемы позволяют поставщику возвращать метаданные потребителю без необходимости запроса или выборки данных этим потребителем.  Выборка метаданных может оказаться гораздо более быстрым процессом, чем изучение возможностей поставщика.  
  
 Спецификация OLE DB требует, чтобы поставщики, реализующие интерфейс **IDBSchemaRowset**, поддерживали три типа наборов строк схемы: **DBSCHEMA\_COLUMNS**, **DBSCHEMA\_PROVIDER\_TYPES** и `DBSCHEMA_TABLES`.  Мастер создает реализации для каждого набора строк схемы.  Все классы, созданные мастером, содержат метод `Execute`.  Этот метод `Execute` позволяет возвращать поставщику данные о том, какие таблицы, столбцы и типы данных поддерживаются.  Обычно эти данные доступны на стадии компиляции.  
  
## См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)