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
- CDaoQueryDefInfo structure
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 80e681345091ef54e2be2e3f1c1ea6ccaefd9d17
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
 Дает уникальное название объекта querydef. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO. Вызов [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) Чтобы получить это свойство напрямую.  
  
 `m_nType`  
 Значение, указывающее операционного типа объекта querydef. Значение может быть одним из следующих:  
  
- **dbQSelect** выберите — запрос выбирает записи.  
  
- **dbQAction** действия — запрос перемещается или изменения данных, но не возвращает записей.  
  
- **dbQCrosstab** перекрестного — запрос возвращает данные в формате электронной таблицы.  
  
- **dbQDelete** удалить — запрос удаляет набор указанных строк.  
  
- **dbQUpdate** обновления — запрос изменяется набор записей.  
  
- **dbQAppend** Append — запрос добавляет новые записи в конец таблицы или запроса.  
  
- **dbQMakeTable** создание таблицы, запрос создает новую таблицу из набора записей.  
  
- **dbQDDL** определение данных — запрос влияет на структуру таблицы или их частей.  
  
- **dbQSQLPassThrough** к серверу — инструкция SQL передается непосредственно в серверной части базы данных, без промежуточной обработки.  
  
- **dbQSetOperation** Union, запрос создает объект набора записей статического типа, содержащий данные из всех указанных записей в двух или более таблиц с повторяющихся записей удаляется. Чтобы включить повторяющиеся записи, добавьте ключевое слово **все** в инструкции SQL querydef.  
  
- **dbQSPTBulk** с **dbQSQLPassThrough** указать запрос, который возвращает записи.  
  
> [!NOTE]
>  Чтобы создать запрос к серверу SQL, не следует задавать **dbQSQLPassThrough** константой. Он задается автоматически ядром базы данных Microsoft Jet при создании объекта querydef и задать свойству Connect.  
  
 Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
 `m_dateCreated`  
 Дата и время создания querydef. Для получения Дата создания querydef непосредственно вызвать [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Также см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
 `m_dateLastUpdated`  
 Дата и время последнего изменения, внесенные в querydef. Для получения даты последнего обновления таблицы непосредственно вызвать [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) querydef функцию-член. Дополнительные сведения см. примечания ниже. И см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, может ли внесены изменения в объект querydef. Если это свойство имеет **TRUE**querydef обновляемых; в противном случае, это не так. Возможно обновление означает, что можно изменить определение объекта querydef запроса. Обновляемое свойство объекта querydef присвоено **TRUE** при определении запроса можно обновить, даже если результирующий набор записей не является обновляемым. Чтобы получить это свойство напрямую, вызовите querydef [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) функции-члена. Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 *m_bReturnsRecords*  
 Показывает, возвращает ли запрос к серверу SQL к внешней базе данных записей. Если это свойство имеет **TRUE**, запрос возвращает записи. Для получения этого свойства непосредственно вызвать [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Не все запросы к серверу для внешних баз данных возвращать записи. Например, SQL **обновление** инструкция обновляет записи без возвращения записей при SQL **ВЫБЕРИТЕ** инструкции возвращают записи. Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.  
  
 *m_strSQL*  
 Инструкция SQL, определяет запрос, выполняемый с помощью объекта querydef. Свойство SQL содержит инструкцию SQL, которая определяет, как будут выбраны записи, сгруппированных и упорядоченные при выполнении запроса. Можно использовать запрос для выбора записей в объекте recordset типа динамических подмножеств данных и моментальных снимков. Можно также определить массовые запросы для изменения данных без возвращения записей. Значение этого свойства можно получить непосредственно, вызывая метод querydef [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) функции-члена.  
  
 `m_strConnect`  
 Предоставляет сведения об источнике базы данных, используемой в запросе к серверу. Эта информация состоит из строки подключения. Дополнительные сведения о объединение строк и сведения о получении значения этого свойства непосредственно в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функции-члена.  
  
 *m_nODBCTimeout*  
 Количество секунд ожидания перед тайм-аута базы данных Microsoft Jet возникает при запуске запроса в базе данных ODBC. При использовании базы данных ODBC, например Microsoft SQL Server из-за использования сети трафика или большой нагрузки на сервер ODBC могут возникать задержки. Вместо ожидания, можно указать время ожидания ядра Microsoft Jet, прежде чем произойдет ошибка. Значение времени ожидания по умолчанию составляет 60 секунд. Значение этого свойства можно получить непосредственно, вызывая метод querydef [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) функции-члена. Дополнительные сведения см. в разделе «Время ожидания ODBC свойство» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 Querydef является объектом класса [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функции-члена в классе `CDaoDatabase`.  
  
 Данные, полученные по [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) функции-члена хранится в `CDaoQueryDefInfo` структуру. Вызов `GetQueryDefInfo` для объекта базы данных, в которых QueryDefs-коллекция хранится объекта querydef. `CDaoQueryDefInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoQueryDefInfo` объекта. Класс `CDaoDatabase` также предоставляет функции-члены для прямого доступа к все свойства, возвращаемые в `CDaoQueryDefInfo` объекта, поэтому, возможно, редко нужно вызывать `GetQueryDefInfo`.  
  
 При добавлении нового поля или объект параметра в коллекцию полей или параметров объекта querydef, создано исключение, если базы данных не поддерживает тип данных, указанный для нового объекта.  
  
 Параметры даты и времени являются производными от компьютера, на котором querydef создания или последнего обновления. В многопользовательской среде, пользователи должны получить эти параметры непосредственно из файла сервера с помощью **в течение времени** команду, чтобы избежать несоответствия в значения свойств DateCreated и LastUpdated.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)

