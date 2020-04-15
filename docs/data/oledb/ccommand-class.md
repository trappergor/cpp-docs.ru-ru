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
ms.openlocfilehash: 52c7e2ce5acdd2df33e2a6422535a337f0a43aec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368630"
---
# <a name="ccommand-class"></a>Класс CCommand

Предоставляет методы настройки и выполнения команды.

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
Тип класса доступа `CDynamicParameterAccessor`(например, `CDynamicStringAccessor`, `CEnumeratorAccessor`или), который вы хотите использовать команду. По умолчанию, `CNoAccessor`который указывает, что класс не поддерживает параметры или выходные столбцы.

*Троусет*<br/>
Тип класса строк `CArrayRowset` (например, `CNoRowset`или), который требуется использовать команде. Значение по умолчанию — `CRowset`.

*TMultiple*<br/>
Чтобы использовать команду OLE DB, которая может вернуть несколько результатов, укажите [CMultipleResults.](../../data/oledb/cmultipleresults-class.md) В противном случае используйте [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md). Для получения подробной информации [см.](/previous-versions/windows/desktop/ms721289(v=vs.85))

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Закрыть](#close)|Закрывает текущую команду.|
|[GetNextResult](#getnextresult)|Получает следующий результат при использовании нескольких наборов результатов.|
|[Открыть](#open)|Выполняет и дополнительно связывает команду.|

### <a name="inherited-methods"></a>Наследуемые методы

|||
|-|-|
|[Создать](#create)|Создает новую команду для указанного сеанса, а затем устанавливает текст команды.|
|[CreateCommand](#createcommand)|Создает новую команду.|
|[GetParameterInfo](#getparameterinfo)|Получает список параметров команды, их имен и типов.|
|[Подготовить](#prepare)|Проверяет и оптимизирует текущую команду.|
|[ОсвобождениеКоманда](#releasecommand)|При необходимости выпускает параметр-доступ, а затем выпускает команду.|
|[SetParameterInfo](#setparameterinfo)|Определяет родной тип каждого параметра команды.|
|[Неподготовитесь](#unprepare)|Отбрасывает текущий план выполнения команд.|

## <a name="remarks"></a>Remarks

Используйте этот класс, когда вам нужно выполнить операцию на основе параметров или выполнить команду. Если вам просто нужно открыть простой набор строк, используйте [CTable](../../data/oledb/ctable-class.md) вместо этого.

Используемый класс аксессуаров определяет метод связывания параметров и данных.

Обратите внимание, что вы не можете использовать сохраненные процедуры с поставщиком OLE DB для Jet, потому что этот поставщик не поддерживает сохраненные процедуры (в строках запроса разрешены только константы).

## <a name="ccommandclose"></a><a name="close"></a>CCommand::Закрыть

Выпускает набор строк доступа, связанный с командой.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

### <a name="remarks"></a>Remarks

Команда использует набор строк, доступ к набору результатов и (по желанию) параметр-аксессуар (в отличие от таблиц, которые не поддерживают параметры и не нуждаются в доступе параметра).

При выполнении команды следует вызвать и `Close` , и [releaseCommand](../../data/oledb/ccommand-releasecommand.md) после команды.

Если вы хотите выполнить одну и ту же команду неоднократно, вы должны освободить каждый набор результатов, позвонив `Close` перед вызовом. `Execute` В конце серии вы должны выпустить параметр `ReleaseCommand`аксессуара, позвонив . Другим распространенным сценарием является вызов сохраненной процедуры, которая имеет параметры вывода. Во многих провайдерах (например, поставщике OLE DB для Сервера S'L) значения параметра вывода не будут доступны до тех пор, пока вы не закроете доступ к набору результатов. Вызов, `Close` чтобы закрыть возвращенный набор строк и набор результатов accessor, но не параметр accessor, что позволяет получить значения параметра вывода.

### <a name="example"></a>Пример

В следующем примере показано, как можно вызывать `Close` и `ReleaseCommand` при повторном выполнении одной и той же команды.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="ccommandgetnextresult"></a><a name="getnextresult"></a>CCommand::GetNextResult

Получает следующий набор результатов, если он доступен.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>Параметры

*pulRowsAffected*<br/>
(в/аут) Указатель на память, где возвращается количество строк, затронутых командой.

*bBind*<br/>
(в) Определяет, следует ли связывать команду автоматически после выполнения. По умолчанию **это правда,** что приводит к тому, что команда будет связана автоматически. Установка *bBind* на **ложную** предотвращает автоматическое переплевание команды, так что вы можете связать вручную. (Ручная привязка представляет особый интерес для пользователей OLAP.)

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Если набор результатов был ранее извлечен, эта функция выпускает предыдущий набор результатов и отсваляет столбцы. Если *bBind* **истинен,** он связывает новые столбцы.

Эту функцию следует называть только в том `CCommand` случае, если вы указали несколько результатов, установив параметр шаблона *TMultiple.*=`CMultipleResults`

## <a name="ccommandopen"></a><a name="open"></a>CCommand::Открыто

Выполняет и дополнительно связывает команду.

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

*Сессии*<br/>
(в) Сеанс, в котором выполняется команда.

*wszCommand*<br/>
(в) Команда для выполнения, передается как строка Unicode. Может быть NULL `CAccessor`при использовании, и в этом случае команда будет извлечена из значения, передаваемого [DEFINE_COMMAND](../../data/oledb/define-command.md) макросу. Смотрите [ICommand::Выполните](/previous-versions/windows/desktop/ms718095(v=vs.85)) в *справке программиста OLE DB* для получения подробной информации.

*szCommand*<br/>
(в) То же самое, что *wszCommand,* за исключением того, что этот параметр принимает строку команды ANSI. Четвертая форма этого метода может иметь значение NULL. Подробнее об этом читайте в материале «Замечания» позже.

*pPropSet*<br/>
(в) Указатель на массив структур [DBPROPSET,](/previous-versions/windows/desktop/ms714367(v=vs.85)) содержащих свойства и значения, которые должны быть установлены. Смотрите [наборы свойств и группы свойств](/previous-versions/windows/desktop/ms713696(v=vs.85)) в *справке программиста OLE DB* в SDK Windows.

*pRowsAffected*<br/>
(в/аут) Указатель на память, где возвращается количество строк, затронутых командой. Если * \*pRowsAffected* является NULL, количество строк не возвращается. В `Open` противном случае, устанавливает * \*pRowsAffected* в соответствии со следующими условиями:

|Если|То|
|--------|----------|
|Элемент `cParamSets` `pParams` больше, чем 1|pRowsAffected представляет общее количество строк, затронутых всеми параметрами, указанными в исполнении. * \**|
|Количество затронутых строк недоступно|pRowsAffected установлен до -1. * \**|
|Команда не обновляет, не удаляет и не вставляет строки|pRowsAffected не определено. * \**|

*guidCommand*<br/>
(в) GUID, который определяет синтаксис и общие правила для поставщика для использования в разборе текста команды. Смотрите [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) и [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) в *справке программиста OLE DB* для получения подробной информации.

*bBind*<br/>
(в) Определяет, следует ли связывать команду автоматически после выполнения. По умолчанию **это правда,** что приводит к тому, что команда будет связана автоматически. Установка *bBind* на **ложную** предотвращает автоматическое переплевание команды, так что вы можете связать вручную. (Ручная привязка представляет особый интерес для пользователей OLAP.)

*ulPropSets*<br/>
(в) Количество структур [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) прошло в споре *pPropSet.*

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Первые три формы `Open` сессии, создать команду и выполнить команду, связывая любые параметры по мере необходимости.

Первая форма `Open` принимает строку команды Unicode и не имеет значения по умолчанию.

Вторая форма `Open` использует строку команды ANSI и не имеет значения по умолчанию (при условии обратной совместимости с существующими приложениями ANSI).

Третья форма `Open` позволяет строке команды быть NULL, из-за ввода **Int** со значением null по умолчанию. Это предусмотрено `Open(session, NULL);` для `Open(session);` вызова или потому, что NULL имеет тип **Int**. Эта версия требует и утверждает, что параметр **int** является NULL.

Используйте четвертую `Open` форму, когда вы уже создали команду, и вы хотите выполнить одну [подготовку](../../data/oledb/ccommand-prepare.md) и несколько выполнения.

> [!NOTE]
> `Open`вызовов, `Execute`которые, `GetNextResult`в свою очередь, вызывает .

## <a name="ccommandcreate"></a><a name="create"></a>CCommand::Создание

Вызывает [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) для создания команды для указанного сеанса, а затем вызывает [ICommandText::SetCommandText,](/previous-versions/windows/desktop/ms709825(v=vs.85)) чтобы указать текст команды.

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

*Сессии*<br/>
(в) Сеанс, на котором можно создать команду.

*wszCommand*<br/>
(в) Указатель на текст Unicode строки команды.

*szCommand*<br/>
(в) Указатель на текст строки команды ANSI.

*guidCommand*<br/>
(в) GUID, который определяет синтаксис и общие правила для поставщика для использования в разборе текста команды. Для описания диалектов, [см. ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) в *справке программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Первая форма `Create` принимает строку команды Unicode. Вторая форма `Create` использует строку команды ANSI (предоставляется для обратной совместимости с существующими приложениями ANSI).

## <a name="ccommandcreatecommand"></a><a name="createcommand"></a>CCommand::CreateCommand

Создает новую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>Параметры

*Сессии*<br/>
(в) Объект, `CSession` связанный с новой командой.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Этот метод создает команду с помощью указанного объекта сеанса.

## <a name="ccommandgetparameterinfo"></a><a name="getparameterinfo"></a>CCommand::GetParameterInfo

Получает список параметров команды, их имен и типов.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>Параметры

Смотрите [ICommandWith Параметры::GetParameterInfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) в *справке программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="ccommandprepare"></a><a name="prepare"></a>CCommand::Pрефарере

Проверяет и оптимизирует текущую команду.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>Параметры

*cExpectedRuns*<br/>
(в) Количество раз, в течение чем вы ожидаете выполнить команду.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Этот метод обертывает метод OLE DB [ICommandPrepare::Prepare](/previous-versions/windows/desktop/ms718370(v=vs.85)).

## <a name="ccommandreleasecommand"></a><a name="releasecommand"></a>CCommand::ReleaseCommand

Выпускает параметр-доступ, а затем выпускает саму команду.

### <a name="syntax"></a>Синтаксис

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>Remarks

`ReleaseCommand`используется в сочетании с `Close`. Смотрите [Close](../../data/oledb/ccommand-close.md) для сведения об использовании.

## <a name="ccommandsetparameterinfo"></a><a name="setparameterinfo"></a>CCommand::SetParameterInfo

Определяет родной тип каждого параметра команды.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>Параметры

Смотрите [ICommandWith Параметры::SetParameterInfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) в *справке программиста OLE DB*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

## <a name="ccommandunprepare"></a><a name="unprepare"></a>CCommand::Неподготовка

Отбрасывает текущий план выполнения команд.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Этот метод обертывает метод OLE DB [ICommandPrepare::Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85)).

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[СПРАВКа о потребительских шаблонах OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
