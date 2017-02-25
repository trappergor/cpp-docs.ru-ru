---
title: "CDaoDatabase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabase class"
  - "CDaoDatabase class, and workspace"
  - "CDaoDatabase class, vs. CDatabase class"
  - "CDatabase - класс, vs. CDaoDatabase class"
  - "классы баз данных [C++], DAO"
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет подключение к базе данных, до которой можно работать с переданным ей данные.  
  
## Синтаксис  
  
```  
class CDaoDatabase : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoDatabase::CDaoDatabase](../Topic/CDaoDatabase::CDaoDatabase.md)|Создает объект `CDaoDatabase`.  Вызовите **Открыть** для подключения объекта в базе данных.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)|Возвращает ненулевое значение, если обозреватель транзакций базы данных.|  
|[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)|Возвращает ненулевое значение, если объект `CDaoDatabase` быть обновляемым \(не только для чтения\).|  
|[CDaoDatabase::Close](../Topic/CDaoDatabase::Close.md)|Закрывает соединение с базой данных.|  
|[CDaoDatabase::Create](../Topic/CDaoDatabase::Create.md)|Создает базовый объект базы данных DAO и инициализирует объект `CDaoDatabase`.|  
|[CDaoDatabase::CreateRelation](../Topic/CDaoDatabase::CreateRelation.md)|Определяет новую связь между таблицами в базе данных.|  
|[CDaoDatabase::DeleteQueryDef](../Topic/CDaoDatabase::DeleteQueryDef.md)|Удаляет объект QueryDef сохраненный в коллекции QueryDefs базы данных.|  
|[CDaoDatabase::DeleteRelation](../Topic/CDaoDatabase::DeleteRelation.md)|Удаляет существующую связь между таблицами в базе данных.|  
|[CDaoDatabase::DeleteTableDef](../Topic/CDaoDatabase::DeleteTableDef.md)|Удаляет определение таблицы в базе данных.  Это удаляет фактическая таблица и все ее данных.|  
|[CDaoDatabase::Execute](../Topic/CDaoDatabase::Execute.md)|Выполняет запрос на изменение.  Вызов **Выполнить** для запроса, который получает штрихи результатов исключение.|  
|[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md)|Возвращает строку подключения, используемую для подключения объект `CDaoDatabase` к базе данных.  Общий для ODBC.|  
|[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)|Возвращает имя базы данных, в настоящее время используется.|  
|[CDaoDatabase::GetQueryDefCount](../Topic/CDaoDatabase::GetQueryDefCount.md)|Возвращает количество запросов, определенных для базы данных.|  
|[CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)|Возвращает сведения об указанном запросе, определенном в базе данных.|  
|[CDaoDatabase::GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)|Возвращает число секунд, после которого операции запроса к базе данных приурочат ожидания.  Распространяется на весь последующий открыть добавляет новую, обновления и операции правки и другие операции на источник данных ODBC \(только\) как вызовы **Выполнить**.|  
|[CDaoDatabase::GetRecordsAffected](../Topic/CDaoDatabase::GetRecordsAffected.md)|Возвращает число записей, затронутых последним обновлением, правкой или добавить операцию, либо вызовом **Выполнить**.|  
|[CDaoDatabase::GetRelationCount](../Topic/CDaoDatabase::GetRelationCount.md)|Возвращает количество связей, определенных между таблицами в базе данных.|  
|[CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)|Возвращает сведения об указанной ссылки указанной между таблицами в базе данных.|  
|[CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md)|Возвращает число таблиц, определенное в базе данных.|  
|[CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)|Возвращает сведения об указанной таблицы в базе данных.|  
|[CDaoDatabase::GetVersion](../Topic/CDaoDatabase::GetVersion.md)|Возвращает версию компонента database engine, связанного с базой данных.|  
|[CDaoDatabase::IsOpen](../Topic/CDaoDatabase::IsOpen.md)|Возвращает ненулевое значение, если объект `CDaoDatabase` в настоящее время для подключения к базе данных.|  
|[CDaoDatabase::Open](../Topic/CDaoDatabase::Open.md)|Устанавливает соединение с базой данных.|  
|[CDaoDatabase::SetQueryTimeout](../Topic/CDaoDatabase::SetQueryTimeout.md)|Задает число секунд, после которого операции запроса к базе данных \(на источник данных ODBC\) приурочат ожидания.  Распространяется на весь последующий открыть добавляет новую, обновления и удаления.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoDatabase::m\_pDAODatabase](../Topic/CDaoDatabase::m_pDAODatabase.md)|Указатель на базовый объект базы данных DAO.|  
|[CDaoDatabase::m\_pWorkspace](../Topic/CDaoDatabase::m_pWorkspace.md)|Указатель на объект [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md), содержащего базу данных и указывающий его место транзакции.|  
  
## Заметки  
 Дополнительные сведения о поддерживаемых форматах базы данных см. в разделе [GetName](../Topic/CDaoWorkspace::GetName.md) функции\-члена.  Можно иметь активные одного или нескольких объектов `CDaoDatabase` одновременно в заданном "область", представленного объектом [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md).  Область поддерживает коллекцию открытых объектов базы данных, вызванную коллекция баз данных.  
  
> [!NOTE]
>  Классы баз данных MFC DAO MFC отличаются от классов баз данных на основе ODBC.  Все имена классов базы данных DAO имеют префикс "CDao".  Класс `CDaoDatabase` предоставляет интерфейс, аналогичный с сигнатурой класса [CDatabase](../../mfc/reference/cdatabase-class.md) ODBC.  Основное отличие состоит в том, что `CDatabase` обращается к engine через ODBC \(ODBC\) и драйвер ODBC engine.  Данные доступа `CDaoDatabase` через объект доступа к данным \(DAO\) на основе компонента database engine для jet \(Майкрософт\).  В общем случае классы MFC DAO способны на основе более чем классы MFC на основе ODBC; DAO\- на основе классы могут получить доступ к данным, включая через драйвер ODBC через собственный компонент database engine.  DAO\- на основе классов также поддерживают операции языка описания данных DDL \(язык DDL\), такие как добавление таблицы с помощью классов DAO непосредственно, без вызова.  
  
## Использование  
 Можно создать объекты базы данных неявно при создании объектов набора записей.  Однако можно также создать объекты базы данных явным образом.  Для использования существующей базы данных к получению с `CDaoDatabase` выполните одно из следующих действий:  
  
-   Создайте объект `CDaoDatabase`, передав указатель на открытый объект [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md).  
  
-   Создайте объект `CDaoDatabase` или без указания область \(MFC создает временный объект области\).  
  
 Чтобы создать новую базу данных Microsoft jet \(.MDB\), создайте объект `CDaoDatabase` и вызовите его функцию\-член [Создание](../Topic/CDaoDatabase::Create.md).  *Не* вызывайте **Открыть** после **Создать**.  
  
 Чтобы открыть существующую базу данных создайте объект `CDaoDatabase` и вызовите его функцию\-член [Открытие](../Topic/CDaoDatabase::Open.md).  
  
 Любые из этих методов добавить объект базы данных DAO к базам данных коллекции область, и открывает подключение к данным.  При построении объектов [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), затем [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) или [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) для работы в подключенной базе данных, передайте конструкторами для этих объектов указатель на объект `CDaoDatabase`.  Завершив использовать соединение, вызовите функцию\-член [Закрыть](../Topic/CDaoDatabase::Close.md) и уничтожить объект `CDaoDatabase`.  **Закрыть** закрывает все наборы записей не закрыли ранее.  
  
## Транзакции  
 Транзакционная обработка базы данных предоставляется на уровне области — см. в разделе [BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md), [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md) и функции\-члены [откат](../Topic/CDaoWorkspace::Rollback.md) класса `CDaoWorkspace`.  
  
## Подключения ODBC  
 Рекомендуемый способ работы с источником данных ODBC вложить внешние таблицы в базе данных Microsoft jet \(.MDB\).  
  
## Коллекции  
 Каждая база данных хранит собственные коллекции tabledef, QueryDef, набора записей и объектов отношений.  Класс `CDaoDatabase` предоставляет функции\-члены для обработки этих объектов.  
  
> [!NOTE]
>  Объекты хранятся в DAO, а не в объекте базы данных MFC.  MFC предоставляет классы для tabledef, QueryDef и объектов наборов записей, но не для объектов отношений.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoDatabase`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)