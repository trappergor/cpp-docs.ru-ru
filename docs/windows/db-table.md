---
title: "db_table | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_table
dev_langs: C++
helpviewer_keywords: db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2d8c7efaa23a8d7169ca41b4bfcb78722d73543
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dbtable"></a>db_table
Открывает таблицу OLE DB.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *db_table*  
 Строка, указывающая имя таблицы базы данных (например, «продукты»).  
  
 *name* (необязательно)  
 Имя дескриптора, который используется для работы с таблицей. Необходимо указать этот параметр, если требуется возвратить более одной строки результатов. **db_table** создает переменную с указанным *имя* , может использоваться для Обзор набора строк или выполнение нескольких запросов.  
  
 *source_name* (необязательно)  
 Переменная `CSession` или экземпляр класса с примененным атрибутом `db_source` , по которому выполняется команда. См. описание [db_source](../windows/db-source.md).  
  
 `hresult` (необязательно)  
 Определяет переменную, которая будет получать `HRESULT` этой команды базы данных. Если переменная не существует, она будет автоматически внедрена с помощью атрибута.  
  
## <a name="remarks"></a>Примечания  
 **db_table** создает [CTable](../data/oledb/ctable-class.md) объект, который используется потребителя OLE DB, чтобы открыть таблицу. Этот атрибут можно использовать только на уровне класса; его нельзя использовать встроенные. Используйте **db_column** для привязки столбцов таблицы переменных; используйте **db_param** в качестве разделителя (задать тип параметра и поэтому на) параметров.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
## <a name="example"></a>Пример  
 В следующем примере открывается в таблице продуктов для использования `CProducts`.  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 Пример этого атрибута, используемого в приложении, см. в примерах [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409) и [MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)   
