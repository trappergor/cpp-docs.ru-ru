---
title: Структура CDaoTableDefInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 5785ed19c6929e19c7d376efa012dd1c059611c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152102"
---
# <a name="cdaotabledefinfo-structure"></a>Структура CDaoTableDefInfo

`CDaoTableDefInfo` Структура содержит сведения об объекте tabledef, определенные для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет tabledef объект. Чтобы получить значение этого свойства напрямую, вызовите объект tabledef [GetName](../../mfc/reference/cdaotabledef-class.md#getname) функция-член. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_bUpdatable*<br/>
Указывает, можно ли сделать изменения в таблицу. Быстро определить, является ли таблица обновляемых, чтобы открыть `CDaoTableDef` объекта для таблицы и вызвать для объекта [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) функция-член. `CanUpdate` всегда возвращает ненулевое значение (TRUE) для объекта только что созданный tabledef и 0 (FALSE) tabledef присоединенного объекта. Новый объект tabledef могут быть добавлены только к базе данных, для которого у текущего пользователя есть разрешение на запись. Если таблица содержит только поля необновляемый `CanUpdate` возвращает 0. Если одно или несколько полей являются обновляемыми, `CanUpdate` возвращает ненулевое значение. Можно изменить только обновляемые поля. Дополнительные сведения см. в разделе «Обновляемые свойство» в справке DAO.

*m_lAttributes*<br/>
Указывает характеристики таблицы, представленной объектом tabledef. Чтобы получить атрибуты текущего tabledef, вызовите его [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) функция-член. Возвращаемое значение может представлять собой сочетание этих длинных констант (с помощью побитового или (**&#124;**) оператор):

- `dbAttachExclusive` Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.

- `dbAttachSavePWD` Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.

- `dbSystemObject` Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet. (только для чтения).

- `dbHiddenObject` Указывает, что таблица является таблицей скрытые, предоставляемые Microsoft Jet database engine (для временного использования). (только для чтения).

- `dbAttachedTable` Указывает, что таблица является подключенной таблицы из базы данных не ODBC, например в базе данных Paradox.

- `dbAttachedODBC` Указывает, что таблица является подключенной таблицы из базы данных ODBC, например Microsoft SQL Server.

*m_dateCreated*<br/>
Дата и время создания таблицы. Чтобы напрямую получить дату создания таблицы, вызовите [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

*m_dateLastUpdated*<br/>
Дата и время последнего изменения, внесенные в структуру таблицы. Чтобы напрямую получить дату последнего обновления таблицы, вызовите [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

*m_strSrcTableName*<br/>
Указывает имя подключенной таблицы, если таковые имеются. Чтобы напрямую получить имя исходной таблицы, вызовите [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) функцию-член `CDaoTableDef` объект, связанный с таблицей.

*m_strConnect*<br/>
Сведения об источнике открытую базу данных. Это свойство можно проверить, вызвав [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) функцию-член вашей `CDaoTableDef` объекта. Дополнительные сведения о строках соединения см `GetConnect`.

*m_strValidationRule*<br/>
Значение, которое проверяет данные в полях tabledef, так как они изменяются или добавить в таблицу. Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Чтобы напрямую получить правила проверки, вызовите [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. в разделе «Значение» в справке DAO.

*m_strValidationText*<br/>
Значение, указывающее текст сообщения, приложения должны отображаться, если правило проверки, указанного в свойстве ValidationRule не удовлетворяется. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.

*m_lRecordCount*<br/>
Количество записей, доступных в объекте tabledef. Этот параметр доступен только для чтения. Чтобы напрямую получить число записей, вызовите [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) функцию-член `CDaoTableDef` объекта. В документации по `GetRecordCount` описывает дальнейшей числа записей. Обратите внимание на то, что получение это число может быть длительной операции, если таблица содержит много записей.

## <a name="remarks"></a>Примечания

Объект класса является tabledef [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функции-члена в классе `CDaoDatabase`.

Сведений, получаемых методом [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функция-член хранится в `CDaoTableDefInfo` структуры. Вызовите `GetTableDefInfo` функцию-член `CDaoDatabase` объекта, в которых tabledefs-коллекция tabledef объект сохраняется. `CDaoTableDefInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoTableDefInfo` объекта.

Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно с файлового сервера, чтобы избежать несоответствия в DateCreated и параметры свойств LastUpdated.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
