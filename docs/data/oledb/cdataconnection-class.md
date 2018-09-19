---
title: Класс CDataConnection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b3786a131015ac71a5b96afa3acd8d4bb4a8008
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029979"
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
|[CDataConnection](#cdataconnection)|Конструктор. Создает и инициализирует `CDataConnection` объекта.|  
|[Копировать](#copy)|Создает копию существующего соединения данных.|  
|[Открыть](#open)|Открывает подключение к источнику данных с помощью строки инициализации.|  
|[OpenNewSession](#opennewsession)|Открывает новый сеанс для текущего соединения.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[Operator BOOL](#op_bool)|Определяет, является ли текущий сеанс открытым.|  
|[operator bool](#op_bool_ole)|Определяет, является ли текущий сеанс открытым.|  
|[оператор CDataSource &](#op_cdata_amp)|Возвращает ссылку на вложенный `CDataSource` объекта.|  
|[оператор CDataSource *](#op_cdata_star)|Возвращает указатель на вложенный `CDataSource` объекта.|  
|[оператор CSession &](#op_csession_amp)|Возвращает ссылку на вложенный `CSession` объекта.|  
|[оператор CSession *](#op_csession_star)|Возвращает указатель на вложенный `CSession` объекта.|  
  
## <a name="remarks"></a>Примечания  

`CDataConnection` Класс особенно полезен для создания клиентов, так как он инкапсулирует необходимых объектов (источника данных и сеанса) и некоторых операций, которые необходимо выполнить при подключении к источнику данных  
  
Без `CDataConnection`, то необходимо создать `CDataSource` , вызовите его [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) метод, создайте экземпляр [CSession](../../data/oledb/csession-class.md) , вызовите его [ Откройте](../../data/oledb/csession-open.md) метод, создайте [CCommand](../../data/oledb/ccommand-class.md) и вызовите его `Open`* методы.  
  
С помощью `CDataConnection`, необходимо только создать объект подключения, передайте его в строку инициализации, а затем использовать это подключение, чтобы открыть команды. Если планируется повторно использовать подключение к базе данных, рекомендуется не закрывайте подключение, и `CDataConnection` предоставляет удобный способ сделать это.  
  
> [!NOTE]
>  Если вы создаете приложение базы данных, который должен обрабатывать несколько сеансов, необходимо использовать [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  

## <a name="#cdataconnection"></a> CDataConnection::CDataConnection

Создает и инициализирует `CDataConnection` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CDataConnection();   
CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>Параметры  

*доменных служб Active Directory*<br/>
[in] Ссылка на существующее подключение к данным.  
  
### <a name="remarks"></a>Примечания  

Первое переопределение создает новую `CDataConnection` с параметрами по умолчанию.  
  
Второе переопределение создает новую `CDataConnection` с параметрами, эквивалентно вами объект подключения к данным. 

## <a name="#copy"></a> CDataConnection::Copy

Создает копию существующего соединения данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*доменных служб Active Directory*<br/>
[in] Ссылка на существующее подключение к данным для копирования. 

## <a name="#open"></a> CDataConnection::Open

Открывает подключение к источнику данных с помощью строки инициализации.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(LPCOLESTR szInitString) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*szInitString*<br/>
[in] Строка инициализации источника данных.  
  
### <a name="return-value"></a>Возвращаемое значение  

Стандартный HRESULT.  

## <a name="#opennewsession"></a> CDataConnection::OpenNewSession

Открывает новый сеанс с использованием источника данных текущего объекта соединения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
```  
  
#### <a name="parameters"></a>Параметры  

*Сеанс*<br/>
[входные/выходные данные] Ссылка на объект нового сеанса.  
  
### <a name="remarks"></a>Примечания  

Новый сеанс использует в качестве родительского объекта источника данных, содержащихся текущего объекта соединения и доступны все те же сведения, что источник данных.  
  
### <a name="return-value"></a>Возвращаемое значение  

Стандартный HRESULT.  

## <a name="op_bool"></a> CDataConnection::operator BOOL

Определяет, является ли текущий сеанс открытым.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator BOOL() throw();  
```  
  
### <a name="remarks"></a>Примечания  

Возвращает **BOOL** (MFC typedef) значение. **Значение TRUE,** означает, что текущий сеанс открыт; **FALSE** означает, что текущий сеанс будет закрыт. 

## <a name="op_bool_ole"></a> CDataConnection::operator bool (OLE DB)

Определяет, является ли текущий сеанс открытым.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator bool() throw();  
```  
  
### <a name="remarks"></a>Примечания  

Возвращает **bool** значение (тип данных C++). **значение true,** означает, что текущий сеанс открыт; **false** означает, что текущий сеанс будет закрыт.  

## <a name="op_cdata_amp"></a> CDataConnection::operator CDataSource&amp;

Возвращает ссылку на вложенный `CDataSource` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CDataSource&() throw();  
```  
  
### <a name="remarks"></a>Примечания  

Этот оператор возвращает ссылку на содержащиеся в нем `CDataSource` объекта, позволяя передавать `CDataConnection` объекта где `CDataSource` ожидается ссылка на.  
  
### <a name="example"></a>Пример  

Если у вас есть функции (такие как `func` ниже), принимающий `CDataSource` ссылки, можно использовать `CDataSource&` для передачи `CDataConnection` вместо этого.  
  
[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)] 

## <a name="op_cdata_star"></a> CDataConnection::operator CDataSource *

Возвращает указатель на вложенный `CDataSource` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CDataSource*() throw();  
```  
  
### <a name="remarks"></a>Примечания  

Этот оператор возвращает указатель на вложенный `CDataSource` объекта, позволяя передавать `CDataConnection` объекта где `CDataSource` требуется указатель.  
  
См. в разделе [оператор CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) пример использования.  

## <a name="op_csession_amp"></a> CDataConnection::operator CSession&amp;

Возвращает ссылку на вложенный `CSession` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CSession&();  
```  
  
### <a name="remarks"></a>Примечания  

Этот оператор возвращает ссылку на содержащиеся в нем `CSession` объекта, позволяя передавать `CDataConnection` объекта где `CSession` ожидается ссылка на.  
  
### <a name="example"></a>Пример  

Если у вас есть функции (такие как `func` ниже), принимающий `CSession` ссылки, можно использовать `CSession&` для передачи `CDataConnection` вместо этого.  
  
[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  

## <a name="op_csession_star"></a> CDataConnection::operator CSession *

Возвращает указатель на вложенный `CSession` объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CSession*() throw();  
```  
  
### <a name="remarks"></a>Примечания  

Этот оператор возвращает указатель на вложенный `CSession` объекта, позволяя передавать `CDataConnection` объекта где `CSession` требуется указатель.  
  
### <a name="example"></a>Пример  

См. в разделе [оператор CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) пример использования.  
  
## <a name="see-also"></a>См. также  

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)