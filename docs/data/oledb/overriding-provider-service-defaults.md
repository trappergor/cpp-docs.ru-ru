---
title: "Переопределение параметров по умолчанию для поставщика службы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9185f1eb3640a4baeb8f7cc1d7b20169c980a8e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-provider-service-defaults"></a>Переопределение используемых по умолчанию параметров службы поставщика
Значение реестра поставщика для **OLEDB_SERVICES** возвращается как значение по умолчанию для [DBPROP_INIT_OLEDBSERVICES, установить](https://msdn.microsoft.com/en-us/library/ms716898.aspx) свойство инициализации объекта источника данных.  
  
 Пока существует запись реестра, статистически обрабатывается объекты поставщика, и пользователь может переопределить поставщика по умолчанию для службы включена, задав **DBPROP_INIT_OLEDBSERVICES, установить** свойства до инициализации. Чтобы включить или отключить конкретную службу, пользователь обычно получает значение текущей **DBPROP_INIT_OLEDBSERVICES, установить** , задает или удаляет бит для конкретного свойства включить или отключить и сбрасывает свойство. **DBPROP_INIT_OLEDBSERVICES, установить** можно задать непосредственно в OLE DB или в строке подключения, передаваемый ADO или **IDataInitialize::GetDatasource**. В следующей таблице перечислены соответствующие значения для включения или отключения отдельных служб.  
  
|Включены службы по умолчанию|DBPROP_INIT_OLEDBSERVICES, установить значение свойства|Значение в строке подключения|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Все службы (по умолчанию)|**DBPROPVAL_OS_ENABLEALL**|«Службы OLE DB = -1;»|  
|Все, за исключением и автоматического зачисления|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~ DBPROPVAL_OS_RESOURCEPOOLING &**<br /><br /> **~ DBPROPVAL_OS_TXNENLISTMENT**|«Службы OLE DB = -4;»|  
|Все, кроме клиентских курсоров|**DBPROPVAL_OS_ENABLEALL** &<br /><br /> ~**DBPROPVAL_OS_CLIENTCURSOR**|«Службы OLE DB = -5;»|  
|Все, кроме пулов автоматического зачисления и клиентских курсоров|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~ DBPROPVAL_OS_TXNENLISTMENT &**<br /><br /> **~ DBPROPVAL_OS_CLIENTCURSOR**|«Службы OLE DB = -7;»|  
|Нет служб|~**DBPROPVAL_OS_ENABLEALL**|«Службы OLE DB = 0;»|  
  
 Если параметр реестра не существует для поставщика, диспетчеры компонентов не будет выполнять статистическую обработку объекты поставщика и службы не будет вызываться, даже если это явно запрошено пользователем.  
  
## <a name="see-also"></a>См. также  
 [Создание пулов ресурсов](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [Как потребители создания пулов ресурсов](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [Как поставщики эффективно работают с Создание пулов ресурсов](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)