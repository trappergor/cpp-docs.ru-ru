---
title: Структура CDaoFieldInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: e2638ac908e4e286530301bc913173e87008df47
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303700"
---
# <a name="cdaofieldinfo-structure"></a>Структура CDaoFieldInfo

Структура `CDaoFieldInfo` содержит сведения об объекте поля, определенном для объектов доступа к данным (DAO).

DAO поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей.

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
Уникально именует объект Field. Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_nType*<br/>
Значение типа, указывающее тип данных поля. Дополнительные сведения см. в разделе "свойство Type" справки DAO. Значение этого свойства может быть одним из следующих:

- `dbBoolean` да/нет, то же, что и TRUE/FALSE

- `dbByte` байт

- `dbInteger` короткий

- `dbLong` Long

- `dbCurrency` Валюта; см. класс MFC [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` один

- `dbDouble` Double

- `dbDate` Дата и время; см. класс MFC [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` текст; см. класс MFC в [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` длинный двоичный файл (объект OLE); Вы можете использовать класс MFC класса [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса `CLongBinary`, так как `CByteArray` более широка и удобна в использовании.

- `dbMemo` ноте; см. раздел MFC Class `CString`

- `dbGUID` глобальный уникальный идентификатор или универсальный уникальный идентификатор, используемый с удаленными вызовами процедур. Дополнительные сведения см. в разделе "свойство Type" справки DAO.

> [!NOTE]
>  Не используйте типы данных String для двоичных данных. Это приводит к тому, что данные проходят через уровень преобразования Unicode/ANSI, что приводит к увеличению затрат и, возможно, непредвиденному преобразованию.

*m_lSize*<br/>
Значение, указывающее максимальный размер (в байтах) объекта поля DAO, содержащего текст, или фиксированный размер объекта поля, содержащего текстовые или числовые значения. Дополнительные сведения см. в разделе "свойство size" справки DAO. Размеры могут иметь одно из следующих значений:

|Введите|Размер (байт)|Описание|
|----------|--------------------|-----------------|
|`dbBoolean`|1 байт|Да/нет (то же, что и true/false)|
|`dbByte`|1|Байт|
|`dbInteger`|2|Целое число|
|`dbLong`|4|Long|
|`dbCurrency`|8|Валюта ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|Дата и время ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Text ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (объект OLE; [CByteArray](../../mfc/reference/cbytearray-class.md); Используйте вместо `CLongBinary`)|
|`dbMemo`|0|МЕМО ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Глобальный уникальный идентификатор или универсальный уникальный идентификатор, используемый с удаленными вызовами процедур.|

*m_lAttributes*<br/>
Задает характеристики объекта поля, содержащегося в объекте tabledef, Recordset, QueryDef или index. Возвращаемое значение может быть суммой этих констант, созданных с помощью оператора C++ побитового или **&#124;** ():

- `dbFixedField` размер поля фиксирован (по умолчанию для числовых полей).

- `dbVariableField` размер поля является переменной (только текстовые поля).

- `dbAutoIncrField` значение поля для новых записей автоматически увеличивается до уникального длинного целого числа, которое нельзя изменить. Поддерживается только для таблиц базы данных Microsoft Jet.

- `dbUpdatableField` значение поля можно изменить.

- `dbDescending` поле сортируется в порядке убывания (Z-A или 100-0) (применяется только к объекту Field в коллекции полей объекта index; в MFC объекты индекса сами по себе содержатся в объектах tabledef). Если опустить эту константу, поле будет отсортировано в порядке возрастания (A – Z или 0-100) (по умолчанию).

При проверке значения этого свойства можно использовать оператор C++ побитового и ( **&** ) для проверки конкретного атрибута. При задании нескольких атрибутов их можно объединить, объединив соответствующие константы с оператором побитового или **&#124;** (). Дополнительные сведения см. в разделе «свойство Attributes» справки DAO.

*m_nOrdinalPosition*<br/>
Значение, указывающее числовой порядок, в котором должно отображаться поле, представленное объектом поля DAO, относительно других полей. Это свойство можно задать с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield). Дополнительные сведения см. в разделе "свойство Ординалпоситион" справки DAO.

*m_bRequired*<br/>
Указывает, требуется ли для объекта поля DAO значение, отличное от NULL. Если это свойство имеет значение TRUE, поле не допускает значение null. Если параметру требуется присвоено значение FALSE, поле может содержать значения NULL, а также значения, соответствующие условиям, заданным в параметрах свойства AllowZeroLength и ValidationRule. Дополнительные сведения см. в подразделе «обязательное свойство» справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Указывает, является ли пустая строка ("") допустимым значением объекта поля DAO с типом данных text или MEMO. Если это свойство имеет значение TRUE, то пустая строка является допустимым значением. Для этого свойства можно задать значение FALSE, чтобы не использовать пустую строку для задания значения поля. Дополнительные сведения см. в разделе «свойство пустые строки» справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Задает последовательность порядка сортировки в тексте для сравнения строк или сортировки. Дополнительные сведения см. в разделе «Настройка параметров реестра Windows для доступа к данным» справки DAO. Список возможных возвращаемых значений см. в `m_lCollatingOrder` элементе структуры [кдаодатабасеинфо](../../mfc/reference/cdaodatabaseinfo-structure.md) . Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Значение, которое в отношении указывает имя объекта поля DAO во внешней таблице, соответствующей полю в первичной таблице. Дополнительные сведения см. в разделе "свойство Фореигннаме" справки DAO.

*m_strSourceField*<br/>
Указывает имя поля, которое является исходным источником данных для объекта поля DAO, содержащегося в объекте tabledef, Recordset или QueryDef. Это свойство указывает имя исходного поля, связанного с объектом поля. Например, это свойство можно использовать для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Дополнительные сведения см. в подразделе «Саурцефиелд, свойства SourceTable» справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Указывает имя таблицы, которая является исходным источником данных для объекта поля DAO, содержащегося в объекте tabledef, Recordset или QueryDef. Это свойство указывает исходное имя таблицы, связанное с объектом поля. Например, это свойство можно использовать для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Дополнительные сведения см. в подразделе «Саурцефиелд, свойства SourceTable» справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Значение, которое проверяет данные в поле при изменении или добавлении в таблицу. Дополнительные сведения см. в разделе "свойство ValidationRule" справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

Дополнительные сведения о tabledef см. в разделе `m_strValidationRule` элемента структуры [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) .

*m_strValidationText*<br/>
Значение, указывающее текст сообщения, которое отображается в приложении, если значение объекта поля DAO не удовлетворяет правилу проверки, заданному свойством ValidationRule. Дополнительные сведения см. в разделе "свойство Валидатионтекст" справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
Значение по умолчанию для объекта поля DAO. При создании новой записи значение свойства DefaultValue автоматически указывается в качестве значения для поля. Дополнительные сведения см. в разделе "свойство DefaultValue" справки DAO. Это свойство можно задать для tabledef с помощью [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Заметки

Ссылки на основные, вторичные и все приведенные выше сведения указывают, каким способом данные возвращаются функцией-членом `GetFieldInfo` в классах [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [кдаокуеридеф](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Объекты полей не представлены классом MFC. Вместо этого объекты DAO базовых объектов MFC следующих классов содержат коллекции объектов Field: [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)и [кдаокуеридеф](../../mfc/reference/cdaoquerydef-class.md). Эти классы предоставляют функции-члены для доступа к некоторым отдельным элементам сведений о полях или к ним можно получить доступ одновременно с помощью объекта `CDaoFieldInfo`, вызвав функцию-член `GetFieldInfo` содержащего объекта.

Помимо использования для проверки свойств объекта, можно также использовать `CDaoFieldInfo` для создания входного параметра для создания новых полей в объекте tabledef. Для этой задачи доступны более простые параметры, но если требуется более тонкий контроль, можно использовать версию [кдаотабледеф:: креатефиелд](../../mfc/reference/cdaotabledef-class.md#createfield) , которая принимает параметр `CDaoFieldInfo`.

Сведения, полученные функцией-членом `GetFieldInfo` (класса, содержащего поле), хранятся в структуре `CDaoFieldInfo`. Вызовите функцию-член `GetFieldInfo` содержащего его объекта, в коллекции полей которого хранится объект Field. `CDaoFieldInfo` также определяет функцию-член `Dump` в отладочных сборках. Для дампа содержимого объекта `CDaoFieldInfo` можно использовать `Dump`.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset:: Жетфиелдинфо](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[Кдаокуеридеф:: Жетфиелдинфо](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
