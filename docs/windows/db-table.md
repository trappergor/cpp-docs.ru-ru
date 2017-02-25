---
title: "db_table | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_table"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_table attribute"
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# db_table
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Открывает таблицу OLE DB.  
  
## Синтаксис  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### Параметры  
 *db\_table*  
 Строка, указывающая имя таблицы базы данных \(например, "продукты"\).  
  
 *Имя* \(необязательно\)  
 Имя маркера используется для работы с таблицей.  Необходимо указать этот параметр, если необходимо возвращать более одной строки результатов.  **db\_table** создает указанную переменную с Имя это можно использовать для обхода набор строк или выполнять несколько запросов на изменение.  
  
 *source\_name* \(необязательно\)  
 `CSession` переменная или экземпляром класса, имеющего  `db_source` атрибут, примененные к нему, выполняется команда.  См. [db\_source](../windows/db-source.md).  
  
 `hresult` \(необязательный параметр\)  
 Указывает переменную, получающую `HRESULT` этой команды базы данных.  Если переменная не существует, то она будет автоматически вставлен с помощью атрибута.  
  
## Заметки  
 **db\_table** создает a  [CTable](../data/oledb/ctable-class.md) объект, который используется объектом\-получателем OLE DB, можно открыть таблицу.  Этот атрибут можно использовать только на уровне класса. его нельзя использовать встроенные.  Используйте **db\_column** привязки столбцов таблицы к переменным. используйте  **db\_param** выделения \(установите параметр типа и т д\) параметров.  
  
 Когда поставщик атрибута объекта\-получателя применяет этот атрибут к классу компилятор переименовывает класс, \_*YourClassName*метод доступа, где *YourClassName* имя указанного класса, и компилятор также создает класс *YourClassName,* что является производным от \_*YourClassName*метод доступа.  В представлении классов отобразится оба класса.  
  
## Пример  
 Следующий пример иллюстрирует открытие таблицу products для использования by `CProducts`.  
  
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
  
 Пример использования данного атрибута, используемого в приложении см. в разделе примеры [AtlAgent](http://msdn.microsoft.com/ru-ru/52bef5da-c1a0-4223-b4e6-9e464b6db409) и  [MultiRead](http://msdn.microsoft.com/ru-ru/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)