---
title: "CDaoRecordset Class | Microsoft Docs"
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
  - "CDaoRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordset - класс"
  - "записи, CDaoRecordSet"
  - "наборы записей, типы"
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет набор записей, выбранных из источника данных.  
  
## Синтаксис  
  
```  
  
class CDaoRecordset : public CObject  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoRecordset::CDaoRecordset](../Topic/CDaoRecordset::CDaoRecordset.md)|Создает объект `CDaoRecordset`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoRecordset::AddNew](../Topic/CDaoRecordset::AddNew.md)|Подготавливает для добавления новой записи.  Вызов [обновление](../Topic/CDaoRecordset::Update.md) для выполнения сложения.|  
|[CDaoRecordset::CanAppend](../Topic/CDaoRecordset::CanAppend.md)|Возвращает ненулевое значение, если новых записей можно добавить к набору записей посредством функции\-члена [AddNew](../Topic/CDaoRecordset::AddNew.md).|  
|[CDaoRecordset::CanBookmark](../Topic/CDaoRecordset::CanBookmark.md)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|  
|[CDaoRecordset::CancelUpdate](../Topic/CDaoRecordset::CancelUpdate.md)|Отменяет все ожидающие обновления из\-за [правка](../Topic/CDaoRecordset::Edit.md) или операции [AddNew](../Topic/CDaoRecordset::AddNew.md).|  
|[CDaoRecordset::CanRestart](../Topic/CDaoRecordset::CanRestart.md)|Возвращает ненулевое значение, если [Requery](../Topic/CDaoRecordset::Requery.md) можно вызывать для выполнения запроса набора записей.|  
|[CDaoRecordset::CanScroll](../Topic/CDaoRecordset::CanScroll.md)|Возвращает ненулевое значение, если можно прокручивать записи.|  
|[CDaoRecordset::CanTransact](../Topic/CDaoRecordset::CanTransact.md)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|  
|[CDaoRecordset::CanUpdate](../Topic/CDaoRecordset::CanUpdate.md)|Возвращает ненулевое значение, если набор записей можно обновить \(можно добавлять, обновлять или удалять записи\).|  
|[CDaoRecordset::Close](../Topic/CDaoRecordset::Close.md)|Закрывает набор записей.|  
|[CDaoRecordset::Delete](../Topic/CDaoRecordset::Delete.md)|Удаляет текущую запись набора записей.  Необходимо явно выполнить прокрутку к другой записи после удаления.|  
|[CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)|Вызываемый для обмена данными \(в обоих направлениях\) между элементами данных полей набора записей и соответствующие записи в источнике данных.  Обмен полями записей DAO инструментов \(DFX\).|  
|[CDaoRecordset::Edit](../Topic/CDaoRecordset::Edit.md)|Подготавливает для изменения текущей записи.  Вызов **Обновить** для завершает правку.|  
|[CDaoRecordset::FillCache](../Topic/CDaoRecordset::FillCache.md)|Заполняет все или часть локального кэша для объекта набора записей, содержащий данные из источника данных ODBC.|  
|[CDaoRecordset::Find](../Topic/CDaoRecordset::Find.md)|Находит во\-первых, следующий, более ранней, либо последнее расположение указанной строки в наборе записей является динамическим подмножеством данных\- типа, удовлетворяющий указанному условию, и делает, который записывает текущую запись.|  
|[CDaoRecordset::FindFirst](../Topic/CDaoRecordset::FindFirst.md)|Находит первую запись в наборе записей является динамическим подмножеством данных\- типа или моментальный снимок\- типа, удовлетворяющий указанному условию, и делает, которое записывает текущую запись.|  
|[CDaoRecordset::FindLast](../Topic/CDaoRecordset::FindLast.md)|Находит последней записи в наборе записей является динамическим подмножеством данных\- типа или моментальный снимок\- типа, удовлетворяющий указанному условию, и делает, которое записывает текущую запись.|  
|[CDaoRecordset::FindNext](../Topic/CDaoRecordset::FindNext.md)|Найдите следующую запись в наборе записей является динамическим подмножеством данных\- типа или моментальный снимок\- типа, удовлетворяющий указанному условию, и делает, которое записывает текущую запись.|  
|[CDaoRecordset::FindPrev](../Topic/CDaoRecordset::FindPrev.md)|Найдите предыдущие записи в наборе записей является динамическим подмножеством данных\- типа или моментальный снимок\- типа, удовлетворяющий указанному условию, и делает, которое записывает текущую запись.|  
|[CDaoRecordset::GetAbsolutePosition](../Topic/CDaoRecordset::GetAbsolutePosition.md)|Возвращает номер записи текущей записи объекта набора записей.|  
|[CDaoRecordset::GetBookmark](../Topic/CDaoRecordset::GetBookmark.md)|Возвращает значение, которое представляет закладку для записи.|  
|[CDaoRecordset::GetCacheSize](../Topic/CDaoRecordset::GetCacheSize.md)|Возвращает значение, указывающее количество записей в наборе записей является динамическим подмножеством данных\- типа, содержащего данные локально, которые необходимо кэшировать из источника данных ODBC.|  
|[CDaoRecordset::GetCacheStart](../Topic/CDaoRecordset::GetCacheStart.md)|Возвращает значение, определяющее закладку первой записи в наборе записей, который необходимо кэшировать.|  
|[CDaoRecordset::GetCurrentIndex](../Topic/CDaoRecordset::GetCurrentIndex.md)|Возвращает `CString`, содержащий имя индекса последнего использовавшего ся для индексирования, табличного типа `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](../Topic/CDaoRecordset::GetDateCreated.md)|Возвращает дату и время создана базовая таблица была лежащие в основе `CDaoRecordset` объект|  
|[CDaoRecordset::GetDateLastUpdated](../Topic/CDaoRecordset::GetDateLastUpdated.md)|Возвращает дату и время самого последнего выполненного изменения в структуре базовой таблицы, лежащие в основе `CDaoRecordset` объект.|  
|[CDaoRecordset::GetDefaultDBName](../Topic/CDaoRecordset::GetDefaultDBName.md)|Возвращает имя по умолчанию источника данных.|  
|[CDaoRecordset::GetDefaultSQL](../Topic/CDaoRecordset::GetDefaultSQL.md)|Вызываемый для получения по умолчанию строку выполнить SQL.|  
|[CDaoRecordset::GetEditMode](../Topic/CDaoRecordset::GetEditMode.md)|Возвращает значение, указывающее состояние изменения для текущей записи.|  
|[CDaoRecordset::GetFieldCount](../Topic/CDaoRecordset::GetFieldCount.md)|Возвращает значение, представляющее число полей в наборе записей.|  
|[CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)|Возвращает сведения о конкретных типов полей в наборе записей.|  
|[CDaoRecordset::GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md)|Возвращает значение поля в наборе записей.|  
|[CDaoRecordset::GetIndexCount](../Topic/CDaoRecordset::GetIndexCount.md)|Получает количество индексов в таблице, лежащие в основе набора записей.|  
|[CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)|Возвращает различные типы сведений об индексе.|  
|[CDaoRecordset::GetLastModifiedBookmark](../Topic/CDaoRecordset::GetLastModifiedBookmark.md)|Используемый, чтобы определить последнее добавления или обновления записи.|  
|[CDaoRecordset::GetLockingMode](../Topic/CDaoRecordset::GetLockingMode.md)|Возвращает значение, указывающее, что тип блокировать то в силе во время редактирования.|  
|[CDaoRecordset::GetName](../Topic/CDaoRecordset::GetName.md)|Возвращает `CString`, содержащий имя набора записей.|  
|[CDaoRecordset::GetParamValue](../Topic/CDaoRecordset::GetParamValue.md)|Возвращает текущее значение указанного параметра, хранящиеся в базовом объекте DAOParameter.|  
|[CDaoRecordset::GetPercentPosition](../Topic/CDaoRecordset::GetPercentPosition.md)|Возвращает позицию текущей записи в процентах общее количество записей.|  
|[CDaoRecordset::GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Возвращает число записей, доступ к которым получен в объекте набора записей.|  
|[CDaoRecordset::GetSQL](../Topic/CDaoRecordset::GetSQL.md)|Получает строку SQL, используемый для выбора записей в наборе записей.|  
|[CDaoRecordset::GetType](../Topic/CDaoRecordset::GetType.md)|Вызываемый для указания типа набора записей. табличный тип, динамическое подмножество данных\-тип или моментальный снимок\-тип.|  
|[CDaoRecordset::GetValidationRule](../Topic/CDaoRecordset::GetValidationRule.md)|Возвращает `CString`, содержащий значение, которое проверяет данные по мере того, как они введены в поле.|  
|[CDaoRecordset::GetValidationText](../Topic/CDaoRecordset::GetValidationText.md)|Извлекает текст, отображаемый, если правило проверки не выполняется.|  
|[CDaoRecordset::IsBOF](../Topic/CDaoRecordset::IsBOF.md)|Возвращает ненулевое значение, если был расположен набор записей перед первой записью.  Отсутствует текущая запись.|  
|[CDaoRecordset::IsDeleted](../Topic/CDaoRecordset::IsDeleted.md)|Возвращает ненулевое значение, если набор записей располагается на удалянную запись.|  
|[CDaoRecordset::IsEOF](../Topic/CDaoRecordset::IsEOF.md)|Возвращает ненулевое значение, если набор записей был расположен после последней записи.  Отсутствует текущая запись.|  
|[CDaoRecordset::IsFieldDirty](../Topic/CDaoRecordset::IsFieldDirty.md)|Возвращает ненулевое значение, если было изменен указанное поле в текущей записи.|  
|[CDaoRecordset::IsFieldNull](../Topic/CDaoRecordset::IsFieldNull.md)|Возвращает ненулевое значение, если указанное поле в текущей записи равен null \(не имеющий значение\).|  
|[CDaoRecordset::IsFieldNullable](../Topic/CDaoRecordset::IsFieldNullable.md)|Возвращает ненулевое значение, если указанное поле в текущей записи можно задать значение null \(не имеющий значение\).|  
|[CDaoRecordset::IsOpen](../Topic/CDaoRecordset::IsOpen.md)|Возвращает ненулевое значение, если [Открытие](../Topic/CDaoRecordset::Open.md) было ранее вызываются.|  
|[CDaoRecordset::Move](../Topic/CDaoRecordset::Move.md)|Располагает набор записей с заданным количеством записей из текущей записи в любом направлении.|  
|[CDaoRecordset::MoveFirst](../Topic/CDaoRecordset::MoveFirst.md)|Располагает текущую запись в первую запись в наборе записей.|  
|[CDaoRecordset::MoveLast](../Topic/CDaoRecordset::MoveLast.md)|Располагает текущую запись на последнюю запись в наборе записей.|  
|[CDaoRecordset::MoveNext](../Topic/CDaoRecordset::MoveNext.md)|Располагает текущую запись в следующую запись в наборе записей.|  
|[CDaoRecordset::MovePrev](../Topic/CDaoRecordset::MovePrev.md)|Располагает текущую запись на предыдущую запись в наборе записей.|  
|[CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)|Создает новый набор записей из таблицы динамического подмножества данных или моментального снимка.|  
|[CDaoRecordset::Requery](../Topic/CDaoRecordset::Requery.md)|Запускает запрос набора записей, чтобы обновить выбранные записи.|  
|[CDaoRecordset::Seek](../Topic/CDaoRecordset::Seek.md)|Найдите запись в индексированном объекте набора записей пользователем табличного типа, удовлетворяющий указанному условию для текущего индекса и делает, которое записывает текущую запись.|  
|[CDaoRecordset::SetAbsolutePosition](../Topic/CDaoRecordset::SetAbsolutePosition.md)|Задает номер записи текущей записи объекта набора записей.|  
|[CDaoRecordset::SetBookmark](../Topic/CDaoRecordset::SetBookmark.md)|Располагает набор записей на запись, содержащий указанную закладку.|  
|[CDaoRecordset::SetCacheSize](../Topic/CDaoRecordset::SetCacheSize.md)|Задает значение, указывающее количество записей в наборе записей является динамическим подмножеством данных\- типа, содержащего данные локально, которые необходимо кэшировать из источника данных ODBC.|  
|[CDaoRecordset::SetCacheStart](../Topic/CDaoRecordset::SetCacheStart.md)|Устанавливает значение, определяющее закладку первой записи в наборе записей, который необходимо кэшировать.|  
|[CDaoRecordset::SetCurrentIndex](../Topic/CDaoRecordset::SetCurrentIndex.md)|Вызываемый для задания индексов в наборе записей пользователем табличный тип.|  
|[CDaoRecordset::SetFieldDirty](../Topic/CDaoRecordset::SetFieldDirty.md)|Помечает указанное поле в текущей записи изменен.|  
|[CDaoRecordset::SetFieldNull](../Topic/CDaoRecordset::SetFieldNull.md)|Задает значение указанного поля в текущей записи к null \(не имеющий значение\).|  
|[CDaoRecordset::SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)|Задает значение поля в наборе записей.|  
|[CDaoRecordset::SetFieldValueNull](../Topic/CDaoRecordset::SetFieldValueNull.md)|Задает значение поля в наборе записей значение null.  \(не имеющий значение\).|  
|[CDaoRecordset::SetLockingMode](../Topic/CDaoRecordset::SetLockingMode.md)|Задает значение, которое указывает тип блокирования, который необходимо запускать во время редактирования.|  
|[CDaoRecordset::SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)|Устанавливает текущее значение указанного параметра, хранящиеся в базовом объекте DAOParameter|  
|[CDaoRecordset::SetParamValueNull](../Topic/CDaoRecordset::SetParamValueNull.md)|Устанавливает текущее значение заданного параметра значение null \(не имеющий значение\).|  
|[CDaoRecordset::SetPercentPosition](../Topic/CDaoRecordset::SetPercentPosition.md)|Задает позицию текущей записи к расположению, соответствующая доля общему количеству записей в наборе записей.|  
|[CDaoRecordset::Update](../Topic/CDaoRecordset::Update.md)|Выполняет операцию `AddNew` или **Изменить** путем сохранения новых или отредактированные данных в источнике данных.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoRecordset::m\_bCheckCacheForDirtyFields](../Topic/CDaoRecordset::m_bCheckCacheForDirtyFields.md)|Содержит пометить указывающее, следует ли автоматически помечаются как изменен поля.|  
|[CDaoRecordset::m\_nFields](../Topic/CDaoRecordset::m_nFields.md)|Содержит число элементов данных полей в классе набора записей и число столбцов, выбранных набором записей из источника данных.|  
|[CDaoRecordset::m\_nParams](../Topic/CDaoRecordset::m_nParams.md)|Содержит число элементов данных параметров в классе набора записей — количество параметров, передаваемых с запросом набора записей|  
|[CDaoRecordset::m\_pDAORecordset](../Topic/CDaoRecordset::m_pDAORecordset.md)|Указатель на интерфейс DAO, лежащие в основе объекта набора записей.|  
|[CDaoRecordset::m\_pDatabase](../Topic/CDaoRecordset::m_pDatabase.md)|База данных\-источник для этого результирующего набора.  Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md).|  
|[CDaoRecordset::m\_strFilter](../Topic/CDaoRecordset::m_strFilter.md)|Содержит строку, используемую для построения выписку **WHERE** SQL.|  
|[CDaoRecordset::m\_strSort](../Topic/CDaoRecordset::m_strSort.md)|Содержит строку, используемую для построения выписку **ORDER BY** SQL.|  
  
