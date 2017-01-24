---
title: "CDaoWorkspace Class | Microsoft Docs"
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
  - "CDaoWorkspace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspace class"
  - "DAO workspaces [C++]"
  - "DAO workspaces [C++], CDaoWorkspace class"
  - "database engine [C++], accessing via workspace"
  - "DDLs [C++]"
  - "default workspaces [C++]"
  - "default workspaces [C++], DAO"
  - "по умолчанию [C++], рабочие области"
  - "классы ODBC [C++], vs. DAO classes"
  - "persistence [C++], DAO workspace"
  - "security [MFC]"
  - "security [MFC], DAO workspaces"
  - "sessions [C++], DAO workspace"
  - "transaction spaces [C++]"
  - "transaction spaces [C++], DAO workspace"
  - "Workspace class"
  - "workspaces [C++], DAO"
  - "workspaces [C++], по умолчанию"
  - "workspaces [C++], interface to database engine"
  - "workspaces [C++], сохранение"
  - "Workspaces collection"
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoWorkspace Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет именованный, защищаются паролем сеанс базы данных из имени входа, которое будет logoff, один пользователь.  
  
## Синтаксис  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoWorkspace::CDaoWorkspace](../Topic/CDaoWorkspace::CDaoWorkspace.md)|Создает объект рабочей области.  После этого вызова **Создать** или **Открыть**.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoWorkspace::Append](../Topic/CDaoWorkspace::Append.md)|Добавляет вновь созданную рабочую область в коллекции областей компонента database engine.|  
|[CDaoWorkspace::BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)|Начинает новую транзакцию, которая применяется ко всем базам данных открытым в рабочей области.|  
|[CDaoWorkspace::Close](../Topic/CDaoWorkspace::Close.md)|Закрывает рабочую область и все объекты она содержит.  Незавершенные транзакции откатите.|  
|[CDaoWorkspace::CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)|Выполняет текущую транзакцию и сохранение изменений.|  
|[CDaoWorkspace::CompactDatabase](../Topic/CDaoWorkspace::CompactDatabase.md)|Сжимает \(или дубликатов\) базы данных.|  
|[CDaoWorkspace::Create](../Topic/CDaoWorkspace::Create.md)|Создает новый объект области DAO.|  
|[CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)|Возвращает количество объектов базы данных DAO в коллекции баз данных рабочей области.|  
|[CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)|Возвращает сведения об указанной базе данных из коллекции баз данных DAO указанной области.|  
|[CDaoWorkspace::GetIniPath](../Topic/CDaoWorkspace::GetIniPath.md)|Возвращает расположение параметры инициализации компонента database engine для jet \(Майкрософт\) в реестре Windows.|  
|[CDaoWorkspace::GetIsolateODBCTrans](../Topic/CDaoWorkspace::GetIsolateODBCTrans.md)|Возвращает значение, указывающее, является ли несколько транзакций, которые содержат один и тот же источник данных ODBC с помощью изолируйте forced несколько подключений к источнику данных.|  
|[CDaoWorkspace::GetLoginTimeout](../Topic/CDaoWorkspace::GetLoginTimeout.md)|Возвращает количество секунд, прежде чем ошибка происходит, когда пользователь предпринимает попытку входа в базу данных ODBC.|  
|[CDaoWorkspace::GetName](../Topic/CDaoWorkspace::GetName.md)|Возвращает определяемое пользователем имя объекта области.|  
|[CDaoWorkspace::GetUserName](../Topic/CDaoWorkspace::GetUserName.md)|Возвращает заданное имя пользователя, если рабочая область была создана.  Это имя владельцем рабочей области.|  
|[CDaoWorkspace::GetVersion](../Topic/CDaoWorkspace::GetVersion.md)|Возвращает строку, которая содержит версию компонента database engine, связанного с рабочей областью.|  
|[CDaoWorkspace::GetWorkspaceCount](../Topic/CDaoWorkspace::GetWorkspaceCount.md)|Возвращает количество объектов области DAO в коллекции областей компонента database engine.|  
|[CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)|Возвращает сведения об указанной области DAO, указанной в коллекции областей компонента database engine.|  
|[CDaoWorkspace::Idle](../Topic/CDaoWorkspace::Idle.md)|Разрешает database engine для выполнения фоновой задачи.|  
|[CDaoWorkspace::IsOpen](../Topic/CDaoWorkspace::IsOpen.md)|Возвращает ненулевое значение, если область открыта.|  
|[CDaoWorkspace::Open](../Topic/CDaoWorkspace::Open.md)|Явно открыть объект области, связанный с рабочей областью по умолчанию DAO.|  
|[CDaoWorkspace::RepairDatabase](../Topic/CDaoWorkspace::RepairDatabase.md)|Пытается исправить поврежденную базу данных.|  
|[CDaoWorkspace::Rollback](../Topic/CDaoWorkspace::Rollback.md)|Завершает текущую транзакцию и не сохраняет изменения.|  
|[CDaoWorkspace::SetDefaultPassword](../Topic/CDaoWorkspace::SetDefaultPassword.md)|Задает пароль, который компонент database engine использует когда объект области создание без определенного пароля.|  
|[CDaoWorkspace::SetDefaultUser](../Topic/CDaoWorkspace::SetDefaultUser.md)|Задает имя пользователя, которое компонент database engine использует когда объект области создание без определенного имени пользователя.|  
|[CDaoWorkspace::SetIniPath](../Topic/CDaoWorkspace::SetIniPath.md)|Задает расположение параметры инициализации компонента database engine для jet \(Майкрософт\) в реестре Windows.|  
|[CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md)|Определяет, является ли несколько транзакции изолируются которые содержат один и тот же источник данных ODBC с помощью форсирования несколько подключений к источнику данных.|  
|[CDaoWorkspace::SetLoginTimeout](../Topic/CDaoWorkspace::SetLoginTimeout.md)|Задает число секунд, прежде чем ошибка происходит, когда пользователь предпринимает попытку входа в источник данных ODBC.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoWorkspace::m\_pDAOWorkspace](../Topic/CDaoWorkspace::m_pDAOWorkspace.md)|Точки к основному объекту области DAO.|  
  
