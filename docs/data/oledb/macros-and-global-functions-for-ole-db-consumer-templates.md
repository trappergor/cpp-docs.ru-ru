---
title: Макросы и глобальные функции для шаблонов потребителей OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0f6bb0949525bd844d4c9faf4a712a0b28f3fb23
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083883"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Макросы и глобальные функции для шаблонов потребителей OLE DB

Шаблоны потребителей OLE DB включают следующие макросы и глобальные функции:  
  
## <a name="global-functions"></a>Глобальные функции  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Помещает в дамп данные записи об ошибке OLE DB для устройства хранения, если возвращается ошибка.|  
  
## <a name="accessor-map-macros"></a>Макросы сопоставления доступа  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](#begin_accessor)|Отмечает начало записи метода доступа.|  
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Отмечает начало карты записей метода доступа.|  
|[END_ACCESSOR](#end_accessor)|Помечает конец записи метода доступа.|  
|[END_ACCESSOR_MAP](#end_accessor_map)|Помечает конец карты записей метода доступа.|  
  
## <a name="column-map-macros"></a>Макросы сопоставления столбцов  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](#begin_column_map)|Отмечает начало карты записей столбцов в класс записей пользователя.|  
|[BLOB_ENTRY](#blob_entry)|Используется для привязки больших двоичных объектов (BLOB).|  
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|Возвращает длину столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|Сообщает, длина и состояние столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_ENTRY_STATUS](#blob_entry_status)|Сообщает о состоянии столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_NAME](#blob_name)|Используется для привязки большого двоичного объекта по имени столбца.|  
|[BLOB_NAME_LENGTH](#blob_name_length)|Возвращает длину столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|Сообщает, длина и состояние столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BLOB_NAME_STATUS](#blob_name_status)|Сообщает о состоянии столбца данных больших двоичных ОБЪЕКТОВ.|  
|[BOOKMARK_ENTRY](#bookmark_entry)|Представляет запись закладки в наборе строк. Запись закладки — это особый тип элемента столбца.|  
|[COLUMN_ENTRY](#column_entry)|Представляет привязку к указанному столбцу в базе данных.|  
|[COLUMN_ENTRY_EX](#column_entry_ex)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *тип*, *длина*, *точности*, *масштабирования*, и *состояние* параметров.|  
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *длина* переменной.|  
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* и *длина* параметров.|  
|[COLUMN_ENTRY_PS](#column_entry_ps)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *точности* и *масштабирования* параметров.|  
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *длина* переменной, *точности* и *масштабирования* параметров.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* и *длина* переменные, *точности* и *масштабирования* параметров.|  
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* переменной, *точности* и *масштабирования* параметров.|  
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *состояние* переменной.|  
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *типа* параметра.|  
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Представляет привязку к указанному столбцу в базе данных. Поддерживает *тип* и *размер* параметров.|  
|[COLUMN_NAME](#column_name)|Представляет привязку к указанному столбцу в базе данных по имени.|  
|[COLUMN_NAME_EX](#column_name_ex)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации типа данных, размер, точность, масштаб, длину столбца и состояние столбца.|  
|[COLUMN_NAME_LENGTH](#column_name_length)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации длина столбца.|  
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации длина столбца и состояние.|  
|[COLUMN_NAME_PS](#column_name_ps)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации точность и масштаб.|  
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации длина, точность, масштаб и столбца.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации точность, масштаб, длину столбца и состояние столбца.|  
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации точность, масштаб и столбец состояния.|  
|[COLUMN_NAME_STATUS](#column_name_status)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации состояния столбца.|  
|[COLUMN_NAME_TYPE](#column_name_type)|Представляет привязку к указанному столбцу в базе данных по имени. Поддерживает спецификацию типа данных.|  
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Представляет привязку к указанному столбцу в базе данных по имени. Поддерживает спецификацию типа данных, точности и масштаба.|  
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Представляет привязку к указанному столбцу в базе данных по имени. Поддерживает спецификацию типа данных и размера.|  
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Представляет привязку к указанному столбцу в базе данных по имени. Поддержка спецификации состояние типа и столбцов данных.|  
|[END_COLUMN_MAP](#end_column_map)|Помечает конец карты записей столбцов.|  
  
## <a name="command-macros"></a>Макрос команды  
  
|||  
|-|-|  
|[DEFINE_COMMAND](#define_command)|Команда, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Принимает только строковые типы, сопоставления указанного типа приложения (ANSI или Юникод). Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо DEFINE_COMMAND.|  
|[DEFINE_COMMAND_EX](#define_command_ex)|Команда, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Поддерживает приложения, ANSI и Юникод.|  
  
## <a name="parameter-map-macros"></a>Макросы сопоставления параметров  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](#begin_param_map)|Отмечает начало карты записей параметр в класс записей пользователя.|  
|[END_PARAM_MAP](#end_param_map)|Помечает конец параметра карты записей.|  
|[SET_PARAM_TYPE](#set_param_type)|Указывает макросы COLUMN_ENTRY последующих set_param_type-макрос как входные, выходные или ввода вывода.|  

### <a name="atltraceerrorrecords"></a> AtlTraceErrorRecords

Помещает в дамп данные записи об ошибке OLE DB для устройства хранения, если возвращается ошибка.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Параметры  

*hErr*<br/>
[in] Значение типа HRESULT, возвращаемых с помощью функции члена шаблона потребителя OLE DB.  
  
#### <a name="remarks"></a>Примечания  

Если *hErr* не имеет значение S_OK, `AtlTraceErrorRecords` помещает в дамп данные записи об ошибке OLE DB для устройства хранения ( **Отладка** вкладка в окне вывода или файл). Данные записи об ошибке, полученной от поставщика, включает в себя номер строки источника, описание, файл справки, контекст и идентификатор GUID для каждой операции записи ошибки. `AtlTraceErrorRecords` выводит эти сведения только в отладочных сборках. В сборках выпуска это пустую заглушку, которая оптимизирована out.  
  
#### <a name="see-also"></a>См. также    

[Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)

### <a name="begin_accessor"></a> BEGIN_ACCESSOR

Отмечает начало записи метода доступа.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp  
BEGIN_ACCESSOR(num, bAuto)  
```  
  
#### <a name="parameters"></a>Параметры  

*num*<br/>
[in] Число ноль смещение для метода доступа в этой карте метода доступа.  
  
*кнопкой мыши*<br/>
[in] Указывает, является ли данный метод доступа автоматического доступа или метода доступа вручную. Если **true**, метод доступа — auto; Если **false**, метод доступа выполняется вручную. Метод доступа автоматически означает, что данные извлекаются для вас на операции перемещения.  
  
#### <a name="remarks"></a>Примечания  

В случае нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR-макрос для каждого отдельного метода доступа. BEGIN_ACCESSOR-макрос выполняется с помощью end_accessor-макрос. Begin_accessor_map-макрос выполняется с помощью end_accessor_map-макрос.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

Отмечает начало карты записей метода доступа.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp  
BEGIN_ACCESSOR_MAP(x, num)  
```  
  
#### <a name="parameters"></a>Параметры  

*x*<br/>
[входные данные] Имя класса записей пользователя.  
  
*num*<br/>
[входные данные] Число методов доступа в этой карте метода доступа.  
  
#### <a name="remarks"></a>Примечания  

В случае нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP в начале и использовать BEGIN_ACCESSOR-макрос для каждого отдельного метода доступа. BEGIN_ACCESSOR-макрос выполняется с помощью end_accessor-макрос. Карта метода доступа выполняется с помощью end_accessor_map-макрос.  
  
Если в записи пользователя имеется только один метод доступа, используйте макрос [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).  
  
#### <a name="example"></a>Пример  

```cpp  
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a> END_ACCESSOR

Помечает конец записи метода доступа.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_ACCESSOR()  
```  
  
#### <a name="remarks"></a>Примечания  

Для нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR-макрос для каждого отдельного метода доступа. BEGIN_ACCESSOR-макрос выполняется с помощью end_accessor-макрос. Begin_accessor_map-макрос выполняется с помощью end_accessor_map-макрос.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="end_accessor_map"></a> END_ACCESSOR_MAP

Помечает конец карты записей метода доступа.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_ACCESSOR_MAP()  
```  
  
#### <a name="remarks"></a>Примечания  

Для нескольких методов доступа в наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR-макрос для каждого отдельного метода доступа. BEGIN_ACCESSOR-макрос выполняется с помощью end_accessor-макрос. Begin_accessor_map-макрос выполняется с помощью end_accessor_map-макрос.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="begin_column_map"></a> BEGIN_COLUMN_MAP

Отмечает начало карты записей столбцов.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp  
BEGIN_COLUMN_MAP(x)  
```  
  
#### <a name="parameters"></a>Параметры  

*x*<br/>
[входные данные] Имя класса записей пользователя, производного от `CAccessor`.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос используется при наличии одного метода доступа в наборе строк. При наличии нескольких методов доступа в наборе строк, используйте [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
BEGIN_COLUMN_MAP-макрос выполняется с помощью END_COLUMN_MAP-макрос. Этот макрос используется, если имеется только один метод доступа, необходимый для записи пользователя.  
  
Столбцы соответствуют полям в наборе строк, который нужно привязать.  
  
#### <a name="example"></a>Пример  

Ниже приведен пример карты столбцов и параметров.  
  
<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a> BLOB_ENTRY

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)).  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="example"></a>Пример  

См. в разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает длину в байтах столбца BLOB-ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)  
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[out] (Фактические) длина в байтах столбца BLOB-ОБЪЕКТОВ.  
  
#### <a name="example"></a>Пример  

См. в разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также возвращает длину и состояние столбца BLOB-ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_ENTRY_LENGTH_STATUS(  
    nOrdinal,  
    IID,  
    flags,  
    data,
    length,
    status )  
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[out] (Фактические) длина в байтах столбца BLOB-ОБЪЕКТОВ.  
  
*status*<br/>
[out] Состояние столбца данных больших двоичных ОБЪЕКТОВ.  
  
#### <a name="example"></a>Пример  

См. в разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

Используется с BEGIN_COLUMN_MAP или BEGIN_ACCESSOR_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает состояние столбца BLOB-ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)   
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[out] Состояние поля типа BLOB.  
  
#### <a name="example"></a>Пример  

См. в разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_name"></a> BLOB_NAME

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос принимает имя столбца, а не как число столбцов.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_NAME(pszName, IID, flags, data )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="example"></a>Пример  

См. в разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_name_length"></a> BLOB_NAME_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [имя_большого_двоичного_объекта](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает длину в байтах данных столбца больших двоичных ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[out] (Фактические) длина в байтах столбца BLOB-ОБЪЕКТОВ.  

### <a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [имя_большого_двоичного_объекта](../../data/oledb/blob-name.md), за исключением того, что этот макрос также возвращает длину и состояние столбца данных больших двоичных ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[out] (Фактические) длина в байтах столбца BLOB-ОБЪЕКТОВ.  
  
*status*<br/>
[out] Состояние поля типа BLOB.  

### <a name="blob_name_status"></a> BLOB_NAME_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP для привязки больших двоичных объектов ([BLOB-ОБЪЕКТОВ](/previous-versions/windows/desktop/ms711511)). Аналогичную [имя_большого_двоичного_объекта](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает состояние столбца данных больших двоичных ОБЪЕКТОВ.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*IID*<br/>
[in] Интерфейс GUID, такие как `IDD_ISequentialStream`, которое используется для получения большого двоичного ОБЪЕКТА.  
  
*flags*<br/>
[in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, `STGM_READ`).  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[out] Состояние поля типа BLOB.  
  
### <a name="bookmark_entry"></a> BOOKMARK_ENTRY

Привязывает закладку для столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BOOKMARK_ENTRY(variable)  
```  
  
#### <a name="parameters"></a>Параметры  

*Переменная*<br/>
[in] Переменная для привязки столбца закладки.  
  
#### <a name="example"></a>Пример  

```cpp  
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```
  
#### <a name="see-also"></a>См. также  

[Класс CBookmark](../../data/oledb/cbookmark-class.md)<br/>
[DBPROP_BOOKMARKS](/previous-versions/windows/desktop/ms709728)

### <a name="column_entry"></a> COLUMN_ENTRY

Представляет привязку в наборе строк, определенный столбец в наборе строк.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY(nOrdinal, data)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

COLUMN_ENTRY-макрос используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
#### <a name="example"></a>Пример  

См. в примерах в разделах макрос [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="column_entry_ex"></a> COLUMN_ENTRY_EX

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*wType*<br/>
[in] Тип данных.  
  
*nLength*<br/>
[in] Размер данных в байтах.  
  
*nPrecision*<br/>
[in] Максимальная точность для использования при получении данных и *wType* является `DBTYPE_NUMERIC`. В противном случае этот параметр учитывается.  
  
*nScale*<br/>
[in] Шкалу для использования при получении данных и *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

Column_entry_ex-макрос используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
#### <a name="example"></a>Пример  

См. в разделе [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца, начиная с единицы. Закладка соответствует нулевым столбцом.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос поддерживает *длина* переменной. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
### <a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

Используйте этот макрос, если требуется поддерживать длина и состояние переменных. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_entry_ps"></a> COLUMN_ENTRY_PS

Представляет привязку в наборе строк, определенный столбец в наборе строк.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать точность и масштаб столбца, который вы хотите выполнить привязку. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца, начиная с единицы. Закладка соответствует нулевым столбцом.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать точность и масштаб столбца, который вы хотите выполнить привязку. Этот макрос поддерживает *длина* переменной. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать точность и масштаб столбца, который вы хотите выполнить привязку. Используйте этот макрос, если требуется поддерживать длина и состояние переменных. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать точность и масштаб столбца, который вы хотите выполнить привязку. Этот макрос поддерживает *состояние* переменной. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
### <a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

Представляет привязку в наборе строк, определенный столбец в базе данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [DBBINDING](/previous-versions/windows/desktop/ms716845) в *справочнике программиста OLE DB*.  
  
*nOrdinal*<br/>
[in] Номер столбца.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос поддерживает *состояние* переменной. Он используется в следующих местах:  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

Представляет привязку к указанному столбцу в базе данных. Поддерживает *типа* параметра.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*wType*<br/>
[in] Тип данных записи в столбце.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос представляет собой специализированный вариант [COLUMN_ENTRY](../../data/oledb/column-entry.md) макрос, который предоставляет средства для указания типа данных.  

### <a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

Представляет привязку к указанному столбцу в базе данных. Поддерживает *тип* и *размер* параметров.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*nOrdinal*<br/>
[in] Номер столбца.  
  
*wType*<br/>
[in] Тип данных записи в столбце.  
  
*nLength*<br/>
[in] Размер записи в столбце в байтах.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос представляет собой специализированный вариант [COLUMN_ENTRY](../../data/oledb/column-entry.md) макрос, который предоставляет средства для указания типа и размера данных.  

### <a name="column_name"></a> COLUMN_NAME

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_ENTRY](../../data/oledb/column-entry.md), за исключением того, что этот макрос принимает имя столбца, а не номер столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME(pszName, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

В тех же расположениях, как используются макросы COLUMN_NAME_ * [COLUMN_ENTRY](../../data/oledb/column-entry.md):  
  
- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  

### <a name="column_name_ex"></a> COLUMN_NAME_EX

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных, размер, точность, масштаб, длину столбца и состояние столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*wType*<br/>
[in] Тип данных.  
  
*nLength*<br/>
[in] Размер данных в байтах.  
  
*nPrecision*<br/>
[in] Максимальная точность для использования при получении данных и *wType* является `DBTYPE_NUMERIC`. В противном случае этот параметр учитывается.  
  
*nScale*<br/>
[in] Шкалу для использования при получении данных и *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_length"></a> COLUMN_NAME_LENGTH

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает длину столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_LENGTH(pszName, data, length)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает длину столбца и состояние столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_ps"></a> COLUMN_NAME_PS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос принимает также точность и масштаб.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает длину, точность, масштаб и столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает точность, масштаб, длину столбца и состояние столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*length*<br/>
[in] Переменная для привязки к длина столбца.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает точность, масштаб и столбец состояния.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*nPrecision*<br/>
[in] Максимальная точность столбца, который вы хотите выполнить привязку.  
  
*nScale*<br/>
[in] Масштаб столбца, который вы хотите выполнить привязку.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_status"></a> COLUMN_NAME_STATUS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает состояние столбца.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_STATUS(pszName, data, status )  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_type"></a> COLUMN_NAME_TYPE

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_TYPE(pszName, wType, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*wType*<br/>
[in] Тип данных.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных, точность и масштаб.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*wType*<br/>
[in] Тип данных.  
  
*nPrecision*<br/>
[in] Максимальная точность для использования при получении данных и *wType* является `DBTYPE_NUMERIC`. В противном случае этот параметр учитывается.  
  
*nScale*<br/>
[in] Шкалу для использования при получении данных и *wType* — `DBTYPE_NUMERIC` или `DBTYPE_DECIMAL`.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип и размер.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*wType*<br/>
[in] Тип данных.  
  
*nLength*<br/>
[in] Размер данных в байтах.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

Представляет привязку в наборе строк, определенный столбец в наборе строк. Аналогичную [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип и столбец состояния данных.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)  
```  
  
#### <a name="parameters"></a>Параметры  

*pszName*<br/>
[in] Указатель на имя столбца. Имя должно быть строкой Юникода. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
*wType*<br/>
[in] Тип данных.  
  
*status*<br/>
[in] Переменная для привязки к состояние столбца.  
  
*data*<br/>
[in] Соответствующий элемент данных в записи пользователя.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения, в которых используются макросы COLUMN_NAME_ *.  

### <a name="end_column_map"></a> END_COLUMN_MAP

Помечает конец карты записей столбцов.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_COLUMN_MAP()  
```  
  
#### <a name="remarks"></a>Примечания  

Он используется с помощью одного метода доступа для набора строк. BEGIN_COLUMN_MAP-макрос выполняется с помощью END_COLUMN_MAP-макрос.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).  

### <a name="define_command"></a> DEFINE_COMMAND

Команда, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Принимает только строковые типы, сопоставления указанного типа приложения (ANSI или Юникод).  
  
> [!NOTE]
>  Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо DEFINE_COMMAND.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
```  
  
#### <a name="parameters"></a>Параметры  

*x*<br/>
[in] Имя класса записей (команда) пользователя.  
  
*szCommand*<br/>
[in] Командная строка, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
#### <a name="remarks"></a>Примечания  

Командная строка, которая вами будет использоваться по умолчанию, если вы не укажете текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) метод.  
  
Этот макрос принимает строки ANSI, если сборка приложения осуществляется как ANSI или строки в Юникоде, если сборка приложения осуществляется в Юникоде. Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо DEFINE_COMMAND, так как первый принимает строк в Юникоде независимо от типа приложения ANSI или Юникод.  
  
#### <a name="example"></a>Пример  

См. в разделе [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="define_command_ex"></a> DEFINE_COMMAND_EX

Команда, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Поддержка Юникода в ANSI и приложения.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
```  
  
#### <a name="parameters"></a>Параметры  

*x*<br/>
[in] Имя класса записей (команда) пользователя.  
  
*wszCommand*<br/>
[in] Командная строка, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
#### <a name="remarks"></a>Примечания  

Командная строка, которая вами будет использоваться по умолчанию, если вы не укажете текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) метод.  
  
Этот макрос принимает строк в Юникоде независимо от типа приложения. Этот макрос предпочтительнее, чем [DEFINE_COMMAND](../../data/oledb/define-command.md) так как он поддерживает Юникод и ANSI приложений.  
  
#### <a name="example"></a>Пример  

См. в разделе [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="begin_param_map"></a> BEGIN_PARAM_MAP

Отмечает начало карты записей параметра.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PARAM_MAP(x)  
```  
  
#### <a name="parameters"></a>Параметры  

*x*<br/>
[входные данные] Имя класса записей пользователя.  
  
#### <a name="remarks"></a>Примечания  

Используются параметры [команды](/previous-versions/windows/desktop/ms724608).  
  
#### <a name="example"></a>Пример  

См. в примере [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) макрос.  

### <a name="end_param_map"></a> END_PARAM_MAP

Помечает конец параметра карты записей.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_PARAM_MAP()  
```  
  
#### <a name="example"></a>Пример  

См. в примере [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) макрос.  
  
### <a name="set_param_type"></a> SET_PARAM_TYPE

Указывает макросы COLUMN_ENTRY последующих SET_PARAM_TYPE макрос входной, выходной или ввода вывода.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
SET_PARAM_TYPE(type)  
```  
  
#### <a name="parameters"></a>Параметры  

*type*<br/>
[входные данные] Тип, задаваемый для параметра.  
  
#### <a name="remarks"></a>Примечания  

Поставщики поддерживают только входные и выходные типы параметров, поддерживаемые в базовом источнике данных. Тип представляет собой сочетание одного или нескольких `DBPARAMIO` значения (см. в разделе [структуры DBBINDING](/previous-versions/windows/desktop/ms716845) в *Справочник программиста OLE DB по*):  
  
- `DBPARAMIO_NOTPARAM` Метод доступа не имеет параметров. Обычно задается `eParamIO` этому значению в строке доступа, чтобы напомнить пользователям, что параметры игнорируются.  
  
- `DBPARAMIO_INPUT` Входной параметр.  
  
- `DBPARAMIO_OUTPUT` Выходной параметр.  
  
- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` Параметр является входным и выходным параметром.  
  
#### <a name="example"></a>Пример  

```cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 

## <a name="requirements"></a>Требования  

**Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  

[Макросы и глобальные функции для шаблонов объектов-получателей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)    