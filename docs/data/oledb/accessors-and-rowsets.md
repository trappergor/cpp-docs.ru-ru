---
title: "Методы доступа и наборы строк | Microsoft Docs"
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
  - "методы доступа [C++]"
  - "методы доступа [C++], наборы строк"
  - "набор строк массива"
  - "набор строк пакета"
  - "CAccessorBase - класс"
  - "CAccessorRowset - класс, типы методов доступа"
  - "CArrayRowset - класс, методы доступа"
  - "CBulkRowset - класс, методы доступа"
  - "CRowset - класс, методы доступа и наборы строк"
  - "шаблоны потребителя OLE DB, методы доступа"
  - "шаблоны потребителя OLE DB, поддержка наборов строк"
  - "наборы строк [C++], доступ"
  - "наборы строк [C++], поддерживаемые типы"
  - "одиночные наборы строк"
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Методы доступа и наборы строк
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для записи и извлечения данных шаблоны OLE DB используют метод доступа и набор строк с помощью класса [CAccessorRowset](../Topic/CAccessorRowset%20Class.md).  Этот класс может обрабатывать несколько методов доступа различного типа.  
  
## Типы методов доступа  
 Все методы доступа наследуются от [CAccessorBase](../../data/oledb/caccessorbase-class.md).  `CAccessorBase` предоставляет привязку к параметру и к столбцу.  
  
 На следующем рисунке показаны типы методов доступа.  
  
 ![Типы методов доступа](../../data/oledb/media/vcaccessortypes.gif "vcAccessorTypes")  
Классы методов доступа  
  
-   [CAccessor](../Topic/CAccessor%20Class.md) Используйте этот метод доступа, если структура источника базы данных во время разработки известна.  `CAccessor` статически привязывает к источнику данных запись базы данных, содержащую буфер.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Используйте этот метод доступа, если структура источника базы данных во время разработки неизвестна.  `CDynamicAccessor` вызывает `IColumnsInfo::GetColumnInfo` для получения сведений о столбце базы данных.  Создает и управляет методом доступа и буфером.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Используйте этот метод доступа для обработки неизвестных типов команд.  При подготовке команд `CDynamicParameterAccessor` может получить сведения о параметрах с помощью интерфейса `ICommandWithParameters`, если поставщик поддерживает `ICommandWithParameters`.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md) и [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) Используйте эти классы, если схема базы данных неизвестна.  `CDynamicStringAccessorA` получает данные в виде строк ANSI; `CDynamicStringAccessorW` получает данные в виде строк Юникода.  
  
-   [CManualAccessor](../Topic/CManualAccessor%20Class.md) С помощью этого класса возможно использование любого типа данных, если поставщик сможет конвертировать этот тип.  Он обрабатывает как столбцы результатов, так и параметры команд.  
  
 Следующая таблица кратко описывает поддержку типов методов доступа для шаблонов OLE DB.  
  
|Тип метода доступа|Динамический|Обрабатывает параметры|Буфер|Несколько методов доступа|  
|------------------------|------------------|----------------------------|-----------|-------------------------------|  
|`CAccessor`|Нет|Да|Пользователь|Да|  
|`CDynamicAccessor`|Да|Нет|Шаблоны OLE DB|Нет|  
|`CDynamicParameterAccessor`|Да|Да|Шаблоны OLE DB|Нет|  
|`CDynamicStringAccessor[A,W]`|Да|Нет|Шаблоны OLE DB|Нет|  
|`CManualAccessor`|Да|Да|Пользователь|Да|  
  
## Типы наборов строк  
 Шаблоны OLE DB поддерживают три вида набора строк \(см. предыдущий рисунок\): одиночный набор строк \(реализован [CRowset](../Topic/CRowset%20Class.md)\), групповой набор строк \(реализован [CBulkRowset](../Topic/CBulkRowset%20Class.md)\) и массивный набор строк \(реализован [CArrayRowset](../../data/oledb/carrayrowset-class.md)\).  Одиночный набор строк загружает дескриптор одной строки при вызове `MoveNext`.  Групповой набор строк может загрузить дескриптор нескольких строк.  Массивный набор строк — тот, к которому можно получить доступ, пользуясь синтаксисом массива.  
  
 На следующем рисунке показаны типы наборов строк.  
  
 ![График RowsetType](../../data/oledb/media/vcrowsettypes.png "vcRowsetTypes")  
Классы набора строк  
  
 [Набор строк схемы](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) не предоставляет доступа к хранилищу данных, а предоставляет информацию о хранилище данных, — метаданные.  Наборы строк схемы обычно используются в ситуациях, когда структура базы данных неизвестна на момент компиляции и должна быть получена во время выполнения.  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)