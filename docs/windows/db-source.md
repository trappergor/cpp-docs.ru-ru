---
title: "db_source | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18c4a4af3f8df4e3af5f6aae8f6643db553c7373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dbsource"></a>db_source
Создает подключение к источнику данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *db_source*  
 Строка подключения, используемая для подключения к источнику данных. Формат строки подключения, в разделе [строки соединения и ссылки на данные](https://msdn.microsoft.com/en-us/library/ms718376.aspx) в Microsoft данных Access Components (MDAC) SDK.  
  
 *name* (необязательно)  
 При использовании `db_source` в классе, *имя* экземпляр объекта источника данных, который имеет `db_source` атрибут, применяемый к нему (см. в примере 1). При использовании `db_source` , встроенный в реализации метода, *имя* является переменной (локальный метода), которая может использоваться для доступа к данным источника (см. Пример 2). Передать этот *имя* для `source_name` параметр **db_command** для связи с источником данных с помощью команды.  
  
 `hresult` (необязательно)  
 Определяет переменную, которая будет получать `HRESULT` этой команды базы данных. Если переменная не существует, она будет автоматически внедрена с помощью атрибута.  
  
## <a name="remarks"></a>Примечания  
 `db_source`Создает [CDataSource](../data/oledb/cdatasource-class.md) и [CSession](../data/oledb/csession-class.md) объекта, которые вместе представляют соединения с источником данных потребитель OLE DB.  
  
 При использовании `db_source` в классе, `CSession` объект становится членом класса.  
  
 При использовании `db_source` в методе, этот код выполняется в области метода и `CSession` объект создается как локальная переменная.  
  
 `db_source`Добавляет свойства источника данных для класса или метода. Он используется в сочетании с **db_command** (который принимает `db_source` *имя* параметра, как его `source_name` параметр).  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
 Пример этого атрибута, используемого в приложении, см. в примерах [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) и [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="example"></a>Пример  
 В этом примере вызываются `db_source` для класса, чтобы создать подключение к источнику данных `ds` с помощью базы данных Northwind. `ds`— Это дескриптор для источника данных, который может использоваться внутренне в `CMyCommand` класса.  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`, member, method, local|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)   
