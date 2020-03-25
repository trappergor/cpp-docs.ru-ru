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
ms.openlocfilehash: 385445081f84f65ff7030466a238a5a96abd63be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212071"
---
# <a name="cdataconnection-class"></a>Класс CDataConnection

Управляет соединением с источником данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CDataConnection
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[CDataConnection](#cdataconnection)|Конструктор. Создает и инициализирует объект `CDataConnection`.|
|[Copy](#copy).|Создает копию существующего подключения к данным.|
|[Открыть](#open)|Открывает соединение с источником данных, используя строку инициализации.|
|[опенневсессион](#opennewsession)|Открывает новый сеанс в текущем соединении.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[BOOL, оператор](#op_bool)|Определяет, открыт ли текущий сеанс.|
|[operator bool](#op_bool_ole)|Определяет, открыт ли текущий сеанс.|
|[Оператор CDataSource &](#op_cdata_amp)|Возвращает ссылку на содержащийся объект `CDataSource`.|
|[operator CDataSource *](#op_cdata_star)|Возвращает указатель на содержащийся объект `CDataSource`.|
|[Оператор CSession &](#op_csession_amp)|Возвращает ссылку на содержащийся объект `CSession`.|
|[operator CSession *](#op_csession_star)|Возвращает указатель на содержащийся объект `CSession`.|

## <a name="remarks"></a>Remarks

`CDataConnection` — это полезный класс для создания клиентов, поскольку он инкапсулирует необходимые объекты (источник данных и сеанс) и часть работы, которую необходимо выполнить при подключении к источнику данных.

Без `CDataConnection`необходимо создать объект `CDataSource`, вызвать его метод [опенфроминитиализатионстринг](../../data/oledb/cdatasource-openfrominitializationstring.md) , затем создать экземпляр объекта [CSession](../../data/oledb/csession-class.md) , вызвать его метод [Open](../../data/oledb/csession-open.md) , а затем создать объект [CCommand](../../data/oledb/ccommand-class.md) и вызвать его методы `Open`*.

В `CDataConnection`необходимо создать объект соединения, передать ему строку инициализации, а затем использовать это соединение для открытия команд. Если вы планируете многократное использование подключения к базе данных, рекомендуется оставаться открытым и `CDataConnection` предоставляет удобный способ для этого подключения.

> [!NOTE]
>  Если вы создаете приложение базы данных, которое должно работать с несколькими сеансами, необходимо использовать [опенневсессион](../../data/oledb/cdataconnection-opennewsession.md).

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>CDataConnection:: CDataConnection

Создает и инициализирует объект `CDataConnection`.

### <a name="syntax"></a>Синтаксис

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Параметры

*DS*<br/>
окне Ссылка на существующее подключение к данным.

### <a name="remarks"></a>Remarks

Первое переопределение создает новый объект `CDataConnection` с параметрами по умолчанию.

Второе переопределение создает новый объект `CDataConnection` с параметрами, эквивалентными указанному объекту подключения к данным.

## <a name="cdataconnectioncopy"></a><a name="copy"></a>CDataConnection:: Copy

Создает копию существующего подключения к данным.

### <a name="syntax"></a>Синтаксис

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Параметры

*DS*<br/>
окне Ссылка на существующее подключение к данным для копирования.

## <a name="cdataconnectionopen"></a><a name="open"></a>CDataConnection:: Open

Открывает соединение с источником данных, используя строку инициализации.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Параметры

*сзинитстринг*<br/>
окне Строка инициализации для источника данных.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>CDataConnection:: Опенневсессион

Открывает новый сеанс, используя источник данных текущего объекта соединения.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>Параметры

*сессии*<br/>
[вход/выход] Ссылка на новый объект Session.

### <a name="remarks"></a>Remarks

В новом сеансе в качестве родительского объекта используется объект источника данных текущего соединения, который может получить доступ ко всем тем же данным, что и источник данных.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>CDataConnection:: operator BOOL

Определяет, открыт ли текущий сеанс.

### <a name="syntax"></a>Синтаксис

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Remarks

Возвращает **логическое** значение (MFC typedef). **Значение true** означает, что текущий сеанс открыт; **Значение false** означает, что текущий сеанс закрыт.

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>CDataConnection:: operator bool (OLE DB)

Определяет, открыт ли текущий сеанс.

### <a name="syntax"></a>Синтаксис

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Remarks

Возвращает **логическое** значение (C++ тип данных). **значение true** означает, что текущий сеанс открыт; **значение false** означает, что текущий сеанс закрыт.

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>CDataConnection:: operator CDataSource&amp;

Возвращает ссылку на содержащийся объект `CDataSource`.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает ссылку на объект, содержащийся `CDataSource`, что позволяет передать объект `CDataConnection`, где ожидается `CDataSource` ссылка.

### <a name="example"></a>Пример

Если у вас есть функция (например, `func` ниже), которая принимает `CDataSource` ссылку, можно использовать `CDataSource&` для передачи объекта `CDataConnection`.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>CDataConnection:: operator CDataSource *

Возвращает указатель на содержащийся объект `CDataSource`.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает указатель на содержащийся объект `CDataSource`, что позволяет передать объект `CDataConnection`, где ожидается указатель `CDataSource`.

Пример использования см. в разделе [operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) .

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>CDataConnection:: operator CSession&amp;

Возвращает ссылку на содержащийся объект `CSession`.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает ссылку на объект, содержащийся `CSession`, что позволяет передать объект `CDataConnection`, где ожидается `CSession` ссылка.

### <a name="example"></a>Пример

Если у вас есть функция (например, `func` ниже), которая принимает `CSession` ссылку, можно использовать `CSession&` для передачи объекта `CDataConnection`.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>CDataConnection:: operator CSession *

Возвращает указатель на содержащийся объект `CSession`.

### <a name="syntax"></a>Синтаксис

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Remarks

Этот оператор возвращает указатель на содержащийся объект `CSession`, что позволяет передать объект `CDataConnection`, где ожидается указатель `CSession`.

### <a name="example"></a>Пример

Пример использования см. в разделе [operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) .

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
