---
title: Класс CDataConnection
ms.date: 03/27/2019
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
ms.openlocfilehash: fe954e218a099fa7956748904a4baa89f741c52f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368616"
---
# <a name="cdataconnection-class"></a>Класс CDataConnection

Управляет соединением с источником данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CDataConnection
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CDataConnection](#cdataconnection)|Конструктор. Мгновения и инициализации `CDataConnection` объекта.|
|[Копирование](#copy)|Создает копию существующего соединения данных.|
|[Открыть](#open)|Открывает подключение к источнику данных с помощью строки инициализации.|
|[OpenNewSession](#opennewsession)|Открывает новый сеанс в текущем подключении.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор BOOL](#op_bool)|Определяет, является ли текущая сессия открытой или нет.|
|[оператор bool](#op_bool_ole)|Определяет, является ли текущая сессия открытой или нет.|
|[оператор CDataИсточник&](#op_cdata_amp)|Возвращает ссылку на `CDataSource` содержащийся объект.|
|[оператор CDataSource](#op_cdata_star)|Возвращает указатель на `CDataSource` содержащийся объект.|
|[оператор CSession&](#op_csession_amp)|Возвращает ссылку на `CSession` содержащийся объект.|
|[оператор CSession*](#op_csession_star)|Возвращает указатель на `CSession` содержащийся объект.|

## <a name="remarks"></a>Remarks

`CDataConnection`является полезным классом для создания клиентов, поскольку он инкапсулирует необходимые объекты (источник данных и сеанс) и некоторые работы, которые необходимо сделать при подключении к источнику данных

`CDataConnection`Без, вы должны `CDataSource` создать объект, вызвать его [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) метод, а затем создать экземпляр объекта [CSession,](../../data/oledb/csession-class.md) вызов `Open`его [Открытый](../../data/oledb/csession-open.md) метод, а затем создать объект [CCommand](../../data/oledb/ccommand-class.md) и вызвать его методы.

С `CDataConnection`помощью , вам нужно только создать объект соединения, передать его строку инициализации, а затем использовать это соединение для открытых команд. Если вы планируете использовать подключение к базе данных неоднократно, это хорошая идея, чтобы сохранить соединение открытым, и `CDataConnection` обеспечивает удобный способ сделать это.

> [!NOTE]
> Если вы создаете приложение базы данных, которое должно обрабатывать несколько сеансов, вам нужно будет использовать [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>CDataConnection::CDataConnection

Мгновения и инициализации `CDataConnection` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Параметры

*Ds*<br/>
(в) Ссылка на существующее соединение данных.

### <a name="remarks"></a>Remarks

Первый переопределение создает `CDataConnection` новый объект с настройками по умолчанию.

Второй переопределение создает `CDataConnection` новый объект с настройками, эквивалентными указанному объекту подключения данных.

## <a name="cdataconnectioncopy"></a><a name="copy"></a>CDataConnection::Copy

Создает копию существующего соединения данных.

### <a name="syntax"></a>Синтаксис

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Параметры

*Ds*<br/>
(в) Ссылка на существующее подключение к данным для копирования.

## <a name="cdataconnectionopen"></a><a name="open"></a>CDataConnection::Открыто

Открывает подключение к источнику данных с помощью строки инициализации.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Параметры

*szInitString*<br/>
(в) Строка инициализации для источника данных.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>CDataConnection:OpenNewSession

Открывает новый сеанс с использованием источника данных объекта текущего соединения.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>Параметры

*Сессии*<br/>
(в/аут) Ссылка на новый объект сеанса.

### <a name="remarks"></a>Remarks

Новая сессия использует объект текущего объекта соединения, содержащийся в источнике данных, в качестве его родительского, и может получить доступ ко всей той же информации, что и источник данных.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>CDataConnection::оператор BOOL

Определяет, является ли текущая сессия открытой или нет.

### <a name="syntax"></a>Синтаксис

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Remarks

Возвращает значение **BOOL** (MFC typedef). **TRUE** означает, что текущая сессия открыта; **FALSE** означает, что текущая сессия закрыта.

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>CDataConnection:Оператор бул (OLE DB)

Определяет, является ли текущая сессия открытой или нет.

### <a name="syntax"></a>Синтаксис

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Remarks

Возвращает значение **bool** (тип данных СЗ). **действительно** означает, что текущая сессия открыта; **ложные** средства, что текущая сессия закрыта.

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>CDataConnection::оператор CDataSource&amp;

Возвращает ссылку на `CDataSource` содержащийся объект.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает ссылку `CDataSource` на содержащийся объект, что позволяет пройти объект, `CDataConnection` где ссылка `CDataSource` ожидается.

### <a name="example"></a>Пример

Если у вас есть `func` функция (например, ниже), которая принимает ссылку, `CDataSource` вы можете использовать `CDataSource&` для передачи `CDataConnection` объекта вместо.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>CDataConnection:оператор CDataSource

Возвращает указатель на `CDataSource` содержащийся объект.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает указатель `CDataSource` на содержащийся объект, `CDataConnection` что `CDataSource` позволяет пройти объект, где указатель ожидается.

Примером использования [оператора CDataSource&.](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>CDataConnection::оператор CSession&amp;

Возвращает ссылку на `CSession` содержащийся объект.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает ссылку `CSession` на содержащийся объект, что позволяет пройти объект, `CDataConnection` где ссылка `CSession` ожидается.

### <a name="example"></a>Пример

Если у вас есть `func` функция (например, ниже), которая принимает ссылку, `CSession` вы можете использовать `CSession&` для передачи `CDataConnection` объекта вместо.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>CDataConnection::оператор CSession

Возвращает указатель на `CSession` содержащийся объект.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает указатель `CSession` на содержащийся объект, `CDataConnection` что `CSession` позволяет пройти объект, где указатель ожидается.

### <a name="example"></a>Пример

Пример [оператора CSession&.](../../data/oledb/cdataconnection-operator-csession-amp.md)

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[СПРАВКа о потребительских шаблонах OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
