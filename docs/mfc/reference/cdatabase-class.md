---
title: "CDatabase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDatabase - класс"
  - "классы баз данных [C++], ODBC"
  - "подключения к базе данных [C++], CDatabase - класс"
  - "MFC [C++], ODBC"
  - "ODBC [C++], CDatabase - класс"
  - "ODBC database class"
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет подключение к источнику данных, к которому можно работать с переданным ей источник данных.  
  
## Синтаксис  
  
```  
  
class CDatabase : public CObject  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDatabase::CDatabase](../Topic/CDatabase::CDatabase.md)|Создает объект `CDatabase`.  Объект необходимо инициализировать путем вызова `OpenEx` или **Открыть**.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDatabase::BeginTrans](../Topic/CDatabase::BeginTrans.md)|Запускает транзакцию" — "ряд реверзибельных вызовов `AddNew`, **Изменить**, **Удалить** и функции\-членам **Обновить** класса `CRecordset` — на подключенном источнике данных.  Источник данных должен поддерживать транзакции для **BeginTrans** иметь любой в силу.|  
|[CDatabase::BindParameters](../Topic/CDatabase::BindParameters.md)|Позволяет параметрам привязки перед вызовом `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](../Topic/CDatabase::Cancel.md)|Отменяет асинхронную операцию или процесс из второго потока.|  
|[CDatabase::CanTransact](../Topic/CDatabase::CanTransact.md)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|  
|[CDatabase::CanUpdate](../Topic/CDatabase::CanUpdate.md)|Возвращает ненулевое значение, если объект `CDatabase` быть обновляемым \(не только для чтения\).|  
|[CDatabase::Close](../Topic/CDatabase::Close.md)|Закрывает соединение с источником данных.|  
|[CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md)|Завершает транзакцию, **BeginTrans**.  Команды в транзакции, которые изменяют источник данных унесены.|  
|[CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)|Выполняет инструкцию SQL.  Отсутствуют записи данных не возвращаются.|  
|[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)|Определяет операции, которые сохраняются в объектах до закладки набора записей.|  
|[CDatabase::GetConnect](../Topic/CDatabase::GetConnect.md)|Возвращает строку подключения, используемую для подключения ODBC объекта `CDatabase` к источнику данных.|  
|[CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md)|Определяет эффект зафиксировать транзакцию на открытом объекте набора записей.|  
|[CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md)|Определяет эффект откатить транзакцию на открытом объекте набора записей.|  
|[CDatabase::GetDatabaseName](../Topic/CDatabase::GetDatabaseName.md)|Возвращает имя базы данных, в настоящее время используется.|  
|[CDatabase::IsOpen](../Topic/CDatabase::IsOpen.md)|Возвращает ненулевое значение, если объект `CDatabase` в настоящее время для подключения к источнику данных.|  
|[CDatabase::OnSetOptions](../Topic/CDatabase::OnSetOptions.md)|Вызываемый платформой для задания стандартные параметры соединения.  Реализация по умолчанию устанавливает значение времени ожидания запроса.  Можно установить эти параметры впереди времени путем вызова `SetQueryTimeout`.|  
|[CDatabase::Open](../Topic/CDatabase::Open.md)|Устанавливает соединение с источником данных \(через драйвер ODBC\).|  
|[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)|Устанавливает соединение с источником данных \(через драйвер ODBC\).|  
|[CDatabase::Rollback](../Topic/CDatabase::Rollback.md)|Обратитей изменения, внесенные во время текущей транзакции.  Источник данных вернется к своему предыдущему состоянию, как определено в вызове **BeginTrans**, без изменений.|  
|[CDatabase::SetLoginTimeout](../Topic/CDatabase::SetLoginTimeout.md)|Задает число секунд, после которого попытка соединения с источником данных времени ожидания.|  
|[CDatabase::SetQueryTimeout](../Topic/CDatabase::SetQueryTimeout.md)|Задает число секунд, после которого операции запроса к базе данных приурочат ожидания.  Распространяется на весь последующий набор записей **Открыть**, `AddNew`, **Изменить** и вызовы **Удалить**.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDatabase::m\_hdbc](../Topic/CDatabase::m_hdbc.md)|Дескриптор соединения ODBC \(ODBC\) с источником данных.  Тип **HDBC**.|  
  
## Заметки  
 Источник данных конкретный экземпляр данных, который размещение некоторая система управления базами данных \(СУБД\).  Примеры включают dBASE Microsoft SQL Server, Microsoft Access Borland и xBASE.  Можно иметь активные одного или нескольких объектов `CDatabase` одновременно в приложении.  
  
> [!NOTE]
>  При работе с DAO \(DAO\) классифицируете, а не классов ODBC \(ODBC\) использует класс [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md).  Дополнительные сведения см. в статье [Общие сведения: программирование базы данных](../../data/data-access-programming-mfc-atl.md).  
  
 Для использования `CDatabase`, создайте объект `CDatabase` и вызовите его функцию\-член `OpenEx`.  Это открывает соединение.  Если затем построения объектов `CRecordset` для работы на подключенном источнике данных, передайте конструктору набора записей указатель на объект `CDatabase`.  Завершив использовать соединение, вызовите функцию\-член **Закрыть** и уничтожить объект `CDatabase`.  **Закрыть** закрывает все наборы записей не закрыли ранее.  
  
 Дополнительные сведения о `CDatabase` см. в разделе статьи [источник данных \(ODBC\)](../../data/odbc/data-source-odbc.md) и [Общие сведения: программирование базы данных](../../data/data-access-programming-mfc-atl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDatabase`  
  
## Требования  
 **Header:**  afxdb.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)