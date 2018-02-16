---
title: "Класс CDataConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a891052b4fa92f6f642cdab89aadf444ec4d8475
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnection-class"></a>Класс CDataConnection
Управляет соединение с источником данных.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDataConnection  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|Конструктор. Создает и инициализирует `CDataConnection` объекта.|  
|[Копировать](../../data/oledb/cdataconnection-copy.md)|Создает копию существующего соединения с данными.|  
|[Открыть](../../data/oledb/cdataconnection-open.md)|Открывает соединение с источником данных с помощью строки инициализации.|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|Открывает новый сеанс для текущего соединения.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[Operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)|Определяет, открыт ли в текущем сеансе, или нет.|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|Определяет, открыт ли в текущем сеансе, или нет.|  
|[оператор CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|Возвращает ссылку на содержащиеся в нем `CDataSource` объекта.|  
|[оператор CDataSource *](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|Возвращает указатель на содержащиеся в нем `CDataSource` объекта.|  
|[оператор CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|Возвращает ссылку на содержащиеся в нем `CSession` объекта.|  
|[оператор CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|Возвращает указатель на содержащиеся в нем `CSession` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CDataConnection` Класс особенно полезен для создания клиентов, так как он инкапсулирует необходимых объектов (источника данных и сеанса) и некоторых операций, которые необходимо выполнить при подключении к источнику данных  
  
 Без `CDataConnection`, необходимо создать `CDataSource` , вызовите его [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) метод, затем создайте экземпляр класса [CSession](../../data/oledb/csession-class.md) , вызовите его [ Откройте](../../data/oledb/csession-open.md) метод, затем создайте [CCommand](../../data/oledb/ccommand-class.md) и вызовите его **откройте*** методы.  
  
 С `CDataConnection`, требуется только создать объект подключения, передавая ей строку инициализации, а затем использовать это подключение для открытия команд. Если планируется повторно использовать подключение к базе данных, рекомендуется закрывать соединение и `CDataConnection` предоставляет удобный способ сделать это.  
  
> [!NOTE]
>  Если вы создаете приложение базы данных, который должен обрабатывать несколько сеансов, необходимо использовать [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)