---
title: Класс CCommand
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: 7db2d3d71deecda06e39772541658dfada72ae3b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415270"
---
# <a name="ccommand-class"></a>Класс CCommand

Предоставляет методы для задания и выполнения команды.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>Параметры

*TAccessor*<br/>
Тип метода доступа класса (такие как `CDynamicParameterAccessor`, `CDynamicStringAccessor`, или `CEnumeratorAccessor`) возникает необходимость команду, чтобы использовать. По умолчанию используется `CNoAccessor`, который указывает, что класс не поддерживает параметры или выходные столбцы.

*TRowset*<br/>
Тип класса набора строк (таких как `CArrayRowset` или `CNoRowset`) возникает необходимость команду, чтобы использовать. Значение по умолчанию — `CRowset`.

*Тип TMultiple*<br/>
Чтобы использовать команду OLE DB, может вернуть несколько результатов, укажите [CMultipleResults](../../data/oledb/cmultipleresults-class.md). В противном случае используйте [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Дополнительные сведения см. в разделе [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85)).

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Закрыть](#close)|Закрывает текущую команду.|
|[GetNextResult](#getnextresult)|Извлекает следующий результат, при использовании нескольких результирующих наборов.|
|[Открыть](#open)|Выполняет и при необходимости выполняет привязку команды.|

### <a name="inherited-methods"></a>Наследуемые методы

|||
|-|-|
|[Создание](#create)|Создает новую команду для указанного сеанса, а затем задает текст команды.|
|[CreateCommand](#createcommand)|Создает новую команду.|
|[GetParameterInfo](#getparameterinfo)|Получает список параметров команды, их имена и их типы.|
|[Подготовка](#prepare)|Проверяет и оптимизировать текущую команду.|
|[ReleaseCommand](#releasecommand)|Освобождает параметрическим при необходимости, а затем освобождает команды.|
|[SetParameterInfo](#setparameterinfo)|Указывает в собственный тип каждого параметра команды.|
|[Unprepare](#unprepare)|Отменяет план выполнения текущей команды.|

## <a name="remarks"></a>Примечания

Этот класс используется в том случае, если вам нужно выполнить операцию на основе параметров или для выполнения команды. Если необходимо просто открыть простого набора строк, используйте [CTable](../../data/oledb/ctable-class.md) вместо этого.

Класс доступа, который вы используете, определяет метод привязки параметров и данных.

Обратите внимание, что нельзя использовать хранимые процедуры с поставщиком OLE DB для Jet, так как этот поставщик не поддерживает хранимые процедуры, (только константы допускаются в строках запроса).

## <a name="close"></a> CCommand::Close

Освобождает метод доступа набора строк, связанный с данной командой.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Команда использует набор строк, метод доступа set результата и (необязательно) параметрическим (в отличие от таблиц, которые не поддерживают параметры и не обязательно параметрическим).

При выполнении команды, следует вызвать оба `Close` и [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) после команды.

Если вы хотите выполнить ту же команду повторно, каждый метод доступа set результат должен освободить, вызвав `Close` перед вызовом `Execute`. В конце ряда, метод доступа к параметру должен освободить путем вызова `ReleaseCommand`. Другим распространенным сценарием вызов хранимой процедуры с выходными параметрами. На многих поставщиков (например, поставщик OLE DB для SQL Server) значения выходных параметров не будут доступны до выхода из метода доступа set результат. Вызовите `Close` закрыть возвращенного набора строк и метод доступа set результат, но не параметр метода доступа, позволяя получить значения выходных параметров.

### <a name="example"></a>Пример

В следующем примере показано, как можно вызвать `Close` и `ReleaseCommand` при выполнении той же команды несколько раз.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="getnextresult"></a> CCommand::GetNextResult

Извлекает следующий результирующий набор, если таковой доступен.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Параметры

*pulRowsAffected*<br/>
[входные/выходные данные] Указатель на область памяти, где возвращается число строк, затронутых командой.

*bBind*<br/>
[in] Указывает, нужно ли привязывать команда автоматически после выполнения. По умолчанию используется **true**, который вызывает команду, чтобы автоматически привязать. Установка *bBind* для **false** предотвращает автоматическая привязка команды, можно привязать вручную. (Привязке вручную является особый интерес для пользователей OLAP).

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Если результирующий набор предварительно извлечь, эта функция освобождает предыдущий результирующий набор и отменяет привязку столбцов по. Если *bBind* — **true**, он выполняет привязку новые столбцы.

Эту функцию следует вызывать только в том случае, если вы указали несколько результатов, задав `CCommand` параметр шаблона *тип TMultiple*=`CMultipleResults`.

## <a name="open"></a> CCommand::Open

Выполняет и при необходимости выполняет привязку команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Параметры

*Сеанс*<br/>
[in] Сеанс, в котором выполняется команда.

*wszCommand*<br/>
[in] Команда для выполнения, передается как строка Юникода. Может иметь значение NULL, при использовании `CAccessor`, в этом случае команда будет извлекаться из значение, передаваемое [DEFINE_COMMAND](../../data/oledb/define-command.md) макрос. См. в разделе [ICommand::Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) в *Справочник программиста OLE DB по* подробные сведения.

*szCommand*<br/>
[in] Совпадение с кодом *wszCommand* за исключением того, что этот параметр принимает командной строки ANSI. Четвертый виде этот метод может принимать значение NULL. См. в разделе «Примечания» далее в этом разделе сведения.

*pPropSet*<br/>
[in] Указатель на массив [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) структур, содержащих свойства и значения, которые можно установить. См. в разделе [наборов свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справочнике программиста OLE DB* в Windows SDK.

*pRowsAffected*<br/>
[входные/выходные данные] Указатель на область памяти, где возвращается число строк, затронутых командой. Если  *\*pRowsAffected* имеет значение NULL, счетчик строк не возвращается. В противном случае `Open` задает  *\*pRowsAffected* на следующих условиях:

|If|Следующее действие|
|--------|----------|
|`cParamSets` Элемент `pParams` больше, чем 1|*\*pRowsAffected* представляет общее число строк, затронутых всеми наборов параметров, указанных в этом выполнении.|
|Число затронутых строк недоступен|*\*pRowsAffected* устанавливается равным -1.|
|Команда не обновления, удаления или вставки строк|*\*pRowsAffected* не определено.|

*guidCommand*<br/>
[in] GUID, который определяет синтаксис и общие правила для поставщика, используемого при анализе текста команды. См. в разделе [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) и [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) в *Справочник программиста OLE DB по* подробные сведения.

*bBind*<br/>
[in] Указывает, нужно ли привязывать команда автоматически после выполнения. По умолчанию используется **true**, который вызывает команду, чтобы автоматически привязать. Установка *bBind* для **false** предотвращает автоматическая привязка команды, можно привязать вручную. (Привязке вручную является особый интерес для пользователей OLAP).

*ulPropSets*<br/>
[in] Число [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) структуры, передаются в *pPropSet* аргумент.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Первые три вида `Open` занять сеанс, создать команду и выполните команду, привязки параметров при необходимости.

В первой форме `Open` принимает строку команды Юникода и нет значения по умолчанию.

Вторая форма `Open` принимает командной строки ANSI и без значения по умолчанию (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).

Третья форма из `Open` позволяет принимать значение NULL, из-за типа строку команды **int** со значением по умолчанию NULL. Он предоставляется для вызова `Open(session, NULL);` или `Open(session);` так как имеет значение NULL тип **int**. Эта версия требуется и проверяется, **int** параметр иметь значение NULL.

Используйте четвертый форму `Open` при создании команды и необходимо выполнить один [Подготовка](../../data/oledb/ccommand-prepare.md) и несколько выполнений.

> [!NOTE]
>  `Open` вызовы `Execute`, который в свою очередь вызывает `GetNextResult`.

## <a name="create"></a> CCommand::Create

Вызовы [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) для создания команды для указанного сеанса, затем вызывает [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) для задания текста команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>Параметры

*Сеанс*<br/>
[in] Сеанс, для которых можно создать команду.

*wszCommand*<br/>
[in] Указатель на текст в Юникоде командной строки.

*szCommand*<br/>
[in] Указатель на текст ANSI командной строки.

*guidCommand*<br/>
[in] GUID, который определяет синтаксис и общие правила для поставщика, используемого при анализе текста команды. Описание диалекты, см. в разделе [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) в *Справочник программиста OLE DB по*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

В первой форме `Create` принимает строку команды Юникода. Вторая форма `Create` принимает командной строки ANSI (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).

## <a name="createcommand"></a> CCommand::CreateCommand

Создает новую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Параметры

*Сеанс*<br/>
[in] Объект `CSession` объекта, связываемого с новой команды.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает команду с помощью объекта указанного сеанса.

## <a name="getparameterinfo"></a> CCommand::GetParameterInfo

Получает список параметров команды, их имена и их типы.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandWithParameters::GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="prepare"></a> CCommand::Prepare

Проверяет и оптимизировать текущую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Параметры

*cExpectedRuns*<br/>
[in] Сколько раз вы планируете выполнить команду.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода OLE DB [ICommandPrepare::Prepare](/previous-versions/windows/desktop/ms718370(v=vs.85)).

## <a name="releasecommand"></a> CCommand::ReleaseCommand

Освобождает метод доступа к параметру, а затем освобождает в саму команду.

### <a name="syntax"></a>Синтаксис

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Примечания

`ReleaseCommand` используется в сочетании с `Close`. См. в разделе [закрыть](../../data/oledb/ccommand-close.md) сведения об использовании.

## <a name="setparameterinfo"></a> CCommand::SetParameterInfo

Указывает в собственный тип каждого параметра команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandWithParameters::SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="unprepare"></a> CCommand::Unprepare

Отменяет план выполнения текущей команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод создает оболочку для метода OLE DB [ICommandPrepare::Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85)).

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)