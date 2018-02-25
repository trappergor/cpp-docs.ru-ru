---
title: "Ссылка на шаблоны поставщика OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68c741f09772c881b42dc4e4cd17de31ed107f8c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-provider-templates-reference"></a>Ссылка на шаблоны поставщика OLE DB
Классы и интерфейсы для шаблонов поставщика OLE DB могут быть сгруппированы в следующие категории. Справочные материалы также включает информацию о [макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Классы используют следующее соглашение об именовании: класс с именем с шаблоном **IWidgetImpl** бы предоставить реализацию интерфейса **IWidget**.  
  
## <a name="session-classes"></a>Классы сеансов  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на только что созданного сеанса. Обязательный интерфейс для объектов источника данных.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Реализует свойства сеанса, вызвав статическую функцию, определяемую сопоставление набора свойств. Сопоставление набора свойств должен быть указан в классе сеанса. Обязательный интерфейс для сеансов.  
  
## <a name="rowset-classes"></a>Классы набора строк  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Предоставляет стандартную реализацию набора строк OLE DB без необходимости множественное наследование многие реализации интерфейсов. Это единственный метод, для которого необходимо предоставить реализация **Execute**.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Предоставляет реализацию по умолчанию для дескриптора строки, которая используется в `IRowsetImpl` класса. Дескриптор строки логически представляет собой уникальный тег для строки результата. `IRowsetImpl` Создает новый `CSimpleRow` для запрашиваемого каждой строки в `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB требует, чтобы реализовать поставщики **HACCESSOR**, являющееся тег в массив **DBBINDING** структуры. Предоставляет **HACCESSOR**, которые адреса **BindType** структуры. Обязателен для наборов строк и команд.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Делегаты статическую функцию, определяемую сопоставления столбца поставщика. Обязательный интерфейс для наборов строк и команд.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Сведения о доступности преобразований типа команды или для набора строк. Обязателен для наборов строк, команды и наборы строк индекса. Реализует **IConvertType** интерфейса делегирование для преобразования объекта, заданного параметром OLE DB.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Реализует **IDBSchemaRowset** интерфейс и шаблонизируемую функцию создателя `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. Обязательный интерфейс для объекта сеанса.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Реализует OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) интерфейс, позволяющий обновления значений столбцов в существующих строках, удаление строк и вставки новых строк.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Этот класс наследует от [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) и переопределяет [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl` выполняет те же функции, как `IObjectWithSite` , но и обеспечивает свойства OLE DB **DBPROPCANSCROLLBACKWARDS** и **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Реализует **IRowsetIdentity** интерфейс, который позволяет сравнивать ли две строки данных идентичны, или нет.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 Предоставляет реализацию `IRowset` интерфейс, который имеет базовый интерфейс набора строк.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Реализует свойства набора строк с помощью свойства задать карты, определенные в классе команд. Обязательный интерфейс для наборов строк.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Реализует OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) интерфейс, который извлекает строки из набора строк. Поддерживает закладки OLE DB в наборе строк, чтобы наследовать от этого класса набора строк.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Реализует широковещательных функции для в точке подключения **IID_IRowsetNotify** изменений содержимого набора строк. Объекты-получатели, обрабатывать уведомления реализовать [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) и зарегистрируйте его на эту точку подключения.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 Реализует OLE DB [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) для источника данных и отменить изменения перед их отправкой.  
  
## <a name="command-classes"></a>Командные классы  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 Предоставляет реализацию интерфейса `ICommand`. Этот интерфейс не отображается, но обрабатывается **ICommandTextImpl**. Обязательный интерфейс для объекта команды.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Эта реализация **ICommandProperties** интерфейс, предоставляемый статическую функцию, определяемую `BEGIN_PROPSET_MAP` макрос. Обязателен для команды.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Задает, сохраняет и возвращает текст команды. Обязателен для команды.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Создание новой команды из объекта сеанса и возвращает запрошенный интерфейс на созданная команда. Дополнительный интерфейс для объектов сеанса.  
  
 Другие команды классы являются `IColumnsInfoImpl` и `IAccessorImpl`, описанных в предыдущем разделе классы набора строк.  
  
## <a name="data-source-classes"></a>Классы источника данных  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 Создает и удаляет соединения с потребителем. Обязательный интерфейс для объектов источников данных и дополнительный интерфейс для перечислителей.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` — обязательный интерфейс для объектов источников данных и дополнительный интерфейс для перечислителей. Тем не менее если перечислитель предоставляет **IDBInitialize**, он должен предоставлять `IDBProperties` (свойства в источнике данных).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Получает указатель интерфейса на объект источника данных. Обязательный интерфейс для сеанса.  
  
## <a name="other-classes"></a>Другие классы  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Реализует свойства для различных свойств интерфейсы OLE DB (например, `IDBProperties`, **ISessionProperties**, и `IRowsetInfo`).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Реализует OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) интерфейс, добавление записей, а также получение записей из элемента данных.  
  
## <a name="see-also"></a>См. также  
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)