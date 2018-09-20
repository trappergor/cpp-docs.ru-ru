---
title: Структура CDaoFieldInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaf3f41bf6a6fe5d67ec5835d57889f6ec7dbae6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437693"
---
# <a name="cdaofieldinfo-structure"></a>Структура CDaoFieldInfo

`CDaoFieldInfo` Структура содержит сведения об объекте поля, определенные для объектах доступа к данным (DAO).

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

*m_strName*<br/>
Однозначно называет объект поля. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_nType*<br/>
Значение, указывающее тип данных поля. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO. Значение этого свойства может принимать одно из следующих значений:

- `dbBoolean` Да/Нет так же, как TRUE или FALSE

- `dbByte` байтов

- `dbInteger` короткий

- `dbLong` Long

- `dbCurrency` Валюта; класс MFC см. в разделе [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` Единый

- `dbDouble` Double

- `dbDate` Даты и времени; класс MFC см. в разделе [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` Текст; класс MFC см. в разделе [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` Long двоичный файл (OLE-объекта); Вы можете использовать класс MFC [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса `CLongBinary` как `CByteArray` является более широкие и проще в использовании.

- `dbMemo` MEMO; класс MFC см. в разделе `CString`

- `dbGUID` Глобально уникальный код/универсально уникальный идентификатор, используемый для вызовов удаленных процедур. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.

> [!NOTE]
>  Не используйте строковых типов данных для двоичных данных. В результате ваши данные, передаваемые через слой преобразования Юникода/ANSI, приведет к повышенной издержки и возможно непредвиденное преобразование.

*m_lSize*<br/>
Значение, указывающее максимальный размер в байтах, поля объекта DAO, который содержит текст или фиксированного размера поле объекта, содержащий текстовых или числовых. Дополнительные сведения см. в разделе «Свойство Size» в справке DAO. Размеры может принимать одно из следующих значений:

|Тип|Размер (байт)|Описание|
|----------|--------------------|-----------------|
|`dbBoolean`|1 байт|Да/Нет (то же, как True или False)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Целое число|
|`dbLong`|4|Long|
|`dbCurrency`|8|Валюта ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|Даты и времени ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Текст ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long двоичный файл (OLE-объекта; [CByteArray](../../mfc/reference/cbytearray-class.md); используйте вместо `CLongBinary`)|
|`dbMemo`|0|MEMO ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Глобально уникальный код/универсально уникальный идентификатор, используемый для вызовов удаленных процедур.|

*m_lAttributes*<br/>
Указывает характеристики объекта поля, содержащихся в tabledef, набор записей, querydef или индекс объекта. Возвращаемое значение может быть суммой эти константы, созданных с помощью C++ побитового или (**&#124;**) оператор:

- `dbFixedField` Размер поля является фиксированным (по умолчанию для числовых полей).

- `dbVariableField` Размер поля является переменной (только для текстового поля).

- `dbAutoIncrField` Значение поля для новых записей автоматически увеличивается на единицу в уникальный длинное целое число, которое нельзя изменить. Поддерживается только для таблиц базы данных Microsoft Jet.

- `dbUpdatableField` Можно изменить значение поля.

- `dbDescending` Поле сортируются в нисходящем (Z - A или 100-0) (применяется только к объекту поля в коллекцию полей индекса объекта; в MFC, индекс, сами объекты находятся в объектах tabledef) порядке. Если опустить этой константы, поле сортируется по возрастанию (A - Z или 0 – 100) порядке (по умолчанию).

При проверке значения свойства, можно использовать C++ побитовое- и оператор (**&**) для проверки конкретного атрибута. При установке нескольких атрибутов, их можно объединить, объединяя соответствующие константы с помощью побитового или (**&#124;**) оператор. Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

*m_nOrdinalPosition*<br/>
Значение, указывающее числовой порядок, в котором нужно полю, представленному объекту DAO поля для отображения относительно других полей. Можно задать это свойство с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Дополнительные сведения см. в разделе «OrdinalPosition свойство» в справке DAO.

*m_bRequired*<br/>
Указывает, требует ли объект поля DAO ненулевое значение. Если это свойство имеет значение TRUE, поле не допускает значение Null. При необходимости, имеет значение FALSE, это поле может содержать значения Null, а также значения, которые соответствуют условиям, заданным параметром значения свойств пустые строки и ValidationRule. Дополнительные сведения см. в разделе «Требуется свойство» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Указывает, является ли пустая строка ("») является допустимым значением объекта DAO поля с типом данных Text или Memo. Если это свойство имеет значение TRUE, пустая строка является допустимым значением. Это свойство можно задать значение false, чтобы убедиться, что нельзя использовать пустую строку для задания значения поля. Дополнительные сведения см. в разделе «Пустые строки свойство» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Указывает последовательность сортировки в текст для сравнения строк или сортировки. Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO. Список возможных значений, возвращаемых, см. в разделе `m_lCollatingOrder` членом [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) структуры. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Значение, в связи, имя объекта DAO поля во внешней таблице, которая соответствует полю в таблице первичного. Дополнительные сведения см. в разделе «ForeignName свойство» в справке DAO.

*m_strSourceField*<br/>
Указывает имя поля, которое является исходный источник данных для объекта поля DAO, содержащихся в tabledef, набор записей или querydef объекта. Это свойство указывает исходное имя поля, связанные с объект поля. Например может использовать это свойство для определения исходного источника данных в поле запроса, имя которого не соответствует имени поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField SourceTable свойства» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Указывает имя таблицы, которая является исходный источник данных для объекта поля DAO, содержащихся в tabledef, набор записей или querydef объекта. Это свойство указывает исходное имя таблицы, связанный с объектом поля. Например может использовать это свойство для определения исходного источника данных в поле запроса, имя которого не соответствует имени поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField SourceTable свойства» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Значение, которое проверяет данные в поле, изменить или добавить в таблицу. Дополнительные сведения см. в разделе «Значение» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

Дополнительные сведения о tabledefs см. в разделе `m_strValidationRule` членом [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) структуры.

*m_strValidationText*<br/>
Значение, указывающее текст сообщения, которое отображает приложения, если значение поля объекта DAO не удовлетворяет правила проверки, заданного параметром значения этого свойства ValidationRule. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
Значение по умолчанию объект поля DAO. При создании новой записи, значение свойства DefaultValue автоматически вводится в качестве значения для поля. Дополнительные сведения см. в разделе «Свойства DefaultValue» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Примечания

Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по `GetFieldInfo` функция-член в классах [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), и [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Класс MFC не представлены объектов полей. Вместо этого объекты следующие классы MFC DAO объектов содержат коллекции объектов поля: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), и [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Эти классы функции-члены для доступа к некоторых отдельных элементов сведений о поле, или можно доступа их все одновременно с `CDaoFieldInfo` путем вызова метода `GetFieldInfo` функция-член края содержащего его объекта.

Помимо использования для проверки свойств объекта, можно также использовать `CDaoFieldInfo` для построения для создания новых полей в tabledef входного параметра. Проще доступны для выполнения этой задачи, но если требуется детальный контроль, можно использовать версию [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , принимающий `CDaoFieldInfo` параметра.

Сведений, получаемых методом `GetFieldInfo` функцию-член (класс, который содержит поле) хранится в `CDaoFieldInfo` структуры. Вызовите `GetFieldInfo` функция-член края содержащего его объекта в коллекции которого поля хранится объект поля. `CDaoFieldInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoFieldInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

