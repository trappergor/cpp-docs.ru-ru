---
title: "Переопределение используемых по умолчанию параметров службы поставщика | Microsoft Docs"
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
  - "службы OLE DB [OLE DB], переопределение параметров по умолчанию"
  - "поставщики служб [OLE DB]"
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Переопределение используемых по умолчанию параметров службы поставщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Значение раздела реестра **OLEDB\_SERVICES** поставщика возвращается в качестве значения по умолчанию для свойства инициализации [DBPROP\_INIT\_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) объекта источника данных.  
  
 В течение всего времени существования раздела реестра объекты поставщика находятся в агрегированном состоянии. В этом случае пользователь может переопределить используемые по умолчанию параметры включенных служб поставщика, устанавливая свойство **DBPROP\_INIT\_OLEDBSERVICES** до инициализации.  Чтобы включить или отключить конкретную службу, следует получить текущее значение свойства **DBPROP\_INIT\_OLEDBSERVICES**, установить или обнулить бит для включения или отключения конкретного свойства, а затем сбросить свойство.  Свойство **DBPROP\_INIT\_OLEDBSERVICES** можно установить непосредственно в OLE DB, а также в строке подключения, передаваемой в объект ADO или метод **IDataInitialize::GetDatasource**.  В следующей таблице приведены значения, используемые для включения и отключения отдельных служб.  
  
|Включенные по умолчанию службы|Значение свойства DBPROP\_INIT\_OLEDBSERVICES|Значение в строке подключения|  
|------------------------------------|---------------------------------------------------|-----------------------------------|  
|Все службы \(по умолчанию\)|**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= \-1;"|  
|Все, за исключением служб заполнения и автоматического зачисления|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT**|"OLE DB Services \= \-4;"|  
|Все, за исключением службы клиентских курсоров|**DBPROPVAL\_OS\_ENABLEALL**&<br /><br /> ~**DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-5;"|  
|Все, за исключением служб регулирования количества запросов, автоматического зачисления и клиентских курсоров|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-7;"|  
|Все службы отключены|~**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= 0;"|  
  
 Если раздел реестра для поставщика не существует, объекты поставщика не агрегируются с помощью диспетчеров компонентов, в результате чего службы не вызываются даже в случае явного запроса со стороны пользователя.  
  
## См. также  
 [Resource Pooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [How Consumers Use Resource Pooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [How Providers Work Effectively with Resource Pooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)