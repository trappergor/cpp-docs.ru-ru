---
title: "db_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_source attribute"
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# db_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает соединение с источником данных.  
  
## Синтаксис  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### Параметры  
 *db\_source*  
 Строка подключения, используемая для подключения к источнику данных.  Для формата строки соединения см. в разделе [строки подключения и каналы передачи данных](https://msdn.microsoft.com/en-us/library/ms718376.aspx) в пакете SDK для компонентов доступа к данным MDAC.  
  
 *Имя* \(необязательно\)  
 При использовании `db_source` в классе Имя экземпляр объекта источника данных, имеющего  `db_source` атрибут, примененный к нему \(см. пример 1\).  При использовании `db_source` встроенный в реализации метода Имя локальная переменная \(метод\), которые могут быть использованы для доступа к источнику данных \(см. пример 2\).  Передается таким Имя к `source_name` параметр   **db\_command** связать источник данных с командой.  
  
 `hresult` \(необязательный параметр\)  
 Указывает переменную, получающую `HRESULT` этой команды базы данных.  Если переменная не существует, то она будет автоматически вставлен с помощью атрибута.  
  
## Заметки  
 `db_source` создает a  [CDataSource](../Topic/CDataSource%20Class.md) и a  [CSession](../data/oledb/csession-class.md) объект, который совместно представляют объекта\-получателя соединение с источником данных OLE DB.  
  
 При использовании `db_source` в классе  `CSession` объект становится элементом класса.  
  
 При использовании `db_source` в методе, введенный код будет выполняться в пределах области действия метода.  `CSession` объект создан в качестве локальной переменной.  
  
 `db_source` добавляет свойства источника данных к классу или в методе.  Он используется совместно с **db\_command** \(который принимает  `db_source` Имя параметр как сво  `source_name` параметр\).  
  
 Когда поставщик атрибута объекта\-получателя применяет этот атрибут к классу компилятор переименовывает класс, \_*YourClassName*метод доступа, где *YourClassName* имя указанного класса, и компилятор также создает класс *YourClassName,* что является производным от \_*YourClassName*метод доступа.  В представлении классов отобразится оба класса.  
  
 Пример использования данного атрибута, используемого в приложении см. в разделе примеры [AtlAgent](http://msdn.microsoft.com/ru-ru/52bef5da-c1a0-4223-b4e6-9e464b6db409) и  [MultiRead](http://msdn.microsoft.com/ru-ru/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Пример  
 Вызовы этого образца `db_source` о классе для создания соединения с источником данных  `ds` использование базы данных Northwind.  `ds` дескриптор для источника данных, в который может использоваться для внутреннего использования  `CMyCommand` класс.  
  
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
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`участник, метод local|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)