---
title: Класс CDaoTableDef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbc191baf452a4e695eee2eed00a8f679285dee1
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952485"
---
# <a name="cdaotabledef-class"></a>Класс CDaoTableDef
Представляет хранимое определение базовой или подключенной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Создает объект `CDaoTableDef`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|Добавляет новую таблицу в базу данных.|  
|[CDaoTableDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если таблицы могут быть обновлены (можно изменить определение поля или свойства таблицы).|  
|[CDaoTableDef::Close](#close)|Закрывает открытые tabledef.|  
|[CDaoTableDef::Create](#create)|Создает таблицу, в которой можно добавить базу данных при помощи [Append](#append).|  
|[CDaoTableDef::CreateField](#createfield)|Вызывается, чтобы создать поле для таблицы.|  
|[CDaoTableDef::CreateIndex](#createindex)|Вызывается, чтобы создать индекс для таблицы.|  
|[CDaoTableDef::DeleteField](#deletefield)|Вызывается, чтобы удалить поле из таблицы.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|Вызывается для удаления индекса из таблицы.|  
|[CDaoTableDef::GetAttributes](#getattributes)|Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|  
|[CDaoTableDef::GetConnect](#getconnect)|Возвращает значение, предоставляющее сведения об источнике таблицы.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Возвращает дату и время в базовой таблице базовый `CDaoTableDef` был создан объект.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенные в структуру базовой таблицы.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее количество полей в таблице.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Возвращает определенные виды информации о поля в таблице.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|Возвращает число индексов для таблицы.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Возвращает определенные виды информации о индексов для таблицы.|  
|[CDaoTableDef::GetName](#getname)|Возвращает имя пользовательской таблицы.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Возвращает число записей в таблице.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Возвращает значение, указывающее имя таблицы, вложенные в базы данных-источника.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Возвращает значение, которое проверяет данные в поле, изменить или добавить в таблицу.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Возвращает значение, указывающее текст сообщения, которое отображает приложения, если значение поля объекта не соответствует указанное правило проверки.|  
|[CDaoTableDef::IsOpen](#isopen)|Возвращает ненулевое значение, если таблица является откройте.|  
|[CDaoTableDef::Open](#open)|Открывает существующий tabledef хранится в базе данных, TableDef элемента коллекции.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|Обновляет сведения о соединении для подключенной таблицы.|  
|[CDaoTableDef::SetAttributes](#setattributes)|Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|  
|[CDaoTableDef::SetConnect](#setconnect)|Задает значение, предоставляющее сведения об источнике таблицы.|  
|[CDaoTableDef::SetName](#setname)|Задает имя таблицы.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Задает значение, указывающее имя подключенной таблицы базы данных-источника.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Задает значение, которое проверяет данные в поле, изменить или добавить в таблицу.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Задает значение, указывающее текст сообщения, которое отображает приложения, если значение поля объекта не соответствует указанное правило проверки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Указатель на интерфейс DAO основного объекта tabledef.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Базы данных-источника для этой таблицы.|  
  
## <a name="remarks"></a>Примечания  
 Каждый объект базы данных DAO поддерживает коллекцию, вызывается TableDefs, который содержит всех сохраненных объектов DAO tabledef.  
  
 Управлять определение таблицы с помощью `CDaoTableDef` объекта. Например, с их помощью можно выполнять следующее.  
  
-   Исследуйте структуру полей и индекс любой локальный, вложенные или внешние таблицы в базе данных.  
  
-   Вызовите `SetConnect` и `SetSourceTableName` функции-члены для вложенных таблиц и использование `RefreshLink` функции-члена для обновления подключений к вложенные таблицы.  
  
-   Вызовите `CanUpdate` функции-члена для определения, если можно изменить определения полей в таблице.  
  
-   Получить или задать условия проверки с использованием `GetValidationRule` и `SetValidationRule`и `GetValidationText` и `SetValidationText` функции-члены.  
  
-   Используйте `Open` функции-члена для создания таблицы, общий или статического типа `CDaoRecordset` объекта.  
  
    > [!NOTE]
    >  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. классы DAO обычно обеспечивают превосходную возможности, так как они характерны для базы данных Microsoft Jet.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Чтобы использовать tabledef объекты для работы с существующей таблицы или для создания новой таблицы  
  
1.  Во всех случаях сначала создать `CDaoTableDef` объекта, предоставляющего указатель [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта, которому принадлежит таблица.  
  
2.  Затем выполните следующую команду, в зависимости от того, какие действия следует:  
  
    -   Чтобы использовать существующий сохраненный таблицы, вызывающие этот объект tabledef [откройте](#open) функция-член, указав имя таблицы, сохраненный.  
  
    -   Чтобы создать новую таблицу, вызов объекта tabledef [создать](#create) функция-член, указав имя таблицы. Вызовите [CreateField](#createfield) и [CreateIndex](#createindex) Добавление полей и индексов в таблице.  
  
    -   Вызовите [Append](#append) для сохранения таблицы путем добавления его к TableDefs-коллекция базы данных. `Create` Помещает tabledef в открытом состоянии, поэтому после вызова `Create` не вызывается `Open`.  
  
        > [!TIP]
        >  Для их создания и сохранения их в базу данных с помощью Microsoft Access является самым простым способом создания сохраненных таблиц. Затем можно открыть и использовать их в коде MFC.  
  
 Чтобы использовать объект tabledef открывается или создается, создать и открыть `CDaoRecordset` объекта, указав имя tabledef с **dbOpenTable** значение в `nOpenType` параметра.  
  
 Использование для создания объекта tabledef `CDaoRecordset` объекта вы обычно создайте или откройте tabledef, как описано выше, а затем создать объект набора записей указателю на объект tabledef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Tabledef, передаваемые должен быть в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 После завершения работы с объектом tabledef, вызовите его [закрыть](../../mfc/reference/cdaorecordset-class.md#close) члена функции; затем удалите объект tabledef.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="append"></a>  CDaoTableDef::Append  
 Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта tabledef сохранить tabledef в базе данных.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Примечания  
 Функция добавляет объект в коллекцию TableDefs базы данных. Tabledef можно использовать в качестве временного объекта при его определении не добавляя его, но если вы хотите сохранить и использовать его, необходимо вызвать `Append`.  
  
> [!NOTE]
>  При попытке добавить неименованные tabledef (содержащий null или пустую строку), MFC вызывает исключение.  
  
 Дополнительные сведения см. в разделе «Добавление Method» в справке DAO.  
  
##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate  
 Вызовите эту функцию-член для определения ли определение базовой таблицы `CDaoTableDef` объект может быть изменен.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в структуре таблицы (схема) могут быть изменены (Добавление или удаление полей и индексов), иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию вновь созданную таблицу базового `CDaoTableDef` объект может быть изменен и присоединенная таблица базовая `CDaoTableDef` объект не может быть обновлен. Объект `CDaoTableDef` объект может быть обновлен, даже если результирующий набор записей, не является обновляемым.  
  
 Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef  
 Создает **CDaoTableDef** объекта.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Параметры  
 *pDatabase*  
 Указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, необходимо вызвать [создать](#create) или [откройте](#open) функции-члена. После завершения работы с объектом, необходимо вызвать его [закрыть](#close) члена функции и уничтожать `CDaoTableDef` объекта.  
  
##  <a name="close"></a>  CDaoTableDef::Close  
 Вызовите эту функцию-член закрыть и освободить объект tabledef.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Обычно после вызова `Close`, удалении tabledef объекта, если он был выделен с помощью **новый**.  
  
 Можно вызвать [откройте](#open) повторно после вызова `Close`. Это позволяет повторно использовать этот объект tabledef.  
  
 Дополнительные сведения см. в разделе «Метод Close» в справке DAO.  
  
##  <a name="create"></a>  CDaoTableDef::Create  
 Вызовите эту функцию-член для создания новой таблицы сохраненный.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель на строку, содержащую имя таблицы.  
  
 *lAttributes*  
 Значение, соответствующее характеристикам таблиц, представленный объектом tabledef. Побитовое или можно использовать для объединения любой из следующих констант:  
  
|Константа|Описание:|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что вложенные таблицы, открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что скрытые таблицы, предоставляемые базы данных Microsoft Jet.|  
  
 *lpszSrcTable*  
 Указатель на строку, содержащую имя исходной таблицы. По умолчанию это значение инициализируется как **NULL**.  
  
 *lpszConnect*  
 Указатель на строку, содержащую строку подключения по умолчанию. По умолчанию это значение инициализируется как **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Как только вы присвоили tabledef, можно вызвать [Append](#append) для сохранения в базе данных TableDefs-коллекция tabledef. После вызова метода `Append`tabledef находится в открытом состоянии и его можно использовать для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.  
  
 Дополнительные сведения см. в разделе «Метод CreateTableDef» в справке DAO.  
  
##  <a name="createfield"></a>  CDaoTableDef::CreateField  
 Вызовите эту функцию-член для добавления поля к таблице.  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель на строковое выражение, указывающее имя этого поля.  
  
 *nType*  
 Значение, указывающее тип данных поля. Параметр может принимать одно из следующих значений:  
  
|Тип|Размер (в байтах)|Описание:|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 байт|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|8|Валюта ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|float|  
|**dbDouble**|8|double|  
|**dbDate**|8|Даты и времени ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Текст ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Длинные двоичные (OLE-объекта), [CLongBinary](../../mfc/reference/clongbinary-class.md) или [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|MEMO ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 *lSize*  
 Значение, указывающее максимальный размер в байтах, поля, которое содержит текст, или фиксированного размера поля, которое содержит текстовых или числовых значений. *LSize* параметр учитывается для всех, кроме текстовых полей.  
  
 *lAttributes*  
 Значение, соответствующее характеристики поля, которые могут объединяться с помощью побитового или.  
  
|Константа|Описание:|  
|--------------|-----------------|  
|**dbFixedField**|Поле фиксированный размер (по умолчанию для числовых полей).|  
|**dbVariableField**|Размер поля является переменной (только текстовые поля).|  
|**dbAutoIncrField**|Значение поля для новых записей автоматически увеличивается до уникальное целое число типа long, не может быть изменено. Поддерживается только для таблиц базы данных Microsoft Jet.|  
|**dbUpdatableField**|Можно изменить значение поля.|  
|**dbDescending**|Поле сортируется по убыванию (Z - A, или 100-0) порядке (применяется только к объекту поле в коллекции полей индекса объекта). При отсутствии этой константы, поле сортируется по возрастанию (A - Z или 0 - 100) порядке (по умолчанию).|  
  
 *FieldInfo*  
 Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Объект **DAOField** (OLE) объект создается и добавляется в коллекцию полей `DAOTableDef` объектов (OLE). Помимо использования для проверки свойств объекта, можно также использовать `CDaoFieldInfo` для построения для создания новых полей в tabledef входного параметра. Первая версия `CreateField` проще в использовании, но если требуется более точное управление можно использовать второй версии `CreateField`, который принимает `CDaoFieldInfo` параметра.  
  
 Если вы используете версию `CreateField` , который принимает `CDaoFieldInfo` параметр, необходимо тщательно задать каждого из элементов `CDaoFieldInfo` структуры:  
  
- **m_strName**  
  
- **m_nType**  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 Оставшиеся члены `CDaoFieldInfo` должно быть присвоено **0**, **FALSE**, или пустая строка, в зависимости от элемента, или `CDaoException` может возникнуть.  
  
 Дополнительные сведения см. в разделе «Метод CreateField» в справке DAO.  
  
##  <a name="createindex"></a>  CDaoTableDef::CreateIndex  
 Вызывайте эту функцию, чтобы добавить индекс для таблицы.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>Параметры  
 *indexinfo*  
 Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Индексы указывают порядок записей из таблицы базы данных и принимаются ли повторяющиеся записи. Индексы также обеспечивают эффективный доступ к данным.  
  
 Необходимо создать индексы для таблиц, но в большие таблицы неиндексированную, доступ к конкретной записи или создание набора записей может занять много времени. Создание слишком много индексов замедляется с другой стороны, обновление, добавить и удалить операции, так как все индексы автоматически обновляются. Учитывайте эти факторы, как решить, какие индексы для создания.  
  
 Следующие элементы `CDaoIndexInfo` структуры необходимо задать:  
  
- **m_strName** необходимо указать имя.  
  
- **m_pFieldInfos** должен указывать на массив `CDaoIndexFieldInfo` структуры.  
  
- **m_nFields** необходимо указать количество полей в массиве `CDaoFieldInfo` структуры.  
  
 Оставшиеся члены игнорируется, если устанавливается значение **FALSE**. Кроме того **m_lDistinctCount** игнорируется во время создания индекса.  
  
##  <a name="deletefield"></a>  CDaoTableDef::DeleteField  
 Вызовите эту функцию-член для удаления поля и сделать ее недоступной.  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель на строковое выражение, которое является именем существующего поля.  
  
 *nIndex*  
 Индекс поля в коллекции (с нуля) полей таблицы, для поиска по индексу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член можно использовать на новый объект, не добавляются в базу данных или при [CanUpdate](#canupdate) возвращает ненулевое значение.  
  
 Дополнительные сведения см. в разделе «Удаление Method» в справке DAO.  
  
##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex  
 Вызовите эту функцию-член для удаления индекса в базовой таблице.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель на строковое выражение, которое является именем существующего индекса.  
  
 *nIndex*  
 Индекс в массиве объект индекса в коллекции (с нуля) TableDefs базы данных, для поиска по индексу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член можно использовать на новый объект, который еще не были добавлены в базу данных или при [CanUpdate](#canupdate) возвращает ненулевое значение.  
  
 Дополнительные сведения см. в разделе «Удаление Method» в справке DAO.  
  
##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes  
 Для `CDaoTableDef` объекта, возвращаемое значение, указывающее характеристики таблицы, представленной `CDaoTableDef` объекта и может быть суммой значений этих констант:  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
  
|Константа|Описание:|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что вложенные таблицы, открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что скрытые таблицы, предоставляемые базы данных Microsoft Jet.|  
|**dbAttachedTable**|Указывает, что вложенные таблицы из базы данных не ODBC, такие как базы данных Paradox.|  
|**dbAttachedODBC**|Указывает, что вложенные таблицы из базы данных ODBC, например Microsoft SQL Server.|  
  
 Системная таблица является таблицей, созданные базы данных Microsoft Jet для хранения различных внутренних данных.  
  
 Скрытые является таблица, созданную для временной базы данных Microsoft Jet.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getconnect"></a>  CDaoTableDef::GetConnect  
 Вызовите эту функцию-член для получения строки соединения для источника данных.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий путь и тип базы данных для таблицы.  
  
### <a name="remarks"></a>Примечания  
 Для `CDaoTableDef` , представляющий подключенной таблицы `CString` объекта состоит из одного или двух частей (описатель типа базы данных и путь к базе данных).  
  
 Путь, как показано в следующей таблице является полный путь к каталогу, содержащему файлы базы данных и должен предшествовать идентификатор «базы данных =». В некоторых случаях (как базы данных Microsoft Jet и Microsoft Excel) определенные filename включается в аргумент путь базы данных.  
  
 В таблице в [CDaoTableDef::SetConnect](#setconnect) показывает типы возможно, база данных и их соответствующие спецификаторы базы данных и пути:  
  
 Для базовых таблиц базы данных Microsoft Jet, описатель является пустая строка (»»).  
  
 Если пароль требуется, но не указано, драйвер ODBC имя входа диалоговое окно выводится при первом доступ к таблице и снова при закрытии и повторном открытии соединения. Если вложенные таблицы **dbAttachSavePWD** атрибут, в строке имени входа, не появляются при повторном открытии таблицы.  
  
 Дополнительные сведения см. в разделе «Свойства подключения», справки DAO.  
  
##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated  
 Эта функция вызывается для определения даты и времени базовой таблицы `CDaoTableDef` был создан объект.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее дату и время создания базовой таблицы `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, на котором была создана или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры напрямую из файлового сервера, чтобы избежать несоответствия; то есть, все клиенты должны использовать источник времени «standard» — возможно, из одного сервера.  
  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated  
 Эта функция вызывается для определения даты и времени базовой таблицы `CDaoTableDef` последнего обновления объекта.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее дату и время в базовой таблице `CDaoTableDef` последнего обновления объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, на котором была создана или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры напрямую из файлового сервера, чтобы избежать несоответствия; то есть, все клиенты должны использовать источник времени «standard» — возможно, из одного сервера.  
  
 Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.  
  
##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount  
 Вызовите эту функцию-член для извлечения нескольких полей, определенных в таблице.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей в таблице.  
  
### <a name="remarks"></a>Примечания  
 Если его значение равно 0, нет ни одного объекта в коллекции.  
  
 Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.  
  
##  <a name="getfieldinfo"></a>  CDaoTableDef::GetFieldInfo  
 Вызовите эту функцию-член для получения различного рода сведения о поле, определенное в tabledef.  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Индекс поля объекта в коллекции (с нуля) полей таблицы, для поиска по индексу.  
  
 *FieldInfo*  
 Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.  
  
 *dwInfoOptions*  
 Параметры, определяющие, какие поля для извлечения. Ниже перечислены доступные параметры и как они вызвать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, тип, размер, атрибуты. Используйте этот параметр для максимальную производительность.  
  
- `AFX_DAO_SECONDARY_INFO` Первичные данные, а также: порядковый номер позиции, необходимые, разрешить нулевой длины, порядок сортировки, внешнего имени, исходное поле исходной таблицы  
  
- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: правила проверки, текст для проверки, значение по умолчанию  
  
 *lpszName*  
 Указатель на имя объекта поля для поиска по имени. Имя является строкой с длиной до 64 символов, однозначно определяющий поля.  
  
### <a name="remarks"></a>Примечания  
 Одну версию функции позволяет найти поле с индексом. Другая версия позволяет искать поле по имени.  
  
 Описание сведений, возвращаемых см. в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведения на одном уровне, вы получаете сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount  
 Вызовите эту функцию-член для получения числа индексов для таблицы.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число индексов для таблицы.  
  
### <a name="remarks"></a>Примечания  
 Если его значение равно 0, существует ни одного индекса в коллекции.  
  
 Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.  
  
##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo  
 Вызовите эту функцию-член для получения различные виды информации о индекс, определенный в tabledef.  
  
```  
void GetIndexInfo(
    int nIndex,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetIndexInfo(
    LPCTSTR lpszName,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Параметры  
 *nIndex*  
 Числовой индекс, индекс объекта в коллекции (с нуля) индексы таблицы, для поиска по его позиции в коллекции.  
  
 *indexinfo*  
 Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.  
  
 *dwInfoOptions*  
 Параметры, указывающие, какие сведения об индексе для извлечения. Ниже перечислены доступные параметры и как они вызвать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO` Сведения о поле, имя поля. Используйте этот параметр для максимальную производительность.  
  
- `AFX_DAO_SECONDARY_INFO` Первичные данные, а также: основной, Unique, кластеризованный, пропускать пустые значения, необходимые, внешний  
  
- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: числа различных объектов  
  
 *lpszName*  
 Указатель на имя объекта индекса для поиска по имени.  
  
### <a name="remarks"></a>Примечания  
 Одну версию функции позволяет индекса по его позиции в коллекции. Другая версия позволяет найти индекс с именем.  
  
 Описание сведений, возвращаемых см. в разделе [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведения на одном уровне, вы получаете сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getname"></a>  CDaoTableDef::GetName  
 Вызовите эту функцию-член для получения определяемое пользователем имя базовой таблицы.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемое пользователем имя таблицы.  
  
### <a name="remarks"></a>Примечания  
 Это имя начинается с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.  
  
 Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount  
 Вызовите эту функцию-член, чтобы узнать, сколько записей в `CDaoTableDef` объекта.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число записей, получить доступ к объекту tabledef.  
  
### <a name="remarks"></a>Примечания  
 Вызов `GetRecordCount` для типа таблицы `CDaoTableDef` объекта отражает приблизительное количество записей в таблице и немедленно влияет как добавления и удаления записей в таблице. Откат транзакции будут отображаться как часть количество записей до вызова [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Объект `CDaoTableDef` объект без записей имеет свойство счетчик записей, равным 0. При работе с таблицами или баз данных ODBC, `GetRecordCount` всегда возвращает значение -1.  
  
 Дополнительные сведения см. в разделе «RecordCount свойство» в справке DAO.  
  
##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName  
 Вызовите эту функцию-член для извлечения имени подключенной таблицы в базе данных источника.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объекта, указывающее имя источника, связанного с таблицей или пустая строка, если таблица данных в собственном формате.  
  
### <a name="remarks"></a>Примечания  
 Присоединенная таблица является таблицей в другой базе данных, связанных с базой данных Microsoft Jet. Данные для вложенных таблиц остается внешней базы данных, где ими можно управлять другими приложениями.  
  
 Дополнительные сведения см. в разделе «Свойство SourceTableName» в справке DAO.  
  
##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule  
 Вызовите эту функцию-член для извлечения для tabledef правила проверки.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, который проверяет данные в поле, изменить или добавить в таблицу.  
  
### <a name="remarks"></a>Примечания  
 Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef условиям предопределенном перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее значение [GetValidationText](#getvalidationtext) возникает исключение. Для `CDaoTableDef` объекта, это `CString` доступно только для чтения для чтения и записи для базовой таблицы и связанных с таблицей.  
  
 Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO.  
  
##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText  
 Эта функция вызывается для получения строки для отображения, когда пользователь вводит данные, которые не соответствуют правилу проверки.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, который задает текст, отображаемый, если пользователь вводит данные, которые не соответствуют правилу проверки.  
  
### <a name="remarks"></a>Примечания  
 Для `CDaoTableDef` объекта, это `CString` доступно только для чтения для чтения и записи для базовой таблицы и связанных с таблицей.  
  
 Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
##  <a name="isopen"></a>  CDaoTableDef::IsOpen  
 Вызовите эту функцию-член для определения ли `CDaoTableDef` объект открыт в данный момент.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CDaoTableDef` объект открыт; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase  
 Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта для этой таблицы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef  
 Содержит указатель на интерфейс OLE для базового объекта DAO tabledef `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот указатель, если требуется прямой доступ к интерфейсу DAO.  
  
##  <a name="open"></a>  CDaoTableDef::Open  
 Вызов этой функции-члена для открытия tabledef ранее сохраненные в базе данных, TableDef элемента коллекции.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель строка, указывающая имя таблицы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink  
 Вызовите эту функцию-член для обновления сведений о соединении для подключенной таблицы.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>Примечания  
 Изменить сведения о соединении для подключенной таблицы, вызвав метод [SetConnect](#setconnect) соответствующего `CDaoTableDef` объекта, а затем с помощью `RefreshLink` функции-члена для обновления данных. При вызове `RefreshLink`, не изменяются свойства вложенные таблицы.  
  
 Чтобы принудительно измененные сведения о подключении вступили в силу, все открытые [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекты на основании этого tabledef должны быть закрыты.  
  
 Дополнительные сведения см. в разделе «Метод RefreshLink» в справке DAO.  
  
##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes  
 Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>Параметры  
 *lAttributes*  
 Характеристики таблицы, представленной `CDaoTableDef` объекта и может быть суммой значений этих констант:  
  
|Константа|Описание:|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что вложенные таблицы, открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что скрытые таблицы, предоставляемые базы данных Microsoft Jet.|  
  
### <a name="remarks"></a>Примечания  
 При установке нескольких атрибутов, их можно объединить путем суммирования соответствующий оператор побитового или с помощью константы. Установка **dbAttachExclusive** для неприсоединенных таблицы вызвала исключение. Объединение следующие значения, также создают исключение:  
  
- **dbAttachExclusive &#124; dbAttachedODBC**  
  
- **dbAttachSavePWD &#124; dbAttachedTable**  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="setconnect"></a>  CDaoTableDef::SetConnect  
 Для `CDaoTableDef` , представляющий подключенной таблицы, что строковый объект состоит из одной или двух частей (описатель типа базы данных и путь к базе данных).  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszConnect*  
 Указатель на строковое выражение, которое указывает дополнительные параметры для передачи ODBC или устанавливаемые драйверы ISAM.  
  
### <a name="remarks"></a>Примечания  
 Путь, как показано в следующей таблице является полный путь к каталогу, содержащему файлы базы данных и должен предшествовать идентификатор «базы данных =». В некоторых случаях (как базы данных Microsoft Jet и Microsoft Excel) определенные filename включается в аргумент путь базы данных.  
  
> [!NOTE]
>  Не включайте вокруг знака равенства в инструкции путь в формате «базы данных = диск:\\\path». Это приведет к формированию исключения и сбои подключения.  
  
 Ниже приведены типы возможно, база данных и их соответствующие спецификаторы базы данных и пути:  
  
|Тип базы данных|Описатель|Путь|  
|-------------------|---------------|----------|  
|Базы данных с помощью базы данных Jet|"[ `database`];"|« `drive`:\\\ *путь*\\\ *filename*. MDB»|  
|dBASE III|«dBASE III;»|« `drive`:\\\ *путь*»|  
|dBASE IV|«dBASE IV;»|« `drive`:\\\ *путь*»|  
|dBASE 5|«dBASE 5.0;»|« `drive`:\\\ *путь*»|  
|Paradox 3.x|«Paradox 3.x;»|« `drive`:\\\ *путь*»|  
|Paradox 4.x|«Paradox 4.x;»|« `drive`:\\\ *путь*»|  
|Paradox 5.x|«Paradox 5.x;»|« `drive`:\\\ *путь*»|  
|Excel 3.0|«Excel 3.0;»|« `drive`:\\\ *путь*\\\ *filename*. XLS»|  
|Excel 4.0|«Excel 4.0;»|« `drive`:\\\ *путь*\\\ *filename*. XLS»|  
|Excel 5.0 или Excel 95|«Excel 5.0»;|« `drive`:\\\ *путь*\\\ *filename*. XLS»|  
|Excel 97|«Excel 8.0;»|« `drive`:\\\ *путь*\ *filename*. XLS»|  
|Импорт HTML|HTML «Импорт»;|« `drive`:\\\ *путь*\ *filename*»|  
|Экспорт HTML|«Экспорт HTML»;|« `drive`:\\\ *путь*»|  
|Text|«Текст»;|«диск:\\\path»|  
|ODBC|«ODBC; Базы данных = `database`; UID = *пользователя*; PWD = *пароль*; DSN = *datasourcename;* LOGINTIMEOUT = *секунды;*» (Это может быть полной строки соединения для всех серверов, это лишь пример. Очень важно без пробелов между параметров.)|Нет|  
|Exchange|«Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &AMP;#124; 1};]<br /><br /> [Профиль = *профиль*;]<br /><br /> [PWD = *пароль*;]<br /><br /> [БАЗЫ ДАННЫХ = `database`;]»|*«диск*:\\\ *путь*\\\ *filename*. MDB»|  
  
> [!NOTE]
>  Начиная с DAO 3.5 Btrieve больше не поддерживается.  
  
 Необходимо использовать две обратные косые черты (\\\\) в строке подключения. Если вы изменили свойства существующего соединения с помощью `SetConnect`, затем должен вызывать [RefreshLink](#refreshlink). При инициализации свойства соединения, с помощью `SetConnect`, необходимо, чтобы вызов не `RefreshLink`, но сначала нужно выбрать для этого, добавить tabledef.  
  
 Если пароль требуется, но не указано, драйвер ODBC имя входа диалоговое окно выводится при первом доступ к таблице и снова при закрытии и повторном открытии соединения.  
  
 Можно задать строку подключения для `CDaoTableDef` , указав аргумент источника для `Create` функции-члена. Можно проверить параметр, чтобы определить тип, путь, идентификатор пользователя, пароль или источник данных ODBC базы данных. Дополнительные сведения см. в документации для заданного драйвера.  
  
 Дополнительные сведения см. в разделе «Свойства подключения», справки DAO.  
  
##  <a name="setname"></a>  CDaoTableDef::SetName  
 Вызовите эту функцию-член для задания определяемое пользователем имя для таблицы.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszName*  
 Указатель на строковое выражение, указывающее имя таблицы.  
  
### <a name="remarks"></a>Примечания  
 Имя должно начинаться с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.  
  
 Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName  
 Вызовите эту функцию-член для указания имени вложенные таблицы или имя базовой таблицы, на котором `CDaoTableDef` зависимости объекта, которое существовало в исходном источнике данных.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSrcTableName*  
 Указатель на строковое выражение, указывающее имя таблицы внешней базы данных. Для базовой таблицы, параметр — пустая строка (»»).  
  
### <a name="remarks"></a>Примечания  
 Затем нужно вызвать [RefreshLink](#refreshlink). Это свойство является пустым для базовой таблицы и чтение и запись для подключенной таблицы, либо объект не добавляется в коллекцию.  
  
 Дополнительные сведения см. в разделе «Свойство SourceTableName» в справке DAO.  
  
##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule  
 Вызовите эту функцию-член правила проверки для tabledef.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszValidationRule*  
 Указатель на строковое выражение, которое проверяет операции.  
  
### <a name="remarks"></a>Примечания  
 Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef условиям предопределенном перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее текст [GetValidationText](#getvalidationtext) отображается.  
  
 Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Выражение не может ссылаться на определяемые пользователем функции, статистические функции, статистические функции SQL или запросы. Правила проверки для `CDaoTableDef` объект может ссылаться на несколько полей в этом объекте.  
  
 Например, для поля с именем *hire_date* и *termination_date*, возможно, правила проверки:  
  
 [!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 Дополнительные сведения см. в разделе «ValidationRule свойство» в справке DAO.  
  
##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText  
 Вызовите эту функцию-член для задания текста исключения правила проверки для `CDaoTableDef` объект с базовой таблицы поддерживаемые базы данных Microsoft Jet.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszValidationText*  
 Недопустимый указатель на строковое выражение, указывающее текст, отображаемый, если введенные данные.  
  
### <a name="remarks"></a>Примечания  
 Невозможно задать текст проверки вложенные таблицы.  
  
 Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)   
 [Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)
