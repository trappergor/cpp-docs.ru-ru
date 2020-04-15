---
title: Макросы и глобальные функции для шаблонов потребителей OLE DB
ms.date: 02/11/2019
f1_keywords:
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
ms.openlocfilehash: 8b898990672f590f6047eef6fdfd1ed7eecb3f92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369828"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Макросы и глобальные функции для шаблонов потребителей OLE DB

Шаблоны для потребителей OLE DB включают следующие макросы и глобальные функции:

## <a name="global-functions"></a>Глобальные функции

|||
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Сбрасывает информацию об ошибке OLE DB на устройство свалки в случае возврата ошибки.|

## <a name="accessor-map-macros"></a>Аксессуар Карта Макрос

|||
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|Отмечает начало входа аксессуара.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Отмечает начало карты записей метода доступа.|
|[END_ACCESSOR](#end_accessor)|Отметки конца входа аксессуара.|
|[END_ACCESSOR_MAP](#end_accessor_map)|Отметки конца записей карты доступа.|

## <a name="column-map-macros"></a>Колонка Карта Макрос

|||
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|Отмечает начало записи карты столбца в классе записей пользователей.|
|[BLOB_ENTRY](#blob_entry)|Используется для связывания двоичного крупного объекта (BLOB).|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|Сообщает длину столбца данных BLOB.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|Сообщает длину и состояние столбца данных BLOB.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|Сообщает о состоянии столбца данных BLOB.|
|[BLOB_NAME](#blob_name)|Используется для связывания двоичного крупного объекта по имени столбца.|
|[BLOB_NAME_LENGTH](#blob_name_length)|Сообщает длину столбца данных BLOB.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|Сообщает длину и состояние столбца данных BLOB.|
|[BLOB_NAME_STATUS](#blob_name_status)|Сообщает о состоянии столбца данных BLOB.|
|[BOOKMARK_ENTRY](#bookmark_entry)|Представляет запись закладки на наборе строк. Запись закладки — это особый вид ввода столбца.|
|[COLUMN_ENTRY](#column_entry)|Представляет собой привязку к определенному столбце в базе данных.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает *тип,* *длину,* *точность,* *масштабирование*и параметры *статуса.*|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает переменную *длины.*|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает параметры *статуса* и *длины.*|
|[COLUMN_ENTRY_PS](#column_entry_ps)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает параметры *точности* и *масштаба.*|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает переменные *длины,* *точность* и *параметры масштаба.*|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает переменные *состояния* и *длины,* параметры *точности* и *масштаба.*|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает переменные *статуса,* *точность* и *параметры масштаба.*|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Представляет собой привязку к конкретной колонке в базе данных. Поддерживает переменную *статуса.*|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Представляет собой привязку к определенному столбце в базе данных. Параметры *типа* поддерживается.|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Представляет собой привязку к конкретной колонке в базе данных. Параметры *типа* и *размера* поддерживается.|
|[Column_name](#column_name)|Представляет собой привязку к определенному столбце в базе данных по имени.|
|[COLUMN_NAME_EX](#column_name_ex)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию типа данных, размера, точности, масштаба, длины столбцов и состояния столбца.|
|[COLUMN_NAME_LENGTH](#column_name_length)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию длины колонны.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию длины и статуса столба.|
|[COLUMN_NAME_PS](#column_name_ps)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию точности и масштаба.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию точности, масштаба и длины колонны.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию точности, масштаба, длины столбца и состояния столбца.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию точного состояния, масштаба и состояния столбца.|
|[COLUMN_NAME_STATUS](#column_name_status)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию состояния столбца.|
|[COLUMN_NAME_TYPE](#column_name_type)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию типа данных.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию типа, точности и масштаба данных.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию типа и размера данных.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Представляет собой привязку к определенному столбце в базе данных по имени. Поддерживает спецификацию типа данных и состояния столбца.|
|[END_COLUMN_MAP](#end_column_map)|Отметки конца записей карты столбца.|

## <a name="command-macros"></a>Командование Макрос

|||
|-|-|
|[DEFINE_COMMAND](#define_command)|Осведряй команду, которая будет использоваться для создания строки при использовании класса [CCommand.](../../data/oledb/ccommand-class.md) Принимает только типы строк, соответствующие указанному типу приложения (ANSI или Unicode). Рекомендуется использовать [DEFINE_COMMAND_EX,](../../data/oledb/define-command-ex.md) а не DEFINE_COMMAND.|
|[DEFINE_COMMAND_EX](#define_command_ex)|Осведряй команду, которая будет использоваться для создания строки при использовании класса [CCommand.](../../data/oledb/ccommand-class.md) Поддерживает приложения ANSI и Unicode.|

## <a name="parameter-map-macros"></a>Параметр Карта Макрос

|||
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|Отмечает начало записи параметра карты в классе записей пользователей.|
|[END_PARAM_MAP](#end_param_map)|Отметки конца записей карты параметра.|
|[SET_PARAM_TYPE](#set_param_type)|Отославаю COLUMN_ENTRY макросы, которые следуют SET_PARAM_TYPE макросу в качестве входных данных, выходных данных или ввода/вывода.|

### <a name="atltraceerrorrecords"></a><a name="atltraceerrorrecords"></a>AtlTraceErrorRecords

Сбрасывает информацию об ошибке OLE DB на устройство свалки в случае возврата ошибки.

#### <a name="syntax"></a>Синтаксис

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>Параметры

*Герр*<br/>
(в) HRESULT возвращается функцией члена программы OLE DB Consumer Template.

#### <a name="remarks"></a>Remarks

Если *hErr* не `AtlTraceErrorRecords` S_OK, сбрасывает информацию об ошибке OLE DB в устройство свалки (вкладка **Debug** окна вывода или файла). Информация о записи ошибок, полученная от поставщика, включает номер строки, источник, описание, файл справки, контекст и GUID для каждой записи ошибки. `AtlTraceErrorRecords`сбрасывает эту информацию только в отладочных сборках. В сборках релизов, это пустой заглушка, которая оптимизирована. Для получения дополнительной информации [см.](../../data/oledb/cdberrorinfo-class.md)

### <a name="begin_accessor"></a><a name="begin_accessor"></a>BEGIN_ACCESSOR

Отмечает начало входа аксессуара.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>Параметры

*num*<br/>
(в) Номер с нулевым смещением для аксессуара на этой карте аксессуаров.

*bAuto*<br/>
(в) Указывается, является ли этот аксессуар автоматическим аксессуаром или ручным аксессуаром. Если **это правда,** аксессуар является автоматическим; если **ложный,** аксессуар вручную. Автоматический аксессуар означает, что данные извлекаются для вас при операциях перемещения.

#### <a name="remarks"></a>Remarks

В случае нескольких аксессуаров на наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR макрос для каждого отдельного аксессуара. Макрос BEGIN_ACCESSOR дополнен END_ACCESSOR макросом. Макрос BEGIN_ACCESSOR_MAP дополнен макросом END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

Смотрите [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_accessor_map"></a><a name="begin_accessor_map"></a>Begin_accessor_map

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

#### <a name="remarks"></a>Remarks

В случае нескольких аксессуаров на наборе строк необходимо указать BEGIN_ACCESSOR_MAP в начале и использовать BEGIN_ACCESSOR макрос для каждого отдельного аксессуара. Макрос BEGIN_ACCESSOR дополнен END_ACCESSOR макросом. Карта доступа дополнена макросом END_ACCESSOR_MAP.

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

### <a name="end_accessor"></a><a name="end_accessor"></a>END_ACCESSOR

Отметки конца входа аксессуара.

#### <a name="syntax"></a>Синтаксис

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>Remarks

Для нескольких аксессуаров на наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR макрос для каждого отдельного аксессуара. Макрос BEGIN_ACCESSOR дополнен END_ACCESSOR макросом. Макрос BEGIN_ACCESSOR_MAP дополнен макросом END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

Смотрите [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="end_accessor_map"></a><a name="end_accessor_map"></a>END_ACCESSOR_MAP

Отметки конца записей карты доступа.

#### <a name="syntax"></a>Синтаксис

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>Remarks

Для нескольких аксессуаров на наборе строк необходимо указать BEGIN_ACCESSOR_MAP и использовать BEGIN_ACCESSOR макрос для каждого отдельного аксессуара. Макрос BEGIN_ACCESSOR дополнен END_ACCESSOR макросом. Макрос BEGIN_ACCESSOR_MAP дополнен макросом END_ACCESSOR_MAP.

#### <a name="example"></a>Пример

Смотрите [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_column_map"></a><a name="begin_column_map"></a>BEGIN_COLUMN_MAP

Отмечает начало карты записей столбцов.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
[входные данные] Имя класса записей пользователя, производного от `CAccessor`.

#### <a name="remarks"></a>Remarks

Этот макрос используется при наличии одного метода доступа в наборе строк. При наличии нескольких методов доступа в наборе строк, используйте [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

Макрос BEGIN_COLUMN_MAP дополнен макросом END_COLUMN_MAP. Этот макрос используется, если имеется только один метод доступа, необходимый для записи пользователя.

Столбцы соответствуют полям в наборе строк, который нужно привязать.

#### <a name="example"></a>Пример

Ниже приведен пример карты столбцов и параметров.

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a><a name="blob_entry"></a>BLOB_ENTRY

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))).

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>Параметры

*nОрдинал*<br/>
(в) Номер столбца.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="example"></a>Пример

[Посмотрите, как я могу получить BLOB?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length"></a><a name="blob_entry_length"></a>BLOB_ENTRY_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_ENTRY,](../../data/oledb/blob-entry.md)за исключением того, что этот макрос также получает длину в байтах столбца BLOB.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>Параметры

*nОрдинал*<br/>
(в) Номер столбца.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(ваут) (фактическая) длина байтов столбца BLOB.

#### <a name="example"></a>Пример

[Посмотрите, как я могу получить BLOB?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length_status"></a><a name="blob_entry_length_status"></a>BLOB_ENTRY_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_ENTRY,](../../data/oledb/blob-entry.md)за исключением того, что этот макрос также получает длину и статус столбца BLOB.

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

*nОрдинал*<br/>
(в) Номер столбца.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(ваут) (фактическая) длина байтов столбца BLOB.

*состояние*<br/>
(ваут) Состояние столбца данных BLOB.

#### <a name="example"></a>Пример

[Посмотрите, как я могу получить BLOB?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_status"></a><a name="blob_entry_status"></a>BLOB_ENTRY_STATUS

Используется с BEGIN_COLUMN_MAP или BEGIN_ACCESSOR_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_ENTRY,](../../data/oledb/blob-entry.md)за исключением того, что этот макрос также получает статус столбца BLOB.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>Параметры

*nОрдинал*<br/>
(в) Номер столбца.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(ваут) Статус поля BLOB.

#### <a name="example"></a>Пример

[Посмотрите, как я могу получить BLOB?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name"></a><a name="blob_name"></a>BLOB_NAME

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_ENTRY,](../../data/oledb/blob-entry.md)за исключением того, что этот макрос берет имя столбца вместо номера столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="example"></a>Пример

[Посмотрите, как я могу получить BLOB?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name_length"></a><a name="blob_name_length"></a>BLOB_NAME_LENGTH

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_NAME,](../../data/oledb/blob-name.md)за исключением того, что этот макрос также получает длину в байтах столбца данных BLOB.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(ваут) (фактическая) длина байтов столбца BLOB.

### <a name="blob_name_length_status"></a><a name="blob_name_length_status"></a>BLOB_NAME_LENGTH_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_NAME,](../../data/oledb/blob-name.md)за исключением того, что этот макрос также получает длину и статус столбца данных BLOB.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(ваут) (фактическая) длина байтов столбца BLOB.

*состояние*<br/>
(ваут) Статус поля BLOB.

### <a name="blob_name_status"></a><a name="blob_name_status"></a>BLOB_NAME_STATUS

Используется с BEGIN_COLUMN_MAP и END_COLUMN_MAP, чтобы связать двоичный большой объект[(BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). Как и [BLOB_NAME,](../../data/oledb/blob-name.md)за исключением того, что этот макрос также получает статус столбца данных BLOB.

#### <a name="syntax"></a>Синтаксис

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*IID*<br/>
(в) Интерфейс GUID, `IDD_ISequentialStream`например, используется для получения BLOB.

*Флаги*<br/>
(в) Флаги режима хранения в соответствии с моделью `STGM_READ`структурированного хранения OLE (например, ).

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(ваут) Статус поля BLOB.

### <a name="bookmark_entry"></a><a name="bookmark_entry"></a>BOOKMARK_ENTRY

Связывает столбец закладки.

#### <a name="syntax"></a>Синтаксис

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>Параметры

*переменная*<br/>
(в) Переменная, которая будет привязана к столбце закладки.

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

Для получения дополнительной информации [CBookmark Class](../../data/oledb/cbookmark-class.md) [см.](using-bookmarks.md)

### <a name="column_entry"></a><a name="column_entry"></a>COLUMN_ENTRY

Представляет собой привязку к набору строк к определенному столбце в строке.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

Макрос COLUMN_ENTRY используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

#### <a name="example"></a>Пример

Смотрите примеры в макротемах, [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="column_entry_ex"></a><a name="column_entry_ex"></a>COLUMN_ENTRY_EX

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*wType*<br/>
(в) Тип данных.

*nДлина*<br/>
(в) Размер данных в байтах.

*nТочность*<br/>
(в) Максимальная точность в использовании при `DBTYPE_NUMERIC`получении данных и *wType* . В противном случае этот параметр игнорируется.

*nScale*<br/>
(в) Шкала для использования при получении `DBTYPE_NUMERIC` `DBTYPE_DECIMAL`данных и *wType* является или .

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

Макрос COLUMN_ENTRY_EX используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

#### <a name="example"></a>Пример

Смотрите [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="column_entry_length"></a><a name="column_entry_length"></a>COLUMN_ENTRY_LENGTH

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца, начиная с одного. Закладка соответствует столбце ноль.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

#### <a name="remarks"></a>Remarks

Этот макрос поддерживает переменную *длины.* Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_length_status"></a><a name="column_entry_length_status"></a>COLUMN_ENTRY_LENGTH_STATUS

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

Используйте этот макрос, когда требуется поддерживать переменные длины и состояния. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps"></a><a name="column_entry_ps"></a>COLUMN_ENTRY_PS

Представляет собой привязку к набору строк к определенному столбце в строке.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

Позволяет указать точность и масштаб столбца, который вы хотите связать. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_length"></a><a name="column_entry_ps_length"></a>COLUMN_ENTRY_PS_LENGTH

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца, начиная с одного. Закладка соответствует столбце ноль.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

#### <a name="remarks"></a>Remarks

Позволяет указать точность и масштаб столбца, который вы хотите связать. Этот макрос поддерживает переменную *длины.* Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_length_status"></a><a name="column_entry_ps_length_status"></a>COLUMN_ENTRY_PS_LENGTH_STATUS

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

Позволяет указать точность и масштаб столбца, который вы хотите связать. Используйте этот макрос, когда требуется поддерживать переменные длины и состояния. Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_ps_status"></a><a name="column_entry_ps_status"></a>COLUMN_ENTRY_PS_STATUS

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

Позволяет указать точность и масштаб столбца, который вы хотите связать. Этот макрос поддерживает переменную *статуса.* Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_status"></a><a name="column_entry_status"></a>COLUMN_ENTRY_STATUS

Представляет собой привязку к набору строк к конкретному столбце в базе данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>Параметры

Смотрите [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB*.

*nОрдинал*<br/>
(в) Номер столбца.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

Этот макрос поддерживает переменную *статуса.* Он используется в следующих местах:

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_entry_type"></a><a name="column_entry_type"></a>COLUMN_ENTRY_TYPE

Представляет собой привязку к конкретной колонке в базе данных. Параметры *типа* поддерживается.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>Параметры

*nОрдинал*<br/>
(в) Номер столбца.

*wType*<br/>
(в) Тип ввода столбца.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

Этот макрос является специализированным вариантом [COLUMN_ENTRY](../../data/oledb/column-entry.md) макроса, который предоставляет средство определения типа данных.

### <a name="column_entry_type_size"></a><a name="column_entry_type_size"></a>COLUMN_ENTRY_TYPE_SIZE

Представляет собой привязку к конкретной колонке в базе данных. Параметры *типа* и *размера* поддерживается.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>Параметры

*nОрдинал*<br/>
(в) Номер столбца.

*wType*<br/>
(в) Тип ввода столбца.

*nДлина*<br/>
(в) Размер входа столбца в байтах.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

Этот макрос является специализированным вариантом [COLUMN_ENTRY](../../data/oledb/column-entry.md) макроса, который предоставляет средства определения размера и типа данных.

### <a name="column_name"></a><a name="column_name"></a>Column_name

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_ENTRY,](../../data/oledb/column-entry.md)за исключением того, что этот макрос берет имя столбца вместо номера столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

Макросы COLUMN_NAME_ используются в тех же местах, [что и COLUMN_ENTRY:](../../data/oledb/column-entry.md)

- Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросами.

- Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросами.

- Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросами.

### <a name="column_name_ex"></a><a name="column_name_ex"></a>COLUMN_NAME_EX

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает тип данных, размер, точность, масштаб, длину столбца и статус столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*wType*<br/>
(в) Тип данных.

*nДлина*<br/>
(в) Размер данных в байтах.

*nТочность*<br/>
(в) Максимальная точность в использовании при `DBTYPE_NUMERIC`получении данных и *wType* . В противном случае этот параметр игнорируется.

*nScale*<br/>
(в) Шкала для использования при получении `DBTYPE_NUMERIC` `DBTYPE_DECIMAL`данных и *wType* является или .

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_length"></a><a name="column_name_length"></a>COLUMN_NAME_LENGTH

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также занимает длину столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_length_status"></a><a name="column_name_length_status"></a>COLUMN_NAME_LENGTH_STATUS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает статус длины столбца и столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_ps"></a><a name="column_name_ps"></a>COLUMN_NAME_PS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также занимает точность и масштаб.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_ps_length"></a><a name="column_name_ps_length"></a>COLUMN_NAME_PS_LENGTH

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также занимает точность, масштаб и длину столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_ps_length_status"></a><a name="column_name_ps_length_status"></a>COLUMN_NAME_PS_LENGTH_STATUS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает точность, масштаб, длину столбца и статус столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*длина*<br/>
(в) Переменная, которая будет привязана к длине столбца.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_ps_status"></a><a name="column_name_ps_status"></a>COLUMN_NAME_PS_STATUS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также имеет точное состояние, масштаб и статус столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*nТочность*<br/>
(в) Максимальная точность столбца, который вы хотите связать.

*nScale*<br/>
(в) Масштаб столбца, который необходимо связать.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_status"></a><a name="column_name_status"></a>COLUMN_NAME_STATUS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает статус столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_type"></a><a name="column_name_type"></a>COLUMN_NAME_TYPE

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает тип данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*wType*<br/>
(в) Тип данных.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_type_ps"></a><a name="column_name_type_ps"></a>COLUMN_NAME_TYPE_PS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает тип данных, точность и масштаб.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*wType*<br/>
(в) Тип данных.

*nТочность*<br/>
(в) Максимальная точность в использовании при `DBTYPE_NUMERIC`получении данных и *wType* . В противном случае этот параметр игнорируется.

*nScale*<br/>
(в) Шкала для использования при получении `DBTYPE_NUMERIC` `DBTYPE_DECIMAL`данных и *wType* является или .

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_type_size"></a><a name="column_name_type_size"></a>COLUMN_NAME_TYPE_SIZE

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает тип и размер данных.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*wType*<br/>
(в) Тип данных.

*nДлина*<br/>
(в) Размер данных в байтах.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="column_name_type_status"></a><a name="column_name_type_status"></a>COLUMN_NAME_TYPE_STATUS

Представляет собой привязку к набору строк к определенному столбце в строке. Как и [COLUMN_NAME,](../../data/oledb/column-name.md)за исключением того, что этот макрос также принимает тип данных и статус столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>Параметры

*pszName*<br/>
(в) Указатель на имя столбца. Имя должно быть строкой Unicode. Вы можете сделать это, поставив 'L' перед именем, например: `L"MyColumn"`.

*wType*<br/>
(в) Тип данных.

*состояние*<br/>
(в) Переменная, которая будет привязана к статусу столбца.

*данные*<br/>
(в) Соответствующий член данных в записи пользователя.

#### <a name="remarks"></a>Remarks

О [COLUMN_NAME](../../data/oledb/column-name.md) том, где используются макросы COLUMN_NAME_.

### <a name="end_column_map"></a><a name="end_column_map"></a>END_COLUMN_MAP

Отметки конца записей карты столбца.

#### <a name="syntax"></a>Синтаксис

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>Remarks

Используется с одним аксессуаром на наборе. Макрос BEGIN_COLUMN_MAP дополнен макросом END_COLUMN_MAP.

#### <a name="example"></a>Пример

Смотрите [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

### <a name="define_command"></a><a name="define_command"></a>DEFINE_COMMAND

Осведряй команду, которая будет использоваться для создания строки при использовании класса [CCommand.](../../data/oledb/ccommand-class.md) Принимает только типы строк, соответствующие указанному типу приложения (ANSI или Unicode).

> [!NOTE]
> Рекомендуется использовать [DEFINE_COMMAND_EX,](../../data/oledb/define-command-ex.md) а не DEFINE_COMMAND.

#### <a name="syntax"></a>Синтаксис

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
(в) Имя класса записи пользователя (команды).

*szCommand*<br/>
(в) Строка команды, которая будет использоваться для создания строки при использовании [CCommand.](../../data/oledb/ccommand-class.md)

#### <a name="remarks"></a>Remarks

Строка команды, которую вы указываете, будет использоваться в качестве по умолчанию, если вы не укажете текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) method.

Этот макрос принимает строки ANSI, если вы строите приложение как ANSI, или строки Unicode, если вы строите приложение как Unicode. Рекомендуется использовать [DEFINE_COMMAND_EX,](../../data/oledb/define-command-ex.md) а не DEFINE_COMMAND, поскольку первый принимает строки Unicode, независимо от типа приложения ANSI или Unicode.

#### <a name="example"></a>Пример

Смотрите [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="define_command_ex"></a><a name="define_command_ex"></a>DEFINE_COMMAND_EX

Осведряй команду, которая будет использоваться для создания строки при использовании класса [CCommand.](../../data/oledb/ccommand-class.md) Поддерживает приложения Unicode и ANSI.

#### <a name="syntax"></a>Синтаксис

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
(в) Имя класса записи пользователя (команды).

*wszCommand*<br/>
(в) Строка команды, которая будет использоваться для создания строки при использовании [CCommand.](../../data/oledb/ccommand-class.md)

#### <a name="remarks"></a>Remarks

Строка команды, которую вы указываете, будет использоваться в качестве по умолчанию, если вы не укажете текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) method.

Этот макрос принимает строки Unicode, независимо от типа приложения. Этот макрос предпочтительнее [DEFINE_COMMAND,](../../data/oledb/define-command.md) поскольку он поддерживает Unicode, а также приложения ANSI.

#### <a name="example"></a>Пример

Смотрите [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="begin_param_map"></a><a name="begin_param_map"></a>BEGIN_PARAM_MAP

Отметки начала записей параметра карты.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>Параметры

*x*<br/>
[входные данные] Имя класса записей пользователя.

#### <a name="remarks"></a>Remarks

Параметры используются [командами.](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Пример

См пример для [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) макроса.

### <a name="end_param_map"></a><a name="end_param_map"></a>END_PARAM_MAP

Отметки конца записей карты параметра.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>Пример

См пример для [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) макроса.

### <a name="set_param_type"></a><a name="set_param_type"></a>SET_PARAM_TYPE

Отославаю COLUMN_ENTRY макросы, которые соответствуют SET_PARAM_TYPE макровход, вывод или ввод/вывод.

#### <a name="syntax"></a>Синтаксис

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>Параметры

*тип*<br/>
[входные данные] Тип, задаваемый для параметра.

#### <a name="remarks"></a>Remarks

Поставщики поддерживают только входные и выходные типы параметров, поддерживаемые в базовом источнике данных. Тип представляет собой комбинацию `DBPARAMIO` одного или нескольких значений (см. [DBBINDING структуры](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справке программиста OLE DB):*

- `DBPARAMIO_NOTPARAM`Аксессуар не имеет параметров. Как правило, `eParamIO` вы устанавливаете это значение в строке аксессуаров, чтобы напомнить пользователю, что параметры игнорируются.

- `DBPARAMIO_INPUT`Параметр ввода.

- `DBPARAMIO_OUTPUT`Параметр вывода.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT`Параметр является как входиным, так и выходным параметром.

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

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[СПРАВКа о потребительских шаблонах OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
