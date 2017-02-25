---
title: "Команды и таблицы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorRowset - класс, классы команд и таблиц"
  - "CCommand - класс, шаблоны потребителя OLE DB"
  - "команды [C++], шаблоны потребителя OLE DB"
  - "CTable - класс"
  - "шаблоны потребителя OLE DB, поддержка команд"
  - "шаблоны потребителя OLE DB, поддержка таблиц"
  - "наборы строк, доступ"
  - "таблицы [C++], шаблоны потребителя OLE DB"
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Команды и таблицы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Команды и таблицы позволяют обращаться к наборам строк, то есть открывать их, выполнять команды и связывание столбцов.  Классы [CCommand](../../data/oledb/ccommand-class.md) и [CTable](../../data/oledb/ctable-class.md) создают объекты command и table соответственно.  Эти классы являются производными от [CAccessorRowset](../Topic/CAccessorRowset%20Class.md), как показано на следующем рисунке.  
  
 ![CCommand и CTable](../../data/oledb/media/vccommandstables.gif "vcCommandsTables")  
Классы команд и таблиц  
  
 Тип `TAccessor`, показанный в предыдущей таблице, может быть любым типом метода доступа из перечисленных в разделе [Типы методов доступа](../../data/oledb/accessors-and-rowsets.md).  Тип *TRowset* может быть любым типом набора строк из перечисленных в разделе [Типы набора строк](../../data/oledb/accessors-and-rowsets.md).  Тип *TMultiple* указывает тип результата \(один или несколько результирующих наборов\).  
  
 [Мастер потребителей OLE DB библиотеки ATL](../../atl/reference/atl-ole-db-consumer-wizard.md) позволяет указать, необходимо ли использовать объект command или table.  
  
-   Для источников данных без объектов command можно использовать класс `CTable`.  Обычно он применяется к простым наборам записей, для которых не указываются параметры и не требуется нескольких результатов.  Этот простой класс открывает объект table в источнике данных с помощью указанного имени объекта table.  
  
-   Для источников данных, поддерживающих объекты command, также можно использовать класс `CCommand`.  Чтобы выполнить команду, следует вызвать функцию [Open](../../data/oledb/ccommand-open.md) для этого класса.  В качестве альтернативы можно использовать функцию `Prepare` для подготовки команды, которую необходимо выполнить более одного раза.  
  
     Класс **CCommand** имеет три аргумента шаблона: тип метода доступа, тип набора строк и тип результатов \(`CNoMultipleResults`, используемый по умолчанию, или `CMultipleResults`\).  Если используется `CMultipleResults`, класс `CCommand` поддерживает интерфейс **IMultipleResults** и обрабатывает несколько наборов строк.  В примере [DBVIEWER](http://msdn.microsoft.com/ru-ru/07620f99-c347-4d09-9ebc-2459e8049832) показано, как обрабатывать несколько результатов.  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)