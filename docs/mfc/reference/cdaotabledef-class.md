---
title: "Класс CDaoTableDef | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- database classes [C++], DAO
- tabledefs [C++]
- CDaoTableDef class
- database tables [C++], attached table definition
- database tables [C++], base table definition
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8bfd0ef3c63c243cabb0a4f841ba278fbeed4ae8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledef-class"></a>Класс CDaoTableDef
Представляет хранимое определение базовой или подключенной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Создает **CDaoTableDef** объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|Добавляет новую таблицу в базу данных.|  
|[CDaoTableDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если таблицы могут быть обновлены (можно изменить определение полей или свойств таблицы).|  
|[CDaoTableDef::Close](#close)|Закрывает Открытие tabledef.|  
|[CDaoTableDef::Create](#create)|Создает таблицу, который может быть добавлен в базу данных с помощью [Append](#append).|  
|[CDaoTableDef::CreateField](#createfield)|Вызывается для создания поля для таблицы.|  
|[CDaoTableDef::CreateIndex](#createindex)|Вызывается для создания индекса для таблицы.|  
|[CDaoTableDef::DeleteField](#deletefield)|Вызывается, чтобы удалить поле из таблицы.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|Вызывается для удаления индекса из таблицы.|  
|[CDaoTableDef::GetAttributes](#getattributes)|Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|  
|[CDaoTableDef::GetConnect](#getconnect)|Возвращает значение, предоставляющее сведения об исходной таблицы.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Возвращает дату и время базовой таблицы базового `CDaoTableDef` был создан объект.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенные в структуру базовой таблицы.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее число полей в таблице.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Возвращает определенные виды информации о поля в таблице.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|Возвращает число индексов для таблицы.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Возвращает определенные виды информации о индексов для таблицы.|  
|[CDaoTableDef::GetName](#getname)|Возвращает имя пользовательской таблицы.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Возвращает число записей в таблице.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Возвращает значение, указывающее имя таблицы, вложенные в исходной базе данных.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Возвращает значение, которое проверяет данные в поле, изменить или добавить в таблицу.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Возвращает значение, указывающее текст сообщения, которое будет отображаться в приложении, если значение поля объекта не удовлетворяет указанное правило проверки.|  
|[CDaoTableDef::IsOpen](#isopen)|Возвращает ненулевое значение, если таблица является откройте.|  
|[CDaoTableDef::Open](#open)|Открывает существующий tabledef хранятся в базе данных, TableDef элемента коллекции.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|Обновляет сведения о соединении для подключенной таблицы.|  
|[CDaoTableDef::SetAttributes](#setattributes)|Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|  
|[CDaoTableDef::SetConnect](#setconnect)|Задает значение, предоставляющее сведения об исходной таблицы.|  
|[CDaoTableDef::SetName](#setname)|Задает имя таблицы.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Задает значение, указывающее имя связанного с таблицей базы данных-источника.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Задает значение, которое проверяет данные в поле, изменить или добавить в таблицу.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Задает значение, указывающее текст сообщения, которое будет отображаться в приложении, если значение поля объекта не удовлетворяет указанное правило проверки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Указатель на базовый объект tabledef интерфейс DAO.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Базы данных-источника для этой таблицы.|  
  
## <a name="remarks"></a>Примечания  
 Каждый объект базы данных DAO поддерживает коллекцию, вызывается TableDefs, который содержит все сохраненные объекты DAO tabledef.  
  
 Управлять определение таблицы с помощью `CDaoTableDef` объекта. Например, с их помощью можно выполнять следующее.  
  
-   Исследуйте структуру поля и индекс любой локальный, вложенные или внешние таблицы в базе данных.  
  
-   Вызов `SetConnect` и `SetSourceTableName` функции-члены для вложенных таблиц и использование `RefreshLink` функции-члена для обновления подключений к присоединенные таблицы.  
  
-   Вызов `CanUpdate` функции-члена для определения, если можно изменить определения полей в таблице.  
  
-   Получить или задать условия проверки данных с помощью `GetValidationRule` и `SetValidationRule`и `GetValidationText` и `SetValidationText` функции-члены.  
  
-   Используйте **откройте** функции-члена для создания таблицы, общий или статического типа `CDaoRecordset` объекта.  
  
    > [!NOTE]
    >  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему обращаться к источникам данных ODBC с помощью классов DAO. классы DAO обычно предлагают превосходит возможности, поскольку они являются специфическими для базы данных Microsoft Jet.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Использование объектов tabledef для работы с существующей таблице или создать новую таблицу  
  
1.  Во всех случаях сначала конструируется `CDaoTableDef` объекта, указав указатель [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта, к которому принадлежит таблица.  
  
2.  Затем выполните следующую команду, в зависимости от того, что нужно:  
  
    -   Чтобы использовать существующий сохраненный таблицы, вызов объекта tabledef [откройте](#open) функция-член, указав имя таблицы, сохраненное.  
  
    -   Чтобы создать новую таблицу, вызов объекта tabledef [создать](#create) функция-член, указав имя таблицы. Вызов [CreateField](#createfield) и [CreateIndex](#createindex) Добавление полей и индексов в таблице.  
  
    -   Вызов [Append](#append) для сохранения таблицы путем добавления его к коллекции TableDefs базы данных. **Создание** помещает tabledef в открытом состоянии, поэтому после вызова метода **создать** не следует вызывать **откройте**.  
  
        > [!TIP]
        >  Для их создания и сохранения их в базе данных Microsoft Access является самым простым способом создания сохраненных таблиц. Затем можно открыть и использовать их в коде MFC.  
  
 Чтобы использовать объект tabledef открытия или создания, создать и открыть `CDaoRecordset` объекта, указав имя tabledef с **dbOpenTable** значение в `nOpenType` параметр.  
  
 Использовать для создания объектов tabledef `CDaoRecordset` объект, вы обычно создать или открыть tabledef, как описано выше, а затем создайте объект набора записей, передать указатель на объект tabledef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Tabledef, передаваемые должно быть в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 После завершения использования объекта tabledef, вызвать его [закрыть](../../mfc/reference/cdaorecordset-class.md#close) члена функции; затем уничтожить объект tabledef.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::Append  
 Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта tabledef сохранить tabledef в базе данных.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Примечания  
 Функция добавляет объект в коллекцию TableDefs базы данных. Можно использовать tabledef как временный объект во время его определения, не добавляя ее, но если вы хотите сохранить и использовать его, необходимо вызвать **Append**.  
  
> [!NOTE]
>  При попытке добавить безымянные tabledef (содержащие значение null или пустую строку), в MFC создает исключение.  
  
 Дополнительные сведения см. в разделе «Добавить метод» в справке DAO.  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 Вызов этой функции-члена для определения ли определение базовой таблицы `CDaoTableDef` объект может быть изменен.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если изменить структуру таблицы (схема) (Добавление или удаление полей и индексы), в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию только что созданную таблицу базового `CDaoTableDef` объектов могут быть обновлены и присоединенная таблица основной `CDaoTableDef` объект не может быть обновлен. Объект `CDaoTableDef` объект может быть обновляемым, даже если результирующий набор записей не является обновляемым.  
  
 Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 Создает **CDaoTableDef** объекта.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Параметры  
 `pDatabase`  
 Указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 После создания объекта, необходимо вызвать [создать](#create) или [откройте](#open) функции-члена. После завершения работы с объектом, необходимо вызвать его [закрыть](#close) члена функции и уничтожать `CDaoTableDef` объекта.  
  
##  <a name="close"></a>CDaoTableDef::Close  
 Вызовите эту функцию-член закрыть и освободить объект tabledef.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Обычно после вызова метода **закрыть**, удалить объект tabledef, если она была выделена с помощью **новый**.  
  
 Можно вызвать [откройте](#open) снова после вызова метода **закрыть**. Это позволяет повторно использовать этот объект tabledef.  
  
 Дополнительные сведения см. в разделе «Метод Close» в справке DAO.  
  
##  <a name="create"></a>CDaoTableDef::Create  
 Вызовите эту функцию-член для создания новых сохраненных таблицы.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку, содержащую имя таблицы.  
  
 `lAttributes`  
 Значение, соответствующее характеристики таблицы, представленной объектом tabledef. Побитовое или служит для объединения любой из следующих констант:  
  
|Константа|Описание|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|  
  
 *lpszSrcTable*  
 Указатель на строку, содержащую имя исходной таблицы. По умолчанию это значение инициализируется как **NULL**.  
  
 `lpszConnect`  
 Указатель на строку, содержащую строку соединения по умолчанию. По умолчанию это значение инициализируется как **NULL**.  
  
### <a name="remarks"></a>Примечания  
 После присвоили tabledef, можно вызвать [Append](#append) сохранить tabledef в коллекции TableDefs базы данных. После вызова метода **Append**, tabledef находится в открытом состоянии и его можно использовать для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.  
  
 Дополнительные сведения см. в разделе «Метод CreateTableDef» в справке DAO.  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 Вызовите эту функцию-член для добавления поля в таблицу.  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строковое выражение, указывающее имя этого поля.  
  
 `nType`  
 Значение, указывающее тип данных поля. Параметр может принимать одно из следующих значений:  
  
|Тип|Размер (в байтах)|Описание|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 байт|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|8|Валюта ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|плавающее|  
|**dbDouble**|8|double|  
|**dbDate**|8|Даты и времени ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 – 255|Текст ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Long Binary (OLE-объект), [CLongBinary](../../mfc/reference/clongbinary-class.md) или [CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|MEMO ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 Значение, указывающее максимальный размер в байтах, поле, содержащее текст, или фиксированный размер поля, содержащего текстовых или числовых значений. `lSize` Параметр игнорируется для всех, кроме текстовых полей.  
  
 `lAttributes`  
 Значение, соответствующее характеристики поля, которые могут объединяться с помощью битовой операции или.  
  
|Константа|Описание|  
|--------------|-----------------|  
|**dbFixedField**|Размер поля является фиксированным (по умолчанию для числовых полей).|  
|**dbVariableField**|Размер поля является переменной (только текстовые поля).|  
|**dbAutoIncrField**|Значение поля для добавления новых записей автоматически увеличивается на единицу уникальный длинное целое число, не может быть изменено. Поддерживается только для таблиц базы данных Microsoft Jet.|  
|**dbUpdatableField**|Можно изменить значение поля.|  
|**dbDescending**|Поле сортируется по убыванию (Z-A или 100 – 0) порядке (применяется только к объекту поля в коллекцию полей индекса объекта). При отсутствии этой константы, поле сортируется в порядке возрастания (A – Z или 0-100) порядке (по умолчанию).|  
  
 `fieldinfo`  
 Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Объект **DAOField** (OLE) объект создается и добавляется в коллекцию полей **DAOTableDef** объектов (OLE). Помимо использования для проверки свойств объекта, можно использовать `CDaoFieldInfo` для создания входной параметр для создания нового поля в tabledef. Первая версия `CreateField` проще в использовании, но если требуется более тонкое управление, можно использовать вторую версию `CreateField`, который принимает `CDaoFieldInfo` параметр.  
  
 Если вы используете версию `CreateField` , которая принимает `CDaoFieldInfo` параметр, необходимо тщательно задать каждого из следующих членов `CDaoFieldInfo` структуры:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 Остальные элементы `CDaoFieldInfo` должно быть присвоено **0**, **FALSE**, или пустая строка, в зависимости от элемента, или `CDaoException` может возникнуть.  
  
 Дополнительные сведения см. в разделе «Метод CreateField» в справке DAO.  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 Эта функция вызывается для добавления таблицы индекса.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>Параметры  
 `indexinfo`  
 Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.  
  
### <a name="remarks"></a>Примечания  
 Индексы указывают порядок записей, доступ из таблиц базы данных и принимаются ли повторяющиеся записи. Индексы также обеспечивают эффективный способ доступа к данным.  
  
 Необходимо создать индексы для таблиц, но в больших, неиндексированную таблиц, доступ к конкретной записи или создание набора записей может занять много времени. Создание слишком много индексов замедляется с другой стороны, обновления, добавления и операции удаления, пока все индексы обновляются автоматически. Учитывать эти факторы, как вы решите, какие индексы для создания.  
  
 Следующие члены класса `CDaoIndexInfo` структуры необходимо задать:  
  
- **m_strName** необходимо указать имя.  
  
- `m_pFieldInfos`Должен указывать на массив `CDaoIndexFieldInfo` структуры.  
  
- `m_nFields`Необходимо указать количество полей в массиве `CDaoFieldInfo` структуры.  
  
 Оставшиеся члены не учитывается, если указывается **FALSE**. Кроме того **m_lDistinctCount** игнорируется во время создания индекса.  
  
##  <a name="deletefield"></a>CDaoTableDef::DeleteField  
 Вызовите эту функцию-член для удаления поля и сделать недоступными.  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строковое выражение, которое является именем существующего поля.  
  
 `nIndex`  
 Индекс поля в коллекции (с нуля) поля таблицы, для поиска по индексу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член можно использовать на новый объект, не добавляются в базу данных или при [CanUpdate](#canupdate) возвращает ненулевое значение.  
  
 Дополнительные сведения см. в разделе «Метод Delete», в справке DAO.  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 Вызовите эту функцию-член для удаления индекса в базовой таблице.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строковое выражение, которое является именем существующего индекса.  
  
 `nIndex`  
 Индекс массива объекта индекс в коллекции (с нуля) TableDefs базы данных, для поиска по индексу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член можно использовать на новый объект, который еще не были добавлены в базу данных или при [CanUpdate](#canupdate) возвращает ненулевое значение.  
  
 Дополнительные сведения см. в разделе «Метод Delete», в справке DAO.  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 Для `CDaoTableDef` объекта, возвращаемое значение определяет характеристики таблицы, представленной `CDaoTableDef` объекта и может быть сумма из этих констант:  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
  
|Константа|Описание|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|  
|**dbAttachedTable**|Указывает, что таблица является подключенной таблицы из базы данных не ODBC, такие как базы данных Paradox.|  
|**dbAttachedODBC**|Указывает, что таблица является подключенной таблицы из базы данных ODBC, например Microsoft SQL Server.|  
  
 Системная таблица является таблицей, созданные базы данных Microsoft Jet для хранения различных внутренних данных.  
  
 Скрытая таблица является таблицей, созданную для временной базы данных Microsoft Jet.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 Вызовите эту функцию-член для получения строки соединения для источника данных.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий путь и тип базы данных для таблицы.  
  
### <a name="remarks"></a>Примечания  
 Для `CDaoTableDef` , представляющий подключенной таблицы `CString` объекта состоит из одного или двух частей (описатель типа базы данных и путь к базе данных).  
  
 Пути, как показано в следующей таблице — это полный путь для каталога, содержащего файлы базы данных и должен предшествовать идентификатор» базы данных =». В некоторых случаях (как с помощью Microsoft Excel и Microsoft Jet баз данных) определенного файла включена в аргументе путь базы данных.  
  
 Таблицы в [CDaoTableDef::SetConnect](#setconnect) показывает, возможно, база данных типов и их соответствующие спецификаторы базы данных и соответствующих путей:  
  
 Для базовых таблиц базы данных Microsoft Jet, описатель является пустая строка («»).  
  
 Если пароль требуется, но не указан, драйвер ODBC входа диалоговое окно выводится при первом таблицам и снова при закрытии и повторном открытии соединения. Если присоединенная таблица имеет **dbAttachSavePWD** атрибут, вход в систему, не появляются при повторном открытии таблицы.  
  
 Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 Эта функция вызывается для определения даты и времени базовой таблицы `CDaoTableDef` был создан объект.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее дату и время создания базовой таблицы `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно с файлового сервера во избежание несоответствий; то есть, все клиенты должны использовать источник времени «стандартные», возможно, из одного сервера.  
  
 Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 Эта функция вызывается для определения даты и времени базовой таблицы **CDaoTableDef** последнего обновления объекта.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, содержащее дату и время в базовой таблице **CDaoTableDef** последнего обновления объекта.  
  
### <a name="remarks"></a>Примечания  
 Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно с файлового сервера во избежание несоответствий; то есть, все клиенты должны использовать источник времени «стандартные», возможно, из одного сервера.  
  
 Дополнительные сведения см. в разделе «DateCreated свойства LastUpdated» в справке DAO.  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 Вызовите эту функцию-член для получения количества полей, определенных в таблице.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число полей в таблице.  
  
### <a name="remarks"></a>Примечания  
 Если его значение равно 0, нет объектов в коллекции.  
  
 Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.  
  
##  <a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo  
 Вызовите эту функцию-член для получения различных типов сведений о поле, определенное в tabledef.  
  
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
 `nIndex`  
 Индекс поля объекта в коллекции (с нуля) поля таблицы, для поиска по индексу.  
  
 `fieldinfo`  
 Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.  
  
 `dwInfoOptions`  
 Параметры, определяющие, какие поля для извлечения. Ниже перечислены доступные параметры и что они могут вызывать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, тип, размер, атрибуты. Используйте этот параметр для максимальную производительность.  
  
- `AFX_DAO_SECONDARY_INFO`Сведения об основном, а также: порядковый номер позиции, необходимости разрешить нулевой длины, порядок сортировки, имя внешнего, исходное поле исходной таблицы  
  
- `AFX_DAO_ALL_INFO`Основной и дополнительной информации, а также: значение по умолчанию правило проверки, текст для проверки  
  
 `lpszName`  
 Указатель на имя объекта поля для поиска по имени. Имя является строкой с длиной до 64 символов, однозначно задает имя поля.  
  
### <a name="remarks"></a>Примечания  
 Одна версия функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.  
  
 Описание сведений, возвращаемых в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании `dwInfoOptions`. При запросе информации на одном уровне, вы получите сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 Вызовите эту функцию-член для получения числа индексов для таблицы.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество индексов для таблицы.  
  
### <a name="remarks"></a>Примечания  
 Если его значение равно 0, нет никаких индексов в коллекции.  
  
 Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.  
  
##  <a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo  
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
 `nIndex`  
 Числовой индекс, индекс объекта в коллекции (с нуля) индексы таблицы, для поиска по его позиции в коллекции.  
  
 `indexinfo`  
 Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.  
  
 `dwInfoOptions`  
 Параметры, определяющие, какие индекса для извлечения. Ниже перечислены доступные параметры и что они могут вызывать функцию возврата:  
  
- `AFX_DAO_PRIMARY_INFO`Имя, сведения о поле, поля. Используйте этот параметр для максимальную производительность.  
  
- `AFX_DAO_SECONDARY_INFO`Сведения об основном, плюс: основной, Unique, кластеризованный, пропускать пустые значения, необходимые, внешний  
  
- `AFX_DAO_ALL_INFO`Основной и дополнительной информации, а также: числа различных объектов  
  
 `lpszName`  
 Указатель на имя объекта индекса для поиска по имени.  
  
### <a name="remarks"></a>Примечания  
 Одна версия функции позволяет индекса по его позиции в коллекции. Другая версия позволяет искать индекса по имени.  
  
 Описание сведений, возвращаемых в разделе [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании `dwInfoOptions`. При запросе информации на одном уровне, вы получите сведения всех предыдущих уровней.  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 Вызовите эту функцию-член для получения определяемое пользователем имя базовой таблицы.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определяемое пользователем имя таблицы.  
  
### <a name="remarks"></a>Примечания  
 Это имя начинается с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.  
  
 Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 Вызовите эту функцию-член, чтобы узнать, сколько записей в `CDaoTableDef` объекта.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество записей, доступных в объекте tabledef.  
  
### <a name="remarks"></a>Примечания  
 Вызов `GetRecordCount` для типа таблицы `CDaoTableDef` объекта отражает приблизительное количество записей в таблице и немедленно влияет как добавления и удаления записей в таблице. Откат транзакции будут отображаться как часть счетчик записей до вызова метода [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Объект `CDaoTableDef` объект без записей имеет свойство число записей, равным 0. При работе с таблицами или баз данных ODBC, `GetRecordCount` всегда возвращает значение -1.  
  
 Дополнительные сведения см. в разделе «RecordCount свойство» в справке DAO.  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 Вызовите эту функцию-член для извлечения имени подключенной таблицы в исходной базе данных.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, который указывает имя источника, связанного с таблицей или пустая строка, если таблица данных в собственном.  
  
### <a name="remarks"></a>Примечания  
 Присоединенная таблица является таблицей в другой базе данных, связанных с базой данных Microsoft Jet. Данные для вложенных таблиц остается внешней базы данных, где ими можно управлять другими приложениями.  
  
 Дополнительные сведения см. в разделе «SourceTableName свойство» в справке DAO.  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 Вызовите эту функцию-член для получения для tabledef правила проверки.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **CString** объект, который проверяет данные в поле, изменить или добавить в таблицу.  
  
### <a name="remarks"></a>Примечания  
 Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef условиям предопределенным перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее значение [GetValidationText](#getvalidationtext) возникает исключение. Для `CDaoTableDef` объекта, это `CString` доступно только для чтения, связанных с таблицей и чтение и запись для базовой таблицы.  
  
 Дополнительные сведения см. в разделе «Свойства ValidationRule» в справке DAO.  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 Эта функция вызывается для получения строки для отображения, когда пользователь вводит данные, соответствующие правила проверки.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, который задает текст, отображаемый, если пользователь вводит данные, соответствующие правила проверки.  
  
### <a name="remarks"></a>Примечания  
 Для `CDaoTableDef` объекта, это `CString` доступно только для чтения, связанных с таблицей и чтение и запись для базовой таблицы.  
  
 Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 Вызов этой функции-члена для определения ли `CDaoTableDef` объект открыт в данный момент.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CDaoTableDef` объект является открытым; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект для этой таблицы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 Содержит указатель на интерфейс OLE для базового объекта DAO tabledef `CDaoTableDef` объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот указатель, если требуется прямой доступ к интерфейсу DAO.  
  
##  <a name="open"></a>CDaoTableDef::Open  
 Вызов этой функции-члена для открытия tabledef сохраненные в базе данных, TableDef элемента коллекции.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку, указывающее имя таблицы.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 Вызовите эту функцию-член обновить сведения о соединении для подключенной таблицы.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>Примечания  
 Изменить сведения о соединении для подключенной таблицы путем вызова [SetConnect](#setconnect) соответствующего `CDaoTableDef` объекта, а затем с помощью `RefreshLink` функции-члена для обновления данных. При вызове метода `RefreshLink`, не изменяются свойства вложенные таблицы.  
  
 Чтобы принудительно измененные сведения о подключении вступили в силу, все открытые [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекты, основанные на этом tabledef должны быть закрыты.  
  
 Дополнительные сведения см. в разделе «Метод RefreshLink» в справке DAO.  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>Параметры  
 `lAttributes`  
 Характеристики таблицы, представленной `CDaoTableDef` объекта и может быть сумма из этих констант:  
  
|Константа|Описание|  
|--------------|-----------------|  
|**dbAttachExclusive**|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|  
|**dbAttachSavePWD**|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|  
|**dbSystemObject**|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|  
|**dbHiddenObject**|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|  
  
### <a name="remarks"></a>Примечания  
 При установке нескольких атрибутов, их можно объединить суммируя соответствующие констант с помощью оператора побитового или. Установка **dbAttachExclusive** для неприсоединенных таблицы создает исключение. Сочетание следующих значений, также создают исключение:  
  
- **dbAttachExclusive | dbAttachedODBC**  
  
- **dbAttachSavePWD | dbAttachedTable**  
  
 Дополнительные сведения см. в разделе «Атрибуты свойства» в справке DAO.  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 Для `CDaoTableDef` , представляющий вложенные таблицы, строковый объект состоит из одной или двух частей (описатель типа базы данных и путь к базе данных).  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszConnect`  
 Указатель на строковое выражение, которое определяет дополнительные параметры для передачи ODBC или устанавливаемые драйверы ISAM.  
  
### <a name="remarks"></a>Примечания  
 Пути, как показано в следующей таблице — это полный путь для каталога, содержащего файлы базы данных и должен предшествовать идентификатор» базы данных =». В некоторых случаях (как с помощью Microsoft Excel и Microsoft Jet баз данных) определенного файла включена в аргументе путь базы данных.  
  
> [!NOTE]
>  Не включайте вокруг знака равенства в инструкции пути в формате «базы данных = диск:\\\path». Это приведет к возникновению исключения и сбоя подключения.  
  
 Ниже приведены типы возможно, база данных и их соответствующие спецификаторы базы данных и пути:  
  
|Тип базы данных|класса хранения|Путь|  
|-------------------|---------------|----------|  
|Базы данных с помощью базы данных Jet|"[ `database`];"|" `drive`:\\\ *path*\\\ *filename*. MDB»|  
|dBASE III|«dBASE III;»|" `drive`:\\\ *path*"|  
|dBASE IV|«dBASE IV;»|" `drive`:\\\ *path*"|  
|dBASE 5|«dBASE 5.0;»|" `drive`:\\\ *path*"|  
|Paradox 3.x|«Paradox 3.x;»|" `drive`:\\\ *path*"|  
|Paradox 4.x|«Paradox 4.x;»|" `drive`:\\\ *path*"|  
|Парадокс 5.x|«Paradox 5.x;»|" `drive`:\\\ *path*"|  
|Excel 3.0|«Excel 3.0»;|" `drive`:\\\ *path*\\\ *filename*. XLS»|  
|Excel 4.0|«Excel 4.0»;|" `drive`:\\\ *path*\\\ *filename*. XLS»|  
|Excel 5.0 или Excel 95|«Excel 5.0»;|" `drive`:\\\ *path*\\\ *filename*. XLS»|  
|Excel 97|«Excel 8.0»;|" `drive`:\\\ *path*\ *filename*. XLS»|  
|Импорт HTML|HTML «Импорт»;|" `drive`:\\\ *path*\ *filename*"|  
|Экспорт HTML-кода|«Экспорт HTML-кода»;|" `drive`:\\\ *path*"|  
|Text|«Text»;|«диск:\\\path»|  
|ODBC|«ODBC; Базы данных = `database`; UID= *user*; PWD = *пароль*; DSN = *datasourcename;* LOGINTIMEOUT = *секунды;*» (Это может быть полной строки соединения для всех серверов, это лишь пример. Это очень важно не иметь пробелов между параметры.)|Нет|  
|Exchange|«Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 | 1};]<br /><br /> [Профиль = *профиль*;]<br /><br /> [PWD = *пароль*;]<br /><br /> [БАЗЫ ДАННЫХ = `database`;]»|*"drive*:\\\ *path*\\\ *filename*. MDB»|  
  
> [!NOTE]
>  Начиная с DAO 3.5 Btrieve больше не поддерживается.  
  
 Необходимо использовать двойной обратной косой черты (\\\\) в строке подключения. Если вы изменили свойства существующего соединения с помощью `SetConnect`, после этого вызвать [RefreshLink](#refreshlink). При инициализации свойства соединения, с помощью `SetConnect`, необходим вызов не `RefreshLink`, но сначала следует выбрать для этого, добавьте tabledef.  
  
 Если пароль требуется, но не указан, драйвер ODBC входа диалоговое окно выводится при первом таблицам и снова при закрытии и повторном открытии соединения.  
  
 Можно задать строку подключения для `CDaoTableDef` объекта, предоставляя исходного аргумента для **создать** функции-члена. Вы можете проверить параметр, позволяющий определить тип, путь, идентификатор пользователя, пароль или источник данных ODBC для базы данных. Дополнительные сведения см. в документации для заданного драйвера.  
  
 Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 Вызовите эту функцию-член, чтобы задать пользовательское имя для таблицы.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строковое выражение, указывающее имя таблицы.  
  
### <a name="remarks"></a>Примечания  
 Имя должно начинаться с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.  
  
 Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 Вызовите эту функцию-член, чтобы указать имя подключенной таблицы или имя базовой таблицы, на котором `CDaoTableDef` основан объект, как оно существует в исходном источнике данных.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSrcTableName*  
 Указатель на строковое выражение, указывающее имя таблицы внешней базы данных. Для базовой таблицы, значение является пустой строкой («»).  
  
### <a name="remarks"></a>Примечания  
 Затем необходимо вызвать [RefreshLink](#refreshlink). Этот параметр пуст для базовой таблицы и чтение и запись для подключенной таблицы или объекта не добавляется в коллекцию.  
  
 Дополнительные сведения см. в разделе «SourceTableName свойство» в справке DAO.  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 Вызовите эту функцию-член правила проверки для tabledef.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszValidationRule*  
 Указатель на строковое выражение, которое проверяет операцию.  
  
### <a name="remarks"></a>Примечания  
 Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef условиям предопределенным перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее текст [GetValidationText](#getvalidationtext) отображается.  
  
 Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Выражение не может ссылаться на определяемые пользователем функции, статистические функции, статистические функции SQL или запросы. Правила проверки для `CDaoTableDef` объектов могут ссылаться на несколько полей в этом объекте.  
  
 Например, для поля с именем `hire_date` и `termination_date`, возможно, правила проверки:  
  
 [!code-cpp[NVC_MFCDatabase&#34;](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 Дополнительные сведения см. в разделе «Свойства ValidationRule» в справке DAO.  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 Эта функция-член для задания текста исключения правила проверки для вызова `CDaoTableDef` объект с базовой таблицы поддерживается ядром базы данных Microsoft Jet.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszValidationText*  
 Недопустимый указатель на строковое выражение, определяющее текст, отображаемый, если введенные данные.  
  
### <a name="remarks"></a>Примечания  
 Не удается задать текст проверки вложенные таблицы.  
  
 Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset-класс](../../mfc/reference/cdaorecordset-class.md)

