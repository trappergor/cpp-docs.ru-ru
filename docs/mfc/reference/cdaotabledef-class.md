---
title: "CDaoTableDef Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoTableDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDef class"
  - "классы баз данных [C++], DAO"
  - "database tables [C++], attached table definition"
  - "database tables [C++], base table definition"
  - "tabledefs [C++]"
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoTableDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет сохраненных определение базовой таблицы или вложенной таблицы.  
  
## Синтаксис  
  
```  
class CDaoTableDef : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoTableDef::CDaoTableDef](../Topic/CDaoTableDef::CDaoTableDef.md)|Создает объект **CDaoTableDef** .|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoTableDef::Append](../Topic/CDaoTableDef::Append.md)|Добавляет новую таблицу в базе данных.|  
|[CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)|Возвращает ненулевое значение, если таблица может быть обновлена \(можно изменить определение полей или свойств таблицы\).|  
|[CDaoTableDef::Close](../Topic/CDaoTableDef::Close.md)|Закрывает открытые tabledef.|  
|[CDaoTableDef::Create](../Topic/CDaoTableDef::Create.md)|Создается таблица, которая может быть добавлена в базе данных с помощью [Добавление](../Topic/CDaoTableDef::Append.md).|  
|[CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md)|Чтобы создать поле с именем таблицы.|  
|[CDaoTableDef::CreateIndex](../Topic/CDaoTableDef::CreateIndex.md)|Вызываемый для создания индекса для таблицы.|  
|[CDaoTableDef::DeleteField](../Topic/CDaoTableDef::DeleteField.md)|Вызываемый для удаления поле из таблицы.|  
|[CDaoTableDef::DeleteIndex](../Topic/CDaoTableDef::DeleteIndex.md)|Вызываемый для удаления индексов из таблицы.|  
|[CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)|Возвращает значение, указывающее одну или несколько характеристик объекта `CDaoTableDef`.|  
|[CDaoTableDef::GetConnect](../Topic/CDaoTableDef::GetConnect.md)|Возвращает значение, предоставляющее сведения об источнике таблицы.|  
|[CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)|Возвращает дату и время создана базовая таблица была лежащие в основе `CDaoTableDef` объект.|  
|[CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)|Возвращает дату и время самого последнего выполненного изменения в структуре базовой таблицы.|  
|[CDaoTableDef::GetFieldCount](../Topic/CDaoTableDef::GetFieldCount.md)|Возвращает значение, представляющее число полей в таблице.|  
|[CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)|Возвращает определенные типы сведений о полях в таблице.|  
|[CDaoTableDef::GetIndexCount](../Topic/CDaoTableDef::GetIndexCount.md)|Возвращает количество индексов для таблицы.|  
|[CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)|Возвращает определенные типы сведений об индексах для таблицы.|  
|[CDaoTableDef::GetName](../Topic/CDaoTableDef::GetName.md)|Возвращает определенное пользователем имя таблицы.|  
|[CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)|Возвращает число записей в таблице.|  
|[CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)|Возвращает значение, определяющее имя вложенной таблицы в базе данных\-источнике.|  
|[CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)|Возвращает значение, которое проверяет данные в поле, так как именно она изменен или добавлено в таблице.|  
|[CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)|Возвращает значение, указывающее текст сообщения, приложение отображает поля, если значение объекта не удовлетворяет указанное правило проверки.|  
|[CDaoTableDef::IsOpen](../Topic/CDaoTableDef::IsOpen.md)|Возвращает ненулевое, если она открыта.|  
|[CDaoTableDef::Open](../Topic/CDaoTableDef::Open.md)|Открывает существующий tabledef, хранящихся в коллекции TableDef базы данных.|  
|[CDaoTableDef::RefreshLink](../Topic/CDaoTableDef::RefreshLink.md)|Обновляет сведения о соединении для вложенной таблицы.|  
|[CDaoTableDef::SetAttributes](../Topic/CDaoTableDef::SetAttributes.md)|Задает значение, которое указывает один или несколько характеристик объекта `CDaoTableDef`.|  
|[CDaoTableDef::SetConnect](../Topic/CDaoTableDef::SetConnect.md)|Устанавливает значение, предоставляющее сведения об источнике таблицы.|  
|[CDaoTableDef::SetName](../Topic/CDaoTableDef::SetName.md)|Задает имя таблицы.|  
|[CDaoTableDef::SetSourceTableName](../Topic/CDaoTableDef::SetSourceTableName.md)|Задает значение, указывающее имя вложенной таблицы в базе данных\-источнике.|  
|[CDaoTableDef::SetValidationRule](../Topic/CDaoTableDef::SetValidationRule.md)|Задает значение, которое проверяет данные в поле, так как именно она изменен или добавлено в таблице.|  
|[CDaoTableDef::SetValidationText](../Topic/CDaoTableDef::SetValidationText.md)|Задает значение, указывающее текст сообщения, приложение отображает поля, если значение объекта не удовлетворяет указанное правило проверки.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoTableDef::m\_pDAOTableDef](../Topic/CDaoTableDef::m_pDAOTableDef.md)|Указатель на интерфейс DAO, лежащие в основе tabledef объект.|  
|[CDaoTableDef::m\_pDatabase](../Topic/CDaoTableDef::m_pDatabase.md)|База данных\-источник для этой таблицы.|  
  
## Заметки  
 Каждый объект базы данных DAO, называемую поддерживает коллекцию, TableDefs, содержащий все объекты, сохраненные tabledef DAO.  
  
 Необходимо управление определение таблицы с помощью объекта `CDaoTableDef`.  В частности, можно выполнить следующие действия.  
  
-   Просмотрите вложенную структуру полей и индексов any локального или внешнюю таблицу в базе данных.  
  
-   Вызвать функции\-члены `SetConnect` и `SetSourceTableName` для вложенных таблиц и с помощью функции\-члена `RefreshLink` для обновления подключения к вложенным таблицам.  
  
-   Вызовите функцию\-член `CanUpdate`, чтобы определить, можно изменить определения поля в таблице.  
  
-   Возвратите или задайте критерий проверки с помощью `GetValidationRule` и `SetValidationRule` и функции\-члены `GetValidationText` и `SetValidationText`.  
  
-   Использование функции\-члена **Открыть** чтобы создать таблицу, динамическое подмножество данных или объект `CDaoRecordset` моментальный снимок\- типа.  
  
    > [!NOTE]
    >  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  Можно получить доступ к источнику данных ODBC с помощью классов DAO; классы DAO обычно обеспечивают основные возможности, поскольку они относятся к ядру СУБД jet \(Майкрософт\).  
  
### Использование объектов tabledef или работать с существующей таблицей или создать новую таблицу  
  
1.  Во всех случаях, сначала создайте объект `CDaoTableDef`, указав указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), к которому принадлежит таблица.  
  
2.  Затем выполните следующие действия в зависимости от того, что необходимо:  
  
    -   Для использования существовать сохранить таблицу, вызовите функцию\-член [Открытие](../Topic/CDaoTableDef::Open.md) объекта tabledef, указав имя сохраненной таблицы.  
  
    -   Для создания новой таблицы, вызовите функцию\-член [Создание](../Topic/CDaoTableDef::Create.md) объекта tabledef, указав имя таблицы.  Вызовите [CreateField](../Topic/CDaoTableDef::CreateField.md) и [CreateIndex](../Topic/CDaoTableDef::CreateIndex.md) для добавления полей и индексы в таблице.  
  
    -   Вызовите [Добавление](../Topic/CDaoTableDef::Append.md) чтобы сохранить таблицу путем добавления его в коллекцию TableDefs базы данных.  **Создать** помещает tabledef в открытое состояние, поэтому после вызова **Создать** собой не вызывайте **Открыть**.  
  
        > [!TIP]
        >  Самым простым способом создания сохраненные таблицы их создания и сохранения их в базе данных с помощью Microsoft Access.  Затем можно открыть и использовать их в пользовательском коде MFC.  
  
 Чтобы использовать объект tabledef вы открыли или создана, создайте и откройте объект `CDaoRecordset`, указав имя tabledef со значением **dbOpenTable** в параметре `nOpenType`.  
  
 Чтобы использовать объект tabledef создать объект `CDaoRecordset` обычно создании или открытии tabledef, как описано выше, а затем построения объекта набора записей передачи указателя на свой объект tabledef при вызове [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  Tabledef передаче должно находиться в открытом состоянии.  Дополнительные сведения см. в описании класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 После завершения использования объекта tabledef, вызовите его функцию\-член [Закрыть](../Topic/CDaoRecordset::Close.md); затем уничтожить объект tabledef.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoTableDef`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)