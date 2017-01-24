---
title: "Класс CDataConnection | Microsoft Docs"
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
  - "ATL::CDataConnection"
  - "ATL.CDataConnection"
  - "CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection - класс"
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CDataConnection
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управление соединение с источником данных.  
  
## Синтаксис  
  
```  
class CDataConnection  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Конструктор.  Создает и инициализирует объект `CDataConnection`.|  
|[Копировать](../../data/oledb/cdataconnection-copy.md)|Создает копию существующего подключения данных.|  
|[Откройте .](../../data/oledb/cdataconnection-open.md)|Открытие соединения с источником данных с помощью строки инициализации.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Открывает новый сеанс в текущем соединении.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool.md)|Определяет, является ли текущий сеанс открыт или нет.|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Определяет, является ли текущий сеанс открыт или нет.|  
|[оператор CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Возвращает ссылку на объект, который содержит `CDataSource`.|  
|[оператор CDataSource\*](../Topic/CDataConnection::operator%20CDataSource*.md)|Возвращает указатель на объект, который содержит `CDataSource`.|  
|[оператор CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)|Возвращает ссылку на объект, который содержит `CSession`.|  
|[оператор CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)|Возвращает указатель на объект, который содержит `CSession`.|  
  
## Заметки  
 `CDataConnection` полезный класс для создания клиентов, поскольку он инкапсулирует необходимые объекты \(источник данных\) и сеанс и часть работы необходимо сделать при подключении к источнику данных  
  
 Без `CDataConnection`, необходимо создать объект `CDataSource`, вызов метода [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md), то для создания экземпляра объекта [CSession](../../data/oledb/csession-class.md), вызов метода [Открыть](../../data/oledb/csession-open.md), то для создания объекта [CCommand](../../data/oledb/ccommand-class.md) и вызов его методов **Открыть**\*.  
  
 С `CDataConnection`, необходимости создания объекта соединения, передать ему строку инициализации, а затем использовать это подключение к открытым команд.  Если планируется использовать на подключение к базе данных повторно, то рекомендуется поместить хранить подключения открытым и `CDataConnection` обеспечивает удобную задачи два списка.  
  
> [!NOTE]
>  При создании приложения баз данных, который необходимо обрабатывать несколько сеансов, необходимо использовать [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)