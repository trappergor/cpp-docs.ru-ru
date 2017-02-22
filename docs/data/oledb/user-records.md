---
title: "Записи пользователя | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "методы доступа [C++], наборы строк"
  - "методы доступа [C++], статический"
  - "BEGIN_ACCESSOR - макрос, пример"
  - "BEGIN_ACCESSOR_MAP - макрос"
  - "CAccessor - класс, пример"
  - "COLUMN_ENTRY - макрос"
  - "COLUMN_ENTRY_MAP - макрос"
  - "шаблоны потребителя OLE DB, записи пользователя"
  - "наборы строк [C++], методы доступа"
  - "записи пользователя, шаблоны потребителя OLE DB"
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Записи пользователя
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы воспользоваться классом статического доступа \(то есть классом, производным от **CAccessor**\), потребитель должен иметь запись пользователя.  Запись пользователя — это класс C\+\+, который содержит элементы данных для обработки ввода или вывода.  Мастер потребителей OLE DB библиотеки ATL создает запись пользователя для поставщика.  Можно добавить к записи пользователя дополнительные методы для решения второстепенных задач, например, обработки команд.  
  
 Ниже приведен пример записи, обрабатывающей команды.  Макрос `BEGIN_COLUMN_MAP` в записи пользователя представляет набор строк данных, передаваемых потребителю от поставщика.  Макрос `BEGIN_PARAM_MAP` представляет набор параметров команды.  Для обработки параметров команды в этом примере используется класс [CCommand](../../data/oledb/ccommand-class.md).  Члены данных в записях карты представляют собой смещения в одном непрерывном блоке памяти для каждого экземпляра класса.  Макрос `COLUMN_ENTRY` соответствует макросу `PROVIDER_COLUMN_ENTRY` на стороне поставщика.  
  
 Дополнительные сведения о макросах **COLUMN\_MAP** и **PARAM\_MAP** см. в разделе [Макросы для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md).  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## Записи пользователя, созданные мастером  
 При использовании мастера потребителей OLE DB библиотеки ATL для создания потребителя существует выбор — применять шаблоны OLE DB или атрибуты OLE DB.  Генерируемый код будет отличаться в каждом случае.  Дополнительные сведения об этом коде см. в разделе [Классы потребителя, созданные мастером](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## Поддержка записей пользователя для нескольких объектов доступа  
 Подробное рассмотрение скриптов, в которых необходимо использование нескольких объектов доступа, см. в разделе [Использование нескольких объектов доступа к набору строк](../Topic/Using%20Multiple%20Accessors%20on%20a%20Rowset.md).  
  
 В следующем примере показана запись пользователя, измененная с целью поддержки использования нескольких объектов доступа к набору строк.  Вместо макросов `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для каждого объекта доступа используются макросы [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md) и [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md).  Макрос `BEGIN_ACCESSOR` указывает номер объекта доступа \(начиная с нуля\) и то, является ли объект доступа автоматическим.  Автоматические объекты доступа при каждом вызове функции [MoveNext](../../data/oledb/crowset-movenext.md) вызывают функцию `GetData` для автоматического извлечения данных.  Неавтоматические объекты доступа требуют явного извлечения данных.  Использовать неавтоматические объекты доступа следует в тех случаях, если выполняется привязка к полю крупного размера \(например, растровое изображение\), которое было бы нежелательно извлекать для каждой записи.  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)