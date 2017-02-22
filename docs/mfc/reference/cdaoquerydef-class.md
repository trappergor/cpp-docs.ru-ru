---
title: "CDaoQueryDef Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoQueryDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoQueryDef class"
  - "запросы [Visual Studio], определение"
  - "QueryDef objects"
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoQueryDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет определение запроса или "QueryDef" обычно одно сохраненное в базе данных.  
  
## Синтаксис  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoQueryDef::CDaoQueryDef](../Topic/CDaoQueryDef::CDaoQueryDef.md)|Создает объект **CDaoQueryDef** .  В следующем вызове **Открыть** или **Создать**, в зависимости от имеющихся необходимостей.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoQueryDef::Append](../Topic/CDaoQueryDef::Append.md)|Добавляет QueryDef в коллекцию QueryDefs базы данных как сохраненный запрос.|  
|[CDaoQueryDef::CanUpdate](../Topic/CDaoQueryDef::CanUpdate.md)|Возвращает ненулевое значение, если запрос может обновить базу данных.|  
|[CDaoQueryDef::Close](../Topic/CDaoQueryDef::Close.md)|Закрывает объект QueryDef.  Уничтожить объект C\+\+ после завершения с ним.|  
|[CDaoQueryDef::Create](../Topic/CDaoQueryDef::Create.md)|Создает базовый объект QueryDef DAO.  Используйте QueryDef как временный запрос или вызвать метод **Добавление**, чтобы сохранить ее в базе данных.|  
|[CDaoQueryDef::Execute](../Topic/CDaoQueryDef::Execute.md)|Выполняет запрос, определенный объектом QueryDef.|  
|[CDaoQueryDef::GetConnect](../Topic/CDaoQueryDef::GetConnect.md)|Возвращает строку подключения, связанную с QueryDef.  Строка соединения указывает источник данных.  \(Только для запросов к серверу SQL; в противном случае – пустая строка\).|  
|[CDaoQueryDef::GetDateCreated](../Topic/CDaoQueryDef::GetDateCreated.md)|Возвращает дату сохраненный запрос был создан.|  
|[CDaoQueryDef::GetDateLastUpdated](../Topic/CDaoQueryDef::GetDateLastUpdated.md)|Сохраненный запрос возвращает дату последнего обновления.|  
|[CDaoQueryDef::GetFieldCount](../Topic/CDaoQueryDef::GetFieldCount.md)|Возвращает количество полей, заданных QueryDef.|  
|[CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)|Возвращает сведения об указанном поле указанном в запросе.|  
|[CDaoQueryDef::GetName](../Topic/CDaoQueryDef::GetName.md)|Возвращает имя QueryDef.|  
|[CDaoQueryDef::GetODBCTimeout](../Topic/CDaoQueryDef::GetODBCTimeout.md)|Возвращает значение времени ожидания, используемое ODBC \(ODBC\) при QueryDef для запроса будет исполнено.  Это задает время, выделенное для завершения действия запроса.|  
|[CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md)|Возвращает количество параметров, определенных для запроса.|  
|[CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md)|Возвращает сведения об указанном параметре к запросу.|  
|[CDaoQueryDef::GetParamValue](../Topic/CDaoQueryDef::GetParamValue.md)|Возвращает значение указанного параметра к запросу.|  
|[CDaoQueryDef::GetRecordsAffected](../Topic/CDaoQueryDef::GetRecordsAffected.md)|Возвращает число записей, затронутых запросом на изменение.|  
|[CDaoQueryDef::GetReturnsRecords](../Topic/CDaoQueryDef::GetReturnsRecords.md)|Возвращает ненулевое значение, если запрос, указанный QueryDef возвращает записи.|  
|[CDaoQueryDef::GetSQL](../Topic/CDaoQueryDef::GetSQL.md)|Возвращает строку SQL, которая определяет запрос, определенный QueryDef.|  
|[CDaoQueryDef::GetType](../Topic/CDaoQueryDef::GetType.md)|Возвращает тип запроса: добавление, обновление, удаление делать\- таблицы и т д|  
|[CDaoQueryDef::IsOpen](../Topic/CDaoQueryDef::IsOpen.md)|Возвращает ненулевое значение, если QueryDef открытым и может быть исполнено.|  
|[CDaoQueryDef::Open](../Topic/CDaoQueryDef::Open.md)|Открывает существующий QueryDef, хранящихся в коллекции QueryDefs базы данных.|  
|[CDaoQueryDef::SetConnect](../Topic/CDaoQueryDef::SetConnect.md)|Задает строку подключения для запроса к серверу SQL на источник данных ODBC.|  
|[CDaoQueryDef::SetName](../Topic/CDaoQueryDef::SetName.md)|Задает имя сохраненного запроса, заменяя имя использовать, когда QueryDef было создано.|  
|[CDaoQueryDef::SetODBCTimeout](../Topic/CDaoQueryDef::SetODBCTimeout.md)|Задает значение времени ожидания для запроса, используемый ODBC \(ODBC\) при QueryDef будет исполнено.|  
|[CDaoQueryDef::SetParamValue](../Topic/CDaoQueryDef::SetParamValue.md)|Задает значение заданного параметра к запросу.|  
|[CDaoQueryDef::SetReturnsRecords](../Topic/CDaoQueryDef::SetReturnsRecords.md)|Определяет, возвращает ли QueryDef записи.  Установка этого атрибута к **TRUE** допустим только для запросов к серверу SQL.|  
|[CDaoQueryDef::SetSQL](../Topic/CDaoQueryDef::SetSQL.md)|Задает строку SQL, определяющая запрос, определенный QueryDef.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoQueryDef::m\_pDAOQueryDef](../Topic/CDaoQueryDef::m_pDAOQueryDef.md)|Указатель на интерфейс OLE для базового объекта QueryDef DAO.|  
|[CDaoQueryDef::m\_pDatabase](../Topic/CDaoQueryDef::m_pDatabase.md)|Указатель на объект `CDaoDatabase`, с которым QueryDef сопоставлено.  QueryDef может быть сохранено в базе данных.|  
  
