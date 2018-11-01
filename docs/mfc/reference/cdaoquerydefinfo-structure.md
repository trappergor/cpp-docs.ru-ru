---
title: Структура CDaoQueryDefInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: f3c8b464a84bd33d15a19f24010b942bdea59620
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602999"
---
# <a name="cdaoquerydefinfo-structure"></a>Структура CDaoQueryDefInfo

`CDaoQueryDefInfo` Структура содержит сведения об объекте querydef, определенные для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет querydef объект. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO. Вызовите [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) получить это свойство напрямую.

*m_nType*<br/>
Значение, указывающее операционного типа объекта querydef. Он может иметь одно из следующих значений:

- `dbQSelect` SELECT — запрос выбирает записи.

- `dbQAction` Действия — запрос перемещается или изменяет данные, но не возвращает записей.

- `dbQCrosstab` Перекрестный — запрос возвращает данные в формате электронной таблицы.

- `dbQDelete` DELETE — запрос удаляет набор указанных строк.

- `dbQUpdate` Обновление – запрос изменяется набор записей.

- `dbQAppend` Добавление, запрос добавляет новые записи в конец таблицы или запроса.

- `dbQMakeTable` Создание таблицы, запрос создает новую таблицу из набора записей.

- `dbQDDL` Определение данных, запрос может относиться структуры таблиц или их части.

- `dbQSQLPassThrough` Сквозной — инструкция SQL передается непосредственно к серверной части базы данных, без промежуточной обработки.

- `dbQSetOperation` UNION, запрос создает объект набора записей типа, содержащий данные из всех указанных записей в двух или нескольких таблиц с повторяющихся записей удален. Чтобы включить повторяющиеся записи, добавьте ключевое слово **все** в querydef инструкции SQL.

- `dbQSPTBulk` Используется с `dbQSQLPassThrough` , чтобы определить запрос, который не возвращает записей.

> [!NOTE]
>  Чтобы создать запрос к серверу SQL, не следует задавать `dbQSQLPassThrough` константы. Это задается автоматически ядром СУБД Microsoft Jet при создании объекта querydef и задать свойство Connect.

Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.

*m_dateCreated*<br/>
Дата и время создания querydef. Чтобы напрямую получить дату создания querydef, вызовите [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Также см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

*m_dateLastUpdated*<br/>
Дата и время последнего изменения, внесенные в querydef. Чтобы напрямую получить дату последнего обновления таблицы, вызовите [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) querydef функцию-член. Дополнительные сведения см. примечания ниже. И справки DAO см. в разделе «DateCreated LastUpdated свойства».

*m_bUpdatable*<br/>
Указывает, можно ли сделать изменения в объект querydef. Если это свойство имеет значение TRUE, querydef является обновляемым; в противном случае он не является. Возможно обновление означает, что можно изменить определение объекта querydef запроса. Обновляемое свойство объекта querydef имеет значение TRUE, если можно обновить определение запроса, даже если результирующий набор записей не может быть обновлено. Чтобы получить это свойство напрямую, вызовите querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) функция-член. Дополнительные сведения см. в разделе «Обновляемые свойство» в справке DAO.

*m_bReturnsRecords*<br/>
Показывает, возвращает ли запрос к серверу SQL внешней базе данных записей. Если это свойство имеет значение TRUE, то запрос возвращает записи. Чтобы получить это свойство напрямую вызвать [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Не все запросы к серверу для внешних баз данных возвращает записи. Например, SQL **обновление** инструкция обновляет записи, не возвращая записи при SQL **ВЫБЕРИТЕ** инструкция возвращает записи. Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.

*m_strSQL*<br/>
Инструкция SQL, определяющий запрос, выполняемый с помощью объекта querydef. Свойство SQL содержит инструкцию SQL, которая определяет как запись, сгруппированных и упорядоченные при выполнении запроса. Запрос можно использовать для выбора записей в объекте recordset добавляющий или моментального снимка. Можно также определить массового запросов для изменения данных, не возвращая записи. Значение этого свойства можно получить напрямую путем вызова querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) функция-член.

*m_strConnect*<br/>
Сведения об источнике базы данных, используемой в запросе к серверу. Эти данные принимают строки подключения. Дополнительные сведения о объединение строк и сведения о получении значения этого свойства напрямую, см. в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функция-член.

*m_nODBCTimeout*<br/>
Количество секунд ожидания ядра СУБД Microsoft Jet, прежде чем выдать ошибку времени ожидания происходит, когда запрос выполняется в базе данных ODBC. Если вы используете базу данных ODBC, например Microsoft SQL Server, из-за сетевой трафик или большим числом операций использования сервера ODBC могут возникать задержки. Вместо того чтобы без ограничения времени ожидания, можно указать время ожидания ядра Microsoft Jet, прежде чем он выводит сообщение об ошибке. По умолчанию время ожидания составляет 60 секунд. Значение этого свойства можно получить напрямую путем вызова querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) функция-член. Дополнительные сведения см. в разделе «Время ожидания ODBC свойство» в справке DAO.

## <a name="remarks"></a>Примечания

Объект класса является querydef [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функции-члена в классе `CDaoDatabase`.

Сведений, получаемых методом [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функция-член хранится в `CDaoQueryDefInfo` структуры. Вызовите `GetQueryDefInfo` для объекта базы данных, в которых querydefs-коллекция querydef объект сохраняется. `CDaoQueryDefInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoQueryDefInfo` объекта. Класс `CDaoDatabase` также предоставляет функции-члены для прямого доступа к все свойства, возвращаемые в `CDaoQueryDefInfo` объекта, поэтому, возможно, редко нужно вызывать `GetQueryDefInfo`.

При добавлении нового поля, либо объект параметра в коллекцию полей или параметров объекта querydef, исключение возникает в том случае, если основной базе данных не поддерживает тип данных, указанный для нового объекта.

Параметры даты и времени являются производными от компьютера, на котором querydef создания или последнего обновления. В многопользовательской среде, пользователи должны получить эти параметры непосредственно из файлового сервера с помощью **net время** команду, чтобы избежать несоответствия в значения свойств DateCreated и LastUpdated.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
