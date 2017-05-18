---
title: "Структура CDaoFieldInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
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
ms.openlocfilehash: 15db0c56480dfefb9fc8806c08596e37c7d38eb2
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
 Однозначно имена полей объекта. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 `m_nType`  
 Значение, указывающее тип данных поля. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO. Значение этого свойства может быть одно из следующих значений:  
  
- **dbBoolean** Да-Нет, то же, что **TRUE**/**FALSE**  
  
- **dbByte** байтов  
  
- **dbInteger** короткие  
  
- **dbLong** Long  
  
- **dbCurrency** валюты, класс MFC см. в разделе [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle** одного  
  
- **dbDouble** Double  
  
- **dbDate** даты и времени; см. класс MFC [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText** текст; класс MFC см. в разделе [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary** Long Binary (объекта OLE); вы можете использовать класс MFC [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса `CLongBinary` как `CByteArray` является более широкие возможности и проще в использовании.  
  
- **dbMemo** ноты; класс MFC см.`CString`  
  
- **dbGUID** глобально уникальный идентификатор или универсальный уникальный идентификатор, используемый для вызовов удаленных процедур. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
> [!NOTE]
>  Не используйте строковых данных для двоичных данных. В результате данные для передачи через уровень преобразования Юникода или ANSI, возникающие при переводе повышенную нагрузку и возможно непредвиденных.  
  
 *m_lSize*  
 Значение, указывающее максимальный размер в байтах, поля объекта DAO, который содержит текст или фиксированного размера объекта поля, содержащего текстовых или числовых значений. Дополнительные сведения см. в разделе «Свойства Size» в справке DAO. Размер может принимать одно из следующих значений:  
  
|Тип|Размер (байт)|Описание|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 байт|Да/Нет (то же, как True или False)|  
|**dbByte**|1|Байт|  
|**dbInteger**|2|Целое число|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Валюта ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Даты и времени ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Текст ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Long Binary (OLE-объекта; [CByteArray](../../mfc/reference/cbytearray-class.md); используйте вместо `CLongBinary`)|  
|**dbMemo**|0|MEMO ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Глобально уникальный идентификатор или универсальный уникальный идентификатор, используемый для вызовов удаленных процедур.|  
  
 `m_lAttributes`  
 Задает характеристики поле объект, содержащийся в tabledef, набор записей, querydef или объекта индекса. Возвращаемое значение может быть суммой эти константы, созданные с помощью C++ побитового или (**|**) оператор:  
  
- **dbFixedField** размер поля является фиксированным (по умолчанию для числовых полей).  
  
- **dbVariableField** размер поля является переменной (только текстовые поля).  
  
- **dbAutoIncrField** значение поля для добавления новых записей автоматически увеличивается уникальный длинное целое число, не может быть изменено. Поддерживается только для таблиц базы данных Microsoft Jet.  
  
- **dbUpdatableField** значение поля может быть изменено.  
  
- **dbDescending** поле сортируется по убыванию (Z - A или 100-0) порядке (применяется только к объекту поля в коллекцию полей индекса объекта, в MFC, сами объекты находятся в объектах tabledef индекса). При отсутствии этой константы, поле сортируется в порядке возрастания (A - Z или 0 - 100) порядке (по умолчанию).  
  
 При проверке значения этого свойства, можно использовать C++ побитовое- и оператор (**&**) для тестирования для определенного атрибута. При установке нескольких атрибутов, их можно объединить, объединяя соответствующие константы с побитового или (**|**) оператор. Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
 *m_nOrdinalPosition*  
 Значение, указывающее числовой порядок, в которой поля, представленного объект DAO поля для отображения относительно других полей. Можно задать это свойство с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Дополнительные сведения см. в разделе «OrdinalPosition свойство» в справке DAO.  
  
 `m_bRequired`  
 Указывает, требуется ли объект поля DAO непустое значение. Если это свойство имеет **TRUE**, поле не допускает значение Null. Если требуется задать **FALSE**, поле может содержать значения Null, а также значения, которые соответствуют условиям, указанным пустые строки и ValidationRule параметры свойств. Дополнительные сведения см. в разделе «Необходимые свойства» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Указывает, является ли пустая строка («») является допустимым значением объекта DAO поля с типом данных Text или Memo. Если это свойство имеет **TRUE**, пустая строка является допустимым значением. Это свойство можно задать **FALSE** чтобы убедиться, что значение поля нельзя использовать пустую строку. Дополнительные сведения см. в разделе «Свойство пустые строки» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Указывает последовательность сортировки в текст для сравнения строк или сортировки. Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO. Список возможных значений, возвращаемых см. в разделе **m_lCollatingOrder** членом [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) структуры. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Значение, в отношении, задает имя объекта поля DAO внешней таблицы, которая соответствует полю в таблице первичного. Дополнительные сведения см. в разделе «ForeignName свойство» в справке DAO.  
  
 *m_strSourceField*  
 Указывает имя поля, которое находится исходный источник данных для поля объекта DAO tabledef, записей или объекта querydef. Это свойство указывает исходное имя поля, связанного с объектом поля. Например можно использовать это свойство для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField таблица свойств» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Указывает имя таблицы, которая является исходный источник данных для поля объекта DAO tabledef, записей или объекта querydef. Это свойство указывает исходное имя таблицы, связанный с объектом поля. Например можно использовать это свойство для определения исходного источника данных в поле запроса, имя которого не связано с именем поля в базовой таблице. Дополнительные сведения см. в разделе «SourceField таблица свойств» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Значение, которое проверяет данные в поле, изменить или добавить в таблицу. Дополнительные сведения см. в разделе «Свойства ValidationRule» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Дополнительные сведения о tabledefs см. в разделе **m_strValidationRule** членом [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) структуры.  
  
 `m_strValidationText`  
 Значение, указывающее текст сообщения, приложения, если значение поля объекта DAO не удовлетворяет правила проверки, указанном параметром свойства ValidationRule. Дополнительные сведения см. в разделе «Свертыванию» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 Значение по умолчанию объекта поля DAO. При создании новой записи значение свойства DefaultValue автоматически вводится как значение для поля. Дополнительные сведения см. в разделе «Свойство DefaultValue» в справке DAO. Можно задать это свойство для tabledef с [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Примечания  
 Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по `GetFieldInfo` функции-члена в классах [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Класс MFC не представлены объектов полей. Вместо этого объекты следующие классы MFC DAO объектов содержат коллекции объектов поля: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), и [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Эти классы предоставить функции-члены для доступа к некоторых отдельных элементов данных полей, или использовать их все одновременно с `CDaoFieldInfo` путем вызова метода `GetFieldInfo` функцию-член вмещающего объекта.  
  
 Помимо использования для проверки свойств объекта, можно использовать `CDaoFieldInfo` для создания входной параметр для создания нового поля в tabledef. Проще доступны для этой задачи, но если требуется более тонкое управление, можно использовать версию [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , которая принимает `CDaoFieldInfo` параметр.  
  
 Данные, полученные по `GetFieldInfo` функцию-член (класс, который содержит поле) хранится в `CDaoFieldInfo` структуру. Вызов `GetFieldInfo` функция-член которого коллекции полей поля сохраняется объект, содержащего объект. `CDaoFieldInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)


