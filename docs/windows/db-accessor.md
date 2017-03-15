---
title: "db_accessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_accessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_accessor attribute"
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_accessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Группы **db\_column** атрибуты, которые участвуют в пределах  `IAccessor`привязка на платформе.  
  
## Синтаксис  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### Параметры  
 *num*  
 Указывает номер метода доступа \(отсчитываемый от нуля индекс целые числа\).  Необходимо указать числа метода доступа по возрастанию, используя целые числа или указанные значения.  
  
 *Авто*  
 Логическое значение, которое определяет, является ли метод доступа \(извлечь автоматически**True**или не восстанавливается \(\)**False**\).  
  
## Заметки  
 **db\_accessor** определяет основной метод доступа к OLE DB для последующего  **db\_column** и  **db\_param** атрибуты в пределах одного и того же класса или функции.  **db\_accessor** пригоден на уровне члена и используется для группирования  **db\_column** атрибуты, которые участвуют в OLE DB  `IAccessor`привязка на платформе.  Она используется совместно с этим **db\_table** OR  **db\_command** атрибуты.  Вызвать этот атрибут аналогичен вызову [BEGIN\_ACCESSOR](../data/oledb/begin-accessor.md) и  [END\_ACCESSOR](../Topic/END_ACCESSOR.md) макросы.  
  
 db\_accessor создает набор строк, и привязывает его к соответствующему сопоставлениям метода доступа.  Если не вызвать db\_accessorметод доступа 0 будет автоматически создан и все привязки к столбцу будут сопоставлены этот блок метода доступа.  
  
 db\_accessor привязки столбцов базы данных групп в один или несколько методов доступа.  Описание сценариев, в которых необходимо использовать несколько методов доступа см. [Использование нескольких методов доступа в наборе строк](../Topic/Using%20Multiple%20Accessors%20on%20a%20Rowset.md).  Также см. раздел "поддержка записи пользователя для нескольких методов доступа" в [записи пользователя](../data/oledb/user-records.md).  
  
 Когда поставщик атрибута объекта\-получателя применяет этот атрибут к классу компилятор переименовывает класс, \_*YourClassName*метод доступа, где *YourClassName* имя указанного класса, и компилятор также создает класс *YourClassName,* что является производным от \_*YourClassName*метод доступа.  В представлении классов отобразится оба класса.  
  
## Пример  
 Следующий пример использует db\_accessor группирование столбцов в таблице orders из базы данных " борей " в 2 метода доступа.  Метод доступа 0 автоматическая метод доступа, а метод доступа 1 \- нет.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Блоки атрибутов|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)