## Заметки  
 Наборы записей" как "объекты `CDaoRecordset` доступны в следующих форм: 3  
  
-   Наборы записей пользователем табличные типы представляют собой базовую таблицу, которую можно использовать для просмотра, добавления, изменения или удаления записей из одной таблицы базы данных.  
  
-   Наборы записей является динамическим подмножеством данных\- типа результата запроса, который может иметь обновляемые записи.  Эти наборы записей набор записей, которые можно использовать для просмотра, добавления, изменения или удаления записей из базовой таблицы или таблиц базы данных.  Наборы записей является динамическим подмножеством данных\- типа могут содержать поля из одной или нескольких таблиц в базе данных.  
  
-   Наборы записей является моментальным снимок\- типа статическая копия набора записей, которые можно использовать для поиска данных или создавать отчеты.  Эти наборы записей могут содержать поля из одной или нескольких таблиц в базе данных, но не могут быть обновлены.  
  
 Каждая форма набора записей представляет набор записей в момент исправленных набор записей открыт.  При прокрутке к записи в наборе записей пользователем табличный тип или набор записей является динамическим подмножеством данных\- типа, отражает изменения, внесенные в записи после набора записей открыт или другими пользователями или другими наборами записей в приложении.  \(Набор записей является моментальным снимок\- типа a не может быть обновлен\). Можно использовать `CDaoRecordset` напрямую или наследование относящийся к приложению класс набора записей из `CDaoRecordset`.  Можно выполнить следующее.  
  