## Заметки  
 В большинстве случаев не понадобятся нескольких рабочих областей, а не будет создать точные объекты области. при открытии объекты базы данных и набора записей, однако они используют рабочую область по умолчанию DAO.  Однако если требуется, можно выполнять одновременно несколько сеансов путем создания дополнительных объектов рабочей области.  Каждый объект области может содержать объекты базы данных открыты несколько раз в собственной коллекции баз данных.  В MFC, область основным диспетчер транзакций, указав набор открытых баз данных все в той же области транзакции "."  
  
> [!NOTE]
>  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  В общем случае классы MFC DAO способны на основе более чем классы MFC на основе ODBC.  DAO\- на основе классы получают доступ к данным через компонент database engine для jet \(Майкрософт\), в том числе драйвер ODBC.  Они также поддерживают операции языка описания данных DDL \(язык DDL\), такие как создание базы данных и добавление таблиц и полей с помощью классов DAO непосредственно, без вызова.  
  
## Возможности  
 Класс `CDaoWorkspace` предоставляет следующие действия:  
  
-   Явный доступ, если необходимо, для области по умолчанию, созданное при инициализации компонента database engine.  Обычно область по умолчанию DAO использования неявно путем создания объектов базы данных и набора записей.  
  
-   Пространство транзакции, в которой транзакции применяются ко всем базам данных открытым в рабочей области.  Можно создать дополнительные рабочие области для управления отдельными пробелы транзакции.  
  
-   Интерфейс для многих свойств основного компонента database engine для jet \(Майкрософт\) \(см. статические функции\-члены\).  Открытие или создание рабочей области или вызвать функцию статического члена, прежде чем открыть или создать инициализирует компонент database engine.  
  
-   Доступ к коллекции областей database engine, в которой хранятся все активные рабочих областей, которые были добавлены к ней.  Можно также создать и работать с рабочими областями без добавления их в коллекцию.  
  
## Безопасность  
 MFC не реализует пользователей и не группирует коллекции в DAO, которые используются для контроля доступа.  Если необходимы эти аспекты DAO, то ее необходимо запрограммировать их с помощью прямых вызовов к интерфейсам DAO.  Дополнительные сведения см. в разделе [Техническая примечание 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Использование  
 Можно использовать класс `CDaoWorkspace`:  
  
-   Явно открыть область по умолчанию.  
  
     Как правило, использование области по умолчанию неявной — при открытии новые объекты [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  Однако можно получить к нему доступ явно — например, доступ к свойствам компонента database engine или коллекция рабочих областей.  Неявная см. в разделе "использование области по умолчанию" ниже.  
  
-   Создание новых рабочих областей.  Вызовите [Добавление](../Topic/CDaoWorkspace::Append.md) если требуется добавить их в коллекцию рабочих областей.  
  
-   Открыть существующую рабочую область в коллекции областей.  
  
 Создать новую рабочую область, которая уже не существует в коллекции областей, описан в разделе [Создание](../Topic/CDaoWorkspace::Create.md) функцией\-членом.  Объекты области не сохраняются в любом случае между сеансами обработчика datababase.  Если ссылки приложения MFC статически, завершение приложения uninitializes компонента database engine.  Если ссылки приложения с MFC, компонент database engine неинициализированным, когда библиотека DLL MFC.  
  
 Явно открыть область по умолчанию или открыть существующую рабочую область в рабочих областях коллекции, описанные в разделе функцией\-членом [Открытие](../Topic/CDaoWorkspace::Open.md).  
  
 Завершение сеанса области, закрыть область с функцией\-членом [Закрыть](../Topic/CDaoWorkspace::Close.md).  **Закрыть** закрывает все базы данных не закрыли ранее, откатящ всех незафиксированных транзакций.  
  
## Транзакции  
 DAO управляет транзакций на уровне области. следовательно, транзакции в рабочей области с базами данных открытого кратен применяются ко всем базам данных.  Например, если 2 базы данных имеют uncommitted обновления и вызвать [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md), все обновления зафиксироватьы.  Если необходимо ограничить транзакции в одной базе данных, то необходим отдельный объект области.  
  
## Неявное использование области по умолчанию  
 MFC DAO используется область по умолчанию неявно в следующих случаях:  
  
-   Если создается новый объект `CDaoDatabase`, но не сделать через существующий объект `CDaoWorkspace`, MFC создает временный объект области, которые соответствует области по умолчанию DAO.  Если это сделать для нескольких баз данных все объекты базы данных сопоставлены с рабочей областью по умолчанию.  Можно открыть область базы данных с помощью элемента данных `CDaoDatabase`.  
  
-   Аналогично, при создании объекта `CDaoRecordset` без указания указатель на объект `CDaoDatabase`, MFC создает временный объект базы данных, и расширением, временный объект рабочей области.  Можно получить доступ к базе данных набора записей и косвенно свою поверхность, с помощью элемента данных `CDaoRecordset`.  
  
## Другие операции  
 Другие операции базы данных также предоставляются, например исправление поврежденной базы данных или сжатия базы данных.  
  
 Дополнительные сведения о вызов DAO напрямую и о безопасности DAO см. в разделе [Техническая примечание 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoWorkspace`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)