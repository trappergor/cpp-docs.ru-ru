---
title: Структура CDaoFieldInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63fdab9bae7238f427ff2015beffd53570603af4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaofieldinfo-structure"></a>Структура CDaoFieldInfo
`CDaoFieldInfo` Структура содержит сведения об объекте поля, определенные для объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Однозначно имена полей объекта. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 `m_nType`  
 Значение, указывающее тип данных поля. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO. Значение этого свойства может быть одно из следующих значений:  
  
- **dbBoolean** Да/Нет, то же, что **TRUE**/**FALSE**  
  
- **dbByte** байтов  
  
- **dbInteger** короткие  
  
- **dbLong** Long  
  
- **dbCurrency** валюты, класс MFC см. в разделе [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle** один  
  
- **dbDouble** Double  
  
- **dbDate** даты и времени; класс MFC см. в разделе [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText** текст; класс MFC см. в разделе [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary** Long Binary (объекта OLE); вы можете использовать класс MFC [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса `CLongBinary` как `CByteArray` является более подробным и проще в использовании.  
  
- **dbMemo** Memo; класс MFC см.`CString`  
  
- **dbGUID** глобально уникальный идентификатор или универсальный уникальный идентификатор, используемый для вызовов удаленных процедур. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
> [!NOTE]
>  Не используйте строковых типов данных для двоичных данных. В результате данные передаются через уровень перевода Unicode-ANSI, возникающие при переводе увеличение издержек и возможно непредвиденных.  
  
 *m_lSize*  
 Значение, указывающее максимальный размер в байтах, DAO поле объекта, который содержит текст или фиксированного размера поля объекта, который содержит текст или числовых значений. Дополнительные сведения см. в разделе «Свойства Size» в справке DAO. Размеры может принимать одно из следующих значений:  
  
|Тип|Размер (байт)|Описание:|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 байт|Да/Нет (то же, как True или False)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Целое число|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Валюта ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Даты и времени ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Текст ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Длинные двоичные (OLE-объекта; [CByteArray](../../mfc/reference/cbytearray-class.md); используйте вместо `CLongBinary`)|  
|**dbMemo**|0|MEMO ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Глобально уникальный идентификатор или универсальный уникальный идентификатор, используемый для вызовов удаленных процедур.|  
  
 `m_lAttributes`  
 Задает характеристики поле объекта, находящегося tabledef, набор записей, querydef или индекс объекта. Возвращаемое значение может быть суммой эти константы, созданных с помощью C++ побитового или (**&#124;**) оператор:  
  
- **dbFixedField** поле фиксированный размер (по умолчанию для числовых полей).  
  
- **dbVariableField** размер поля является переменной (только текстовые поля).  
  
- **dbAutoIncrField** значение поля для новых записей автоматически увеличивается до уникальное целое число типа long, не может быть изменено. Поддерживается только для таблиц базы данных Microsoft Jet.  
  
- **dbUpdatableField** можно изменить значение поля.  
  
- **dbDescending** поле сортируется по убыванию (Z - A, или 100-0) порядке (применяется только к объекту поля в коллекцию полей индекса объекта, а в MFC, сами объекты находятся в объектах tabledef индекса). При отсутствии этой константы, поле сортируется по возрастанию (A - Z или 0 - 100) порядке (по умолчанию).  
  
 При проверке значения свойства, можно использовать C++ побитовое- и оператор (**&**) для проверки конкретного атрибута. При установке нескольких атрибутов, их можно объединить, объединяя соответствующие константы с побитового или (**&#124;**) оператор. Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
 *m_nOrdinalPosition*  
 Значение, указывающее числовой порядок, в котором нужно поля, представленного объекта DAO поле для отображения относительно других полей. Можно задать это свойство с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Дополнительные сведения см. в разделе «Свойство OrdinalPosition» в справке DAO.  
  
 `m_bRequired`  
 Указывает, требуется ли поле объекта DAO непустое значение. Если это свойство имеет **TRUE**, поле не допускает значение Null. При необходимости установлен в значение **FALSE**, поле может содержать значения Null, а также значения, которые соответствуют условиям, указанным пустые строки и ValidationRule параметры свойств. Дополнительные сведения см. в разделе «Необходимые свойства» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Указывает, является ли пустая строка ("») является допустимым значением объекта DAO поля с типом данных Text или Memo. Если это свойство имеет **TRUE**, пустая строка является допустимым значением. Это свойство можно задать **FALSE** чтобы убедиться, что нельзя использовать пустую строку для задания значения поля. Дополнительные сведения см. в разделе «Свойство пустые строки» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Задает последовательность порядка сортировки в текст для сравнения строк или сортировки. Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO. Список возможных значений, возвращаемых см. в разделе **m_lCollatingOrder** членом [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) структуры. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Значение, в связи, задает имя объекта поля DAO внешней таблицы, которая соответствует полю в таблице первичного. Дополнительные сведения см. в разделе «Свойство ForeignName» в справке DAO.  
  
 *m_strSourceField*  
 Указывает имя поля, которое находится исходный источник данных для поля объекта DAO tabledef, записей или querydef объекта. Это свойство указывает исходное имя поля, связанного с объектом поля. Например может использовать это свойство для определения исходного источника данных в поле запроса, имя которого не соответствует имени поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField свойства SourceTable» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Указывает имя таблицы, которая является исходный источник данных для поля объекта DAO tabledef, записей или querydef объекта. Это свойство указывает исходное имя таблицы, связанный с объектом поля. Например может использовать это свойство для определения исходного источника данных в поле запроса, имя которого не соответствует имени поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField свойства SourceTable» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Значение, которое проверяет данные в поле, изменить или добавить в таблицу. Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Дополнительные сведения о tabledefs см. в разделе **m_strValidationRule** членом [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) структуры.  
  
 `m_strValidationText`  
 Значение, указывающее текст сообщения, которое отображает приложения, если значение поля объекта DAO не удовлетворяет параметр ValidationRule свойства, заданные правила проверки. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 Значение по умолчанию, поле объекта DAO. При создании новой записи значение свойства DefaultValue автоматически вводится как значение для поля. Дополнительные сведения см. в разделе «Свойство DefaultValue» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Примечания  
 Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по `GetFieldInfo` функции-члена в классах [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), и [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Класс MFC не представлены объектов полей. Вместо этого базовых объектов следующие классы MFC DAO объектов содержат коллекции объектов полей: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), и [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Эти классы предоставьте функции-члены для доступа к некоторых отдельных элементов сведений о поле или может получить доступ к их все одновременно с `CDaoFieldInfo` путем вызова метода `GetFieldInfo` функции-члена вмещающего объекта.  
  
 Помимо использования для проверки свойств объекта, можно также использовать `CDaoFieldInfo` для построения для создания новых полей в tabledef входного параметра. Более простые параметры доступны для этой задачи, но если требуется более точное управление, можно использовать версию [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , который принимает `CDaoFieldInfo` параметра.  
  
 Сведений, получаемых методом `GetFieldInfo` функция-член (класса, который содержит поле) хранится в `CDaoFieldInfo` структуры. Вызовите `GetFieldInfo` функции-члена в Коллекция полей которого хранится объект поля вмещающего объекта. `CDaoFieldInfo`также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