## Заметки  
 Объект QueryDef доступа к данным, который содержит инструкцию SQL, описывающее запрос, и ее свойства, такие как "дата, созданная" и "время ожидания ODBC". Можно также создать временные объекты QueryDef без сохранения их, но удобно — и очень эффективным — сохранить часто используемые повторно запросов в базе данных.  Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) поддерживает коллекцию, QueryDefs называемую коллекция, содержащая его сохраненные querydefs.  
  
> [!NOTE]
>  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  Можно получить доступ к источнику данных ODBC с помощью классов DAO.  В общем случае классы MFC DAO способны на основе более чем классы MFC на основе ODBC; DAO\- на основе классы могут получить доступ к данным, включая через драйвер ODBC через собственный компонент database engine.  DAO\- на основе классов также поддерживают операции языка описания данных DDL \(язык DDL\), такие как добавление таблицы с помощью классов DAO непосредственно, без вызова.  
  
## Использование  
 Используйте объекты QueryDef или работать с существующими сохранены запросом или создать новый сохраненный запрос или временный запрос:  
  
1.  Во всех случаях, сначала создайте объект `CDaoQueryDef`, указав указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), к которому принадлежит запрос.  
  
2.  Затем выполните следующие действия в зависимости от того, что необходимо:  
  
    -   Для использования существовать сохранить запрос, вызовите функцию\-член [Открытие](../Topic/CDaoQueryDef::Open.md) объекта QueryDef, указав имя сохраненного запроса.  
  
    -   Чтобы создать новый сохраненный запрос, вызовите функцию\-член [Создание](../Topic/CDaoQueryDef::Create.md) объекта QueryDef, указав имя запроса.  Затем вызовите [Добавление](../Topic/CDaoQueryDef::Append.md) чтобы сохранить запрос путем его добавления в коллекцию QueryDefs базы данных.  **Создать** помещает QueryDef в открытое состояние, поэтому после вызова **Создать** собой не вызывайте **Открыть**.  
  
    -   Чтобы создать временный QueryDef, вызовите **Создать**.  Передайте пустую строку для имени запроса.  Не вызывайте **Добавление**.  
  
 После завершения использования объекта QueryDef, вызовите его функцию\-член [Закрыть](../Topic/CDaoQueryDef::Close.md); затем уничтожить объект QueryDef.  
  
> [!TIP]
>  Самым простым способом создания сохраненных запросов их создания и сохранения их в базе данных с помощью Microsoft Access.  Затем можно открыть и использовать их в пользовательском коде MFC.  
  
## Назначения  
 Можно использовать объект QueryDef для любого из следующих целей:  
  
-   Создание объекта `CDaoRecordset`  
  
-   Вызова функции\-члена **Выполнить** объекта напрямую для выполнения запроса на изменение или запрос к серверу SQL  
  
 Можно использовать объект QueryDef для любого типа запроса, включая select, действия crosstab, удаления, обновления, добавления, делать\- таблицу, определение данных SQL пропуск\- через соединения и массовых запросов.  Тип запроса определяется содержимым инструкции SQL, которое необходимо указать.  Дополнительные сведения о видах запросов см. в разделе **Выполнить** и функции\-члены [GetType](../Topic/CDaoQueryDef::GetType.md).  Наборы записей часто используются для строка\- возвращая запросов обычно тех с использованием **SELECT… ИЗ** ключевых слов.  **Выполнить** чаще всего используется для массовых операций.  Дополнительные сведения см. в разделе [Execute](../Topic/CDaoQueryDef::Execute.md) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## Querydefs и наборы записей  
 Чтобы использовать объект QueryDef создать объект `CDaoRecordset` обычно создании или открытии QueryDef, как описано выше.  Затем создайте объект набора записей передачи указателя на свой объект QueryDef при вызове [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  QueryDef передаче должно находиться в открытом состоянии.  Дополнительные сведения см. в описании класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Нельзя использовать QueryDef для создания набора записей \(чаще всего используются для QueryDef\), если оно не будет в открытом состоянии.  Поместите QueryDef в открытое состояние, путем вызова **Открыть** или **Создать**.  
  
## Внешние базы данных  
 Объекты QueryDef предпочтительный способ \- использовать собственный диалект SQL обработчика внешней базы данных.  Например, можно создать SQL\-запрос Transact \(например, используемое для Microsoft SQL Server\) и сохранить его в объекте QueryDef.  При необходимости использовать SQL\-запрос не на основе компонента database engine для jet \(Майкрософт\), необходимо предоставить строку соединения, указывающую к внешнему источнику данных.  Запросы с допустимыми строками подключения для которых не используется компонент database engine и передают запрос непосредственно на сервер внешней базы данных для обработки.  
  
> [!TIP]
>  Предпочтительный способ работы с таблицами ODBC вложить их в базу данных Microsoft jet \(.MDB\).  
  
 Дополнительные сведения см. в разделах "объект QueryDef", "коллекцию QueryDefs" и "объект CdbDatabase" пакета SDK DAO.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoQueryDef`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)