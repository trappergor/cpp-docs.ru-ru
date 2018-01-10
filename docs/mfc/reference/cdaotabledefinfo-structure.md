---
title: "Структура CDaoTableDefInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoTableDefInfo
dev_langs: C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e949cb0348cb55fcee5a940b5753a5a8197e600b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Однозначно называет tabledef объект. Чтобы получить значение этого свойства напрямую, вызовите объект tabledef [GetName](../../mfc/reference/cdaotabledef-class.md#getname) функции-члена. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, может ли внесены изменения в таблицу. Быстрый способ определить, является ли таблицы обновляемых — для открытия `CDaoTableDef` объекта для таблицы и вызвать объект [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) функции-члена. `CanUpdate`всегда возвращает ненулевое значение (**TRUE**) для объекта только что созданный tabledef и 0 (**FALSE**) tabledef вложенного объекта. Новый объект tabledef можно добавить только к базе данных, для которого у текущего пользователя есть разрешение на запись. Если таблица содержит только поля необновляемый `CanUpdate` возвращает 0. Если одно или несколько полей могут быть обновлены, `CanUpdate` возвращает ненулевое значение. Можно изменить только обновляемых полей. Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 `m_lAttributes`  
 Задает характеристики таблицы, представленной объектом tabledef. Чтобы получить текущие атрибуты tabledef, вызовите его [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) функции-члена. Возвращаемое значение может быть сочетанием этих констант long (с помощью побитового или (**&#124;**) оператор):  
  
- **dbAttachExclusive** для баз данных, использующих базы данных Microsoft Jet, указывает, вложенные таблицы, открыт для монопольного использования.  
  
- **dbAttachSavePWD** для баз данных, использующих базы данных Microsoft Jet, указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.  
  
- **dbSystemObject** указывает таблица является системной таблицей, предоставляемые базы данных Microsoft Jet. (только для чтения).  
  
- **dbHiddenObject** указывает скрытые таблицы, предоставляемые ядро базы данных Microsoft Jet (для временного использования). (только для чтения).  
  
- **dbAttachedTable** указывает вложенные таблицы из базы данных не ODBC, такие как базы данных Paradox.  
  
- **dbAttachedODBC** указывает вложенные таблицы из базы данных ODBC, например Microsoft SQL Server.  
  
 `m_dateCreated`  
 Дата и время создания таблицы. Для получения даты, таблица была создана непосредственно вызвать [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
 `m_dateLastUpdated`  
 Дата и время последнего изменения, внесенные в структуру таблицы. Для получения даты последнего обновления таблицы непосредственно вызвать [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. примечания ниже. Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
 *m_strSrcTableName*  
 Указывает имя подключенной таблицы, если таковые имеются. Для получения имени исходной таблицы непосредственно вызвать [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) функцию-член `CDaoTableDef` объект, связанный с таблицей.  
  
 `m_strConnect`  
 Предоставляет сведения об источнике открытую базу данных. Это свойство можно проверить, вызвав [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) функцию-член вашей `CDaoTableDef` объекта. Дополнительные сведения о строках соединения см `GetConnect`.  
  
 `m_strValidationRule`  
 Значение, которое проверяет данные в полях tabledef, как они изменяются или добавить в таблицу. Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Для получения непосредственно правило проверки, вызовите [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) функцию-член `CDaoTableDef` объект, связанный с таблицей. Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO.  
  
 `m_strValidationText`  
 Значение, указывающее текст сообщения, приложения должны отображаться, если правило проверки, указанного в свойстве ValidationRule условие не удовлетворено. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
 *m_lRecordCount*  
 Число записей, получить доступ к объекту tabledef. Этот параметр доступен только для чтения. Для получения числа записей непосредственно вызвать [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) функцию-член `CDaoTableDef` объекта. Документация по `GetRecordCount` описывает дальнейшей числа записей. Обратите внимание, что получение это число может быть длительной операции, если таблица содержит много записей.  
  
## <a name="remarks"></a>Примечания  
 Объект класса является tabledef [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функции-члена в классе `CDaoDatabase`.  
  
 Сведений, получаемых методом [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) функции-члена хранится в `CDaoTableDefInfo` структуры. Вызовите `GetTableDefInfo` функцию-член `CDaoDatabase` объекта, в которых TableDefs-коллекция tabledef объект сохраняется. `CDaoTableDefInfo`также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoTableDefInfo` объекта.  
  
 Параметры даты и времени являются производными от компьютера, на котором была создана или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно с файлового сервера, чтобы избежать несоответствия в DateCreated и LastUpdated параметры свойств.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
