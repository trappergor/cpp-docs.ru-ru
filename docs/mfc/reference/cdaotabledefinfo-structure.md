---
title: "Структура CDaoTableDefInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4d1ac5ca00f98f8c34332ce2eb1a180ab715e6ba
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledefinfo-structure"></a>Структура CDaoTableDefInfo
`CDaoTableDefInfo` Структура содержит сведения об объекте tabledef, определенные для объектов доступа к данным (DAO).  
  
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
 `m_strName`  
 Дает уникальное название tabledef объекта. Чтобы получить значение этого свойства напрямую, вызовите объект tabledef [GetName](../../mfc/reference/cdaotabledef-class.md#getname) функции-члена. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, может ли внесены изменения в таблицу. Самый быстрый способ определить, является ли таблица обновляемых является открытие `CDaoTableDef` объекта для таблицы и вызов объекта [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) функции-члена. `CanUpdate`всегда возвращает ненулевое значение (**TRUE**) для объекта только что созданный tabledef и 0 (**FALSE**) tabledef вложенного объекта. Новый объект tabledef можно добавить только к базе данных, для которого у текущего пользователя есть разрешение на запись. Если таблица содержит только поля необновляемый `CanUpdate` возвращает 0. Если одно или несколько полей являются обновляемыми, `CanUpdate` возвращает ненулевое значение. Можно изменить только обновляемые поля. Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 `m_lAttributes`  
 Задает характеристики таблицы, представленной объектом tabledef. Чтобы получить текущие атрибуты tabledef, вызовите его [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) функции-члена. Возвращаемое значение может быть сочетанием этих длинных констант (с помощью побитового или (**|**) оператор):  
  
- **dbAttachExclusive** баз данных, использующих базы данных Microsoft Jet, указывает, открыт для монопольного использования подключенной таблицы является таблица.  
  
- **dbAttachSavePWD** для баз данных, использующих базы данных Microsoft Jet, указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.  
  
- **dbSystemObject** указывает таблица является системной таблицей, предоставляемые базы данных Microsoft Jet. (только для чтения).  
  
- **dbHiddenObject** указывает таблицу, скрытые таблице, предоставленной ядро базы данных Microsoft Jet (для временного использования). (только для чтения).  
  
- **dbAttachedTable** указывает таблицу, подключенной таблицы из базы данных не ODBC, такие как базы данных Paradox.  
  
- **dbAttachedODBC** указывает таблицу, подключенной таблицы из базы данных ODBC, например Microsoft SQL Server.  
  
 `m_dateCreated`  
 Дата и время создания таблицы. Для получения Дата создания таблицы непосредственно вызвать [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
 `m_dateLastUpdated`  
 Дата и время последнего изменения, внесенные в структуру таблицы. Для получения даты последнего обновления таблицы непосредственно вызвать [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
 *m_strSrcTableName*  
 Имя подключенной таблицы при их наличии. Для получения имени исходной таблицы непосредственно вызвать [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) функцию-член `CDaoTableDef` объект, связанный с таблицей.  
  
 `m_strConnect`  
 Предоставляет сведения об источнике открыть базу данных. Это свойство можно проверить, вызвав [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) функцию-член вашей `CDaoTableDef` объекта. Дополнительные сведения о строках подключения см. в разделе `GetConnect`.  
  
 `m_strValidationRule`  
 Значение, которое проверяет данные в полях tabledef, как они изменяются или добавить в таблицу. Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Для получения правило проверки непосредственно вызвать [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO.  
  
 `m_strValidationText`  
 Значение, указывающее текст сообщения, приложения должны отображаться, если правило проверки, указанного в свойстве ValidationRule не выполняется. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
 *m_lRecordCount*  
 Количество записей, доступных в объекте tabledef. Этот параметр доступен только для чтения. Для получения числа записей непосредственно вызвать [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) функцию-член `CDaoTableDef` объекта. В документации по `GetRecordCount` описывает дальнейшей число записей. Обратите внимание, что получение это число может быть длительной операции, если таблица содержит много записей.  
  
## <a name="remarks"></a>Примечания  
 Tabledef является объектом класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функции-члена в классе `CDaoDatabase`.  
  
 Данные, полученные по [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функции-члена хранится в `CDaoTableDefInfo` структуру. Вызов `GetTableDefInfo` функцию-член `CDaoDatabase` объекта, в которых TableDefs-коллекция хранится tabledef объект. `CDaoTableDefInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoTableDefInfo` объекта.  
  
 Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно с файлового сервера во избежание несоответствий в Дата создания и настройки свойств LastUpdated.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)

