---
title: Переопределение поставщика по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 106d1991f5312065aa78330888e55383d1f9506a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337022"
---
# <a name="overriding-provider-service-defaults"></a>Переопределение используемых по умолчанию параметров службы поставщика
Значение реестра поставщика для OLEDB_SERVICES возвращается как значение по умолчанию для [DBPROP_INIT_OLEDBSERVICES, установить](https://msdn.microsoft.com/library/ms716898.aspx) свойство инициализации на объекте источника данных.  
  
 Пока существует запись реестра, накапливаются объекты поставщика, и пользователь может переопределить поставщика по умолчанию для включенных служб, задав `DBPROP_INIT_OLEDBSERVICES` свойства до инициализации. Для включения или отключения определенной службы, пользователь обычно получает текущее значение `DBPROP_INIT_OLEDBSERVICES` свойства, задает или сбрасывает бит для конкретного свойства включить или отключить и свойство. `DBPROP_INIT_OLEDBSERVICES` можно задать непосредственно в OLE DB или в строке подключения, передаваемый ADO или `IDataInitialize::GetDatasource`. В следующей таблице перечислены соответствующие значения для включения или отключения отдельных служб.  
  
|Службы по умолчанию включен|Значение свойства DBPROP_INIT_OLEDBSERVICES, установить|Значение в строке подключения|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Все службы (по умолчанию)|`DBPROPVAL_OS_ENABLEALL`|«Службы OLE DB = -1;»|  
|Все, за исключением и автоматического зачисления|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|«Службы OLE DB = -4;»|  
|Все, кроме клиентский курсор|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|«Службы OLE DB = -5;»|  
|Все, кроме пулов, автоматического зачисления и клиентских курсоров|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|«Службы OLE DB = -7;»|  
|Нет служб|`~DBPROPVAL_OS_ENABLEALL`|«Службы OLE DB = 0;»|  
  
 Если запись реестра не существует для поставщика, диспетчеры компонентов не будет выполнять статистическую обработку объекты поставщика и службы не будет вызываться, даже если это явно запрошено пользователем.  
  
## <a name="see-also"></a>См. также  
 [Создание пулов ресурсов](https://msdn.microsoft.com/library/ms713655.aspx)   
 [Как потребители используют Создание пулов ресурсов](https://msdn.microsoft.com/library/ms715907.aspx)   
 [Как поставщики эффективно работают с пулами ресурсов](https://msdn.microsoft.com/library/ms714906.aspx)   
 [Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)