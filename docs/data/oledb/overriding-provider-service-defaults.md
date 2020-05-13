---
title: Переопределение используемых по умолчанию параметров службы поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
ms.openlocfilehash: 4cf3ad1064627f64315822a5045642aa50330d10
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209817"
---
# <a name="overriding-provider-service-defaults"></a>Переопределение используемых по умолчанию параметров службы поставщика

Значение реестра поставщика для OLEDB_SERVICES возвращается в качестве значения по умолчанию для свойства инициализации [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898(v=vs.85)) объекта источника данных.

Пока запись реестра существует, объекты поставщика суммируются. Пользователь может переопределить параметр поставщика по умолчанию для включенных служб, установив свойство DBPROP_INIT_OLEDBSERVICES перед инициализацией. Чтобы включить или отключить определенную службу, пользователь получает текущее значение свойства DBPROP_INIT_OLEDBSERVICES, устанавливает или снимает бит для конкретного свойства, который должен быть включен или отключен, и сбрасывает свойство. DBPROP_INIT_OLEDBSERVICES можно задать непосредственно в OLE DB или в строке подключения, передаваемой ADO или `IDataInitialize::GetDatasource`. Соответствующие значения для включения или отключения отдельных служб перечислены в следующей таблице.

|Службы по умолчанию включены|DBPROP_INIT_OLEDBSERVICES значение свойства|Значение в строке подключения|
|------------------------------|------------------------------------------------|--------------------------------|
|Все службы (по умолчанию)|DBPROPVAL_OS_ENABLEALL|"OLE DB Services =-1;"|
|Все, кроме пулов и автоматического прикрепления|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB Services =-4;"|
|Все, кроме клиентского курсора|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Services =-5;"|
|Все, кроме пулов, автоматического прикрепления и клиентского курсора|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Services =-7;"|
|Нет служб|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB Services = 0;"|

Если запись реестра не существует для поставщика, диспетчеры компонентов не собираются объекты поставщика. Службы не будут включены, даже если они были явно запрошены пользователем.

## <a name="see-also"></a>См. также раздел

[Создание пулов ресурсов](/previous-versions/windows/desktop/ms713655(v=vs.85))<br/>
[Как потребители используют пулы ресурсов](/previous-versions/windows/desktop/ms715907(v=vs.85))<br/>
[Эффективное взаимодействие поставщиков с пулами ресурсов](/previous-versions/windows/desktop/ms714906(v=vs.85))<br/>
[Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>
