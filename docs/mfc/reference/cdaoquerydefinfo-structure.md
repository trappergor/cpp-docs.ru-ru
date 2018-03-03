---
title: "Структура CDaoQueryDefInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e476fd8e95b48b59bbb3bae41d9ad84829ca8fa9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoquerydefinfo-structure"></a>Структура CDaoQueryDefInfo
`CDaoQueryDefInfo` Структура содержит сведения об объекте querydef, определенные для объектов доступа к данным (DAO).  
  
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
 `m_strName`  
 Дает уникальное название объекта querydef. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO. Вызовите [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) Чтобы получить это свойство напрямую.  
  
 `m_nType`  
 Значение, указывающее тип оперативной объекта querydef. Он может иметь одно из следующих значений:  
  
- **dbQSelect** выберите — запрос выбирает записи.  
  
- **dbQAction** действие — запрос перемещается или изменяет данные, но не возвращает записи.  
  
- **dbQCrosstab** перекрестного — запрос возвращает данные в формате, подобном электронной таблицы.  
  
- **dbQDelete** удалить — запрос удаляет набор указанных строк.  
  
- **dbQUpdate** обновления — запрос изменяется набор записей.  
  
- **dbQAppend** Append — запрос добавляет новые записи в конец таблицы или запроса.  
  
- **dbQMakeTable** создание таблицы, запрос создает новую таблицу из набора записей.  
  
- **dbQDDL** определение данных — запрос влияет на структуру таблицы или их частей.  
  
- **dbQSQLPassThrough** сквозной — инструкция SQL передается непосредственно в серверной базе данных, без промежуточной обработки.  
  
- **dbQSetOperation** Union, запрос создает объект набора записей статического типа, содержащий данные из всех указанных записей в двух или более таблиц с какие-либо повторяющиеся записи удаляется. Чтобы включить повторяющиеся значения, добавьте ключевое слово **все** в инструкции SQL querydef.  
  
- **dbQSPTBulk** с **dbQSQLPassThrough** для указания запроса, который возвращает записи.  
  
> [!NOTE]
>  Чтобы создать запрос к серверу SQL, не следует задавать **dbQSQLPassThrough** константой. Он задается автоматически ядром базы данных Microsoft Jet при создании объекта querydef и задать свойству Connect.  
  
 Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
 `m_dateCreated`  
 Дата и время создания querydef. Для получения Дата создания querydef непосредственно вызвать [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Также см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
 `m_dateLastUpdated`  
 Дата и время последнего изменения, внесенные в querydef. Для получения даты последнего обновления таблицы непосредственно вызвать [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) querydef функцию-член. Дополнительные сведения см. примечания ниже. И см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, может ли внесены изменения в объект querydef. Если это свойство имеет **TRUE**, querydef является обновляемым; в противном случае, это не так. Возможно обновление означает, что можно изменить определение запроса объекта querydef. Обновляемое свойство объекта querydef равно **TRUE** при определении запроса можно обновить, даже если результирующий набор записей, не является обновляемым. Чтобы получить это свойство напрямую, вызовите querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) функции-члена. Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 *m_bReturnsRecords*  
 Показывает, возвращает ли запрос к серверу SQL к внешней базе данных записей. Если это свойство имеет **TRUE**, запрос возвращает записи. Для получения этого свойства непосредственно вызвать [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Не все запросы к серверу для внешних баз данных возвращает записи. Например, SQL **обновление** инструкция обновляет записи без возврата записей при SQL **ВЫБЕРИТЕ** инструкция возвращает записи. Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.  
  
 *m_strSQL*  
 Инструкция SQL, который определяет запрос, выполняемый с помощью объекта querydef. Свойство SQL содержит инструкцию SQL, определяющую, каким образом выбраны записи, сгруппированные и упорядоченные при выполнении запроса. Запрос можно использовать для выбора записей в объекте recordset добавляющий или моментальных снимков. Можно также определить запросы массовое изменение данных без возврата записей. Значение этого свойства можно получить непосредственно, путем вызова querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) функции-члена.  
  
 `m_strConnect`  
 Предоставляет сведения об источнике базы данных, используемой в запросе к серверу. Эта информация состоит из строки подключения. Дополнительные сведения о объединение строк и сведения о непосредственно получение значения данного свойства см. в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функции-члена.  
  
 *m_nODBCTimeout*  
 Количество секунд ожидания базы данных Microsoft Jet, прежде чем выдать ошибку времени ожидания происходит при запуске запроса в базе данных ODBC. При использовании базы данных ODBC, например Microsoft SQL Server из-за сетевой трафик или доступно использование сервера ODBC могут возникать задержки. Вместо ожидания, можно указать время ожидания ядра Microsoft Jet, прежде чем произойдет ошибка. Значение времени ожидания по умолчанию — 60 секунд. Значение этого свойства можно получить непосредственно, путем вызова querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) функции-члена. Дополнительные сведения см. в разделе «Время ожидания ODBC свойство» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 Объект класса является querydef [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функции-члена в классе `CDaoDatabase`.  
  
 Сведений, получаемых методом [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функции-члена хранится в `CDaoQueryDefInfo` структуры. Вызовите `GetQueryDefInfo` для объекта базы данных, в которых QueryDefs-коллекция хранится объект querydef. `CDaoQueryDefInfo`также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoQueryDefInfo` объекта. Класс `CDaoDatabase` также предоставляет функции-члены для прямого доступа к все свойства, возвращаемые в `CDaoQueryDefInfo` объекта, поэтому редко, возможно, нужно вызывать `GetQueryDefInfo`.  
  
 Если добавить новое поле или объект параметра в коллекцию полей или параметров объекта querydef, исключение создается в том случае, если основной базы данных не поддерживает тип данных, указанный для нового объекта.  
  
 Параметры даты и времени являются производными от компьютера, на котором querydef создания или последнего обновления. В многопользовательской среде, пользователи должны получить эти параметры напрямую из файлового сервера с помощью **в течение времени** команду, чтобы избежать несоответствия в значения свойств DateCreated и LastUpdated.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