-   Прокрутка по записям.  
  
-   Задайте индекс и быстрый поиск с использованием [поиск](../Topic/CDaoRecordset::Seek.md) \(наборы записей пользователем табличный тип\).  
  
-   Поиск записей на основе сравнения строк: "\<", "\<\=", "\=", "\>\=" или "\>" \(наборы записей является динамическим подмножеством данных\- типа и моментальный снимок\- типа\).  
  
-   Обновление записи и укажите блокируя режим \(за исключением наборов записей является моментальным снимок\- типа\).  
  
-   Отфильтровать набор записей, чтобы ограничить записи, оно выберите пункт из доступных в источнике данных.  
  
-   Сортирует набор записей.  
  
-   Параметризация набора записей не будет настраивать его выделение со сведениями не известное до времени выполнения.  
  
 Предоставляет интерфейс классифицируйте `CDaoRecordset` подобно этому из класса `CRecordset`.  Основное отличие состоит в том, что данные доступа `CDaoRecordset` класса через объект доступа к данным \(DAO\) на основе OLE.  Класс `CRecordset` обращается к engine через ODBC \(ODBC\) и драйвер ODBC engine.  
  
> [!NOTE]
>  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  Можно получить доступ к источнику данных ODBC с помощью классов DAO; классы DAO обычно обеспечивают основные возможности, поскольку они относятся к ядру СУБД jet \(Майкрософт\).  
  
 Можно либо использовать `CDaoRecordset` напрямую или создания производного класса от `CDaoRecordset`.  Использование класса набора записей в любом случае, открыв базу данных и построения объекта набора записей передачи конструктором указатель на объект `CDaoDatabase`.  Можно также создать объект `CDaoRecordset` MFC и позволить создать временный объект `CDaoDatabase`.  Затем вызовите функцию\-член [Открытие](../Topic/CDaoRecordset::Open.md) набора записей, указывающий, должен ли объект набора записей пользователем табличного типа, набор записей является динамическим подмножеством данных\- типа или набор записей является моментальным снимок\- типа.  Вызов **Открыть** выбирает и извлекает данные из базы данных первая запись.  
  
 Использование функций\-членов и элементы данных объекта для прокрутки по записям и приводитесь для них.  В зависимости от операций доступно ли объект набора записей пользователем табличного типа, набор записей является динамическим подмножеством данных\- типа или набор записей является моментальным снимок\- типа и ли он, допускающие обновление или только для чтения " — это зависит от возможностей базы данных или источника данных ODBC \(ODBC\).  Обновление записи, которые могут быть изменены или добавлены поскольку вызов **Открыть**, вызывает функцию\-член [Requery](../Topic/CDaoRecordset::Requery.md) объекта.  Вызовите функцию\-член объекта **Закрыть** и уничтожение объекта после завершения с ним.  
  
 Обмен полями записей DAO польз `CDaoRecordset` \(DFX\) для поддержки чтение и обновление записи полей посредством типобезопасные элементов C\+\+ для `CDaoRecordset` или `CDaoRecordset`\- производного класса.  Также можно реализовать динамическую привязку столбцов в базе данных без использования механизма DFX с помощью [GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md) и [SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md).  
  
 Дополнительные сведения см. в разделе "объект набора записей" в Справке DAO.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoRecordset`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)