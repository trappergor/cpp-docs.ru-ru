---
title: Класс CDataSource
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: f52b5b4313f8c9703a578f7d0d3ed672555f647e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646125"
---
# <a name="cdatasource-class"></a>Класс CDataSource

Соответствующий объект источника данных OLE DB, который представляет подключение через поставщика к источнику данных.

## <a name="syntax"></a>Синтаксис

```cpp
class CDataSource
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Закрыть](#close)|Закрывает соединение.|
|[GetInitializationString](#getinitializationstring)|Извлекает строку инициализации источника данных, который в данный момент открыт.|
|[GetProperties](#getproperties)|Возвращает значения свойств, заданных в настоящее время для подключенного источника данных.|
|[GetProperty](#getproperty)|Получает значение определенного свойства в настоящий момент настроен подключенного источника данных.|
|[Открыть](#open)|Создает подключение к поставщику (источник данных) с помощью `CLSID`, `ProgID`, или `CEnumerator` моникера, предоставленный вызывающим объектом.|
|[OpenFromFileName](#openfromfilename)|Открывает источник данных из файла, указанного пользователем по имени.|
|[OpenFromInitializationString](#openfrominitializationstring)|Открывает источник данных, заданный строкой в инициализации.|
|[OpenWithPromptFileName](#openwithpromptfilename)|Позволяет пользователю выбрать ранее созданный файл связи для открытия соответствующего источника данных.|
|[OpenWithServiceComponents](#openwithservicecomponents)|Открывает объект источника данных, с помощью диалогового окна Data Link.|

## <a name="remarks"></a>Примечания

Один или несколько сеансов базы данных могут создаваться для одного подключения. Эти сеансы, представляются `CSession`. Необходимо вызвать [CDataSource::Open](../../data/oledb/cdatasource-open.md) для открытия подключения перед созданием сеанса с `CSession::Open`.

Пример использования `CDataSource`, см. в разделе ["CatDB"](../../visual-cpp-samples.md) образца.

## <a name="close"></a> CDataSource::Close

Закрывает соединение, выпустив `m_spInit` указатель.

### <a name="syntax"></a>Синтаксис

```cpp
void Close() throw();
```

## <a name="getinitializationstring"></a> CDataSource::GetInitializationString

Извлекает строку инициализации источника данных, который в данный момент открыт.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString, 
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>Параметры

*pInitializationString*<br/>
[out] Указатель на строку инициализации.

*bIncludePassword*<br/>
[in] **true** Если строка содержит пароль; в противном случае **false**.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Результирующая строка инициализации можно использовать для более поздней версии повторного открытия соединения с источником данных.

## <a name="getproperties"></a> CDataSource::GetProperties

Возвращает сведения о свойствах, запрошенный для объекта источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetProperties(ULONG ulPropIDSets, 
   constDBPROPIDSET* pPropIDSet, 
   ULONG* pulPropertySets, 
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>Параметры

См. в разделе [IDBProperties::GetProperties](/previous-versions/windows/desktop/ms714344) в *справочнике программиста OLE DB* в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Чтобы получить одно свойство, используйте [GetProperty](../../data/oledb/cdatasource-getproperty.md).

## <a name="getproperty"></a> CDataSource::GetProperty

Возвращает значение указанного свойства для объекта источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetProperty(const GUID& guid, 
   DBPROPID propid, 
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
[in] Идентификатор GUID, определяющий свойство, для которого возвращаются свойства.

*PropID*<br/>
[in] Идентификатор свойства для свойства для возврата.

*pVariant*<br/>
[out] Указатель на значение variant, где `GetProperty` возвращает значение свойства.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Чтобы получить несколько свойств, используйте [GetProperties](../../data/oledb/cdatasource-getproperties.md).

## <a name="open"></a> CDataSource::Open

Открывает подключение к источнику данных с помощью `CLSID`, `ProgID`, или `CEnumerator` моникер или предлагает пользователю диалоговое окно для выбора.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID, 
   DBPROPSET* pPropSet = NULL, 
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID, 
   LPCTSTR pName,LPCTSTR pUserName = NULL, 
   LPCTSTR pPassword = NULL, 
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>Параметры

*CLSID*<br/>
[in] `CLSID` Поставщика данных.

*pPropSet*<br/>
[in] Указатель на массив [DBPROPSET](/previous-versions/windows/desktop/ms714367) структур, содержащих свойства и значения, которые можно установить. См. в разделе [наборов свойств и группы свойств](/previous-versions/windows/desktop/ms713696) в *справочнике программиста OLE DB* в Windows SDK.

*nPropertySets*<br/>
[in] Число [DBPROPSET](/previous-versions/windows/desktop/ms714367) структуры, передаются в *pPropSet* аргумент.

*pName*<br/>
[входные данные] Имя базы данных, к которой необходимо подключиться.

*pUserName*<br/>
[входные данные] Имя пользователя.

*pPassword*<br/>
[входные данные] Пароль пользователя.

*nInitMode*<br/>
[входные данные] Режим инициализации базы данных. См. в разделе [свойства инициализации](/previous-versions/windows/desktop/ms723127)в *Справочник программиста OLE DB по* в пакете SDK Windows для получения списка допустимых режимов инициализации. Если *nInitMode* — это инициализация нулю, то режим включается в набор свойств, используемых для открытия соединения.

*szProgID*<br/>
[входные данные] Идентификатор программы.

*enumerator*<br/>
[in] Объект [CEnumerator](../../data/oledb/cenumerator-class.md) объект, используемый для получения моникера для открытия соединения, если вызывающий объект не указывает `CLSID`.

*hWnd*<br/>
[входные данные] Дескриптор окна, которое является родительским объектом диалогового окна. Перегрузки функции, которая использует *hWnd* параметр будет автоматически вызываются компоненты службы; Дополнительные сведения см. в разделе "Примечания".

*dwPromptOptions*<br/>
[входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Перегрузка метода, который использует *hWnd* параметра открывает объект источника данных с помощью компонентов службы в oledb32.dll; эта библиотека DLL содержит реализацию возможностей компонентов службы, такие как создание пулов ресурсов, автоматически Прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB в [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

Перегрузки метода, не использующих *hWnd* параметр откройте объект источника данных без использования компонентов службы в oledb32.dll. Объект [CDataSource](../../data/oledb/cdatasource-class.md) открытый с помощью этих перегрузок функций не смогут использовать все функции службы компонентов.

### <a name="example"></a>Пример

В следующем коде показано, как открыть источник данных Jet 4.0 с помощью шаблонов OLE DB. Источник данных Jet обрабатывается так же, как источник данных OLE DB. Тем не менее при вызове `Open` требуется два набора свойства: один для DBPROPSET_DBINIT, а другой — для DBPROPSET_JETOLEDB_DBINIT, таким образом, можно задать DBPROP_JETOLEDB_DATABASEPASSWORD.

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="openfromfilename"></a> CDataSource::OpenFromFileName

Открывает источник данных из файла, указанного пользователем по имени.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>Параметры

*szFileName*<br/>
[входные данные] Имя файла (обычно это файл подключения к источнику данных (UDL)).

Дополнительные сведения о файлах передачи данных (UDL-файлах) см. в разделе [Обзор API связи данных](/previous-versions/windows/desktop/ms718102) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB в [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="openfrominitializationstring"></a> CDataSource::OpenFromInitializationString

Открывает источник данных, указанная в строке инициализации, предоставленные пользователем.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString, 
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>Параметры

*szInitializationString*<br/>
[in] Строка инициализации.

*fPromptForInfo*<br/>
[in] Если этот аргумент имеет значение **true**, затем `OpenFromInitializationString` установит свойство свойство DBPROP_INIT_PROMPT DBPROMPT_COMPLETEREQUIRED, который указывает, что пользователю запрос только в том случае, если необходима дополнительная информация. Это удобно для ситуаций, в которых в строке инициализации указан базу данных, требующий пароль, но строка не содержит пароль. Пользователь будет запрашиваться пароль (или все отсутствующие сведения) при попытке подключения к базе данных.

Значение по умолчанию — **false**, который указывает, что пользователь никогда не быть запросом (наборы свойство DBPROP_INIT_PROMPT в значение DBPROMPT_NOPROMPT).

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д.

## <a name="openwithpromptfilename"></a> CDataSource::OpenWithPromptFileName

Этот метод отображает диалоговое окно, а затем открывает источник данных, используя указанный пользователем файл.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ), 
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE, 
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>Параметры

*hWnd*<br/>
[входные данные] Дескриптор окна, которое является родительским объектом диалогового окна.

*dwPromptOptions*<br/>
[входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.

*szInitialDirectory*<br/>
[входные данные] Исходный каталог для отображения в диалоговом окне выбора.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB в [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="openwithservicecomponents"></a> CDataSource::OpenWithServiceComponents

Открывает объект источника данных с помощью компонентов службы в oledb32.dll.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>Параметры

*CLSID*<br/>
[in] `CLSID` Поставщика данных.

*szProgID*<br/>
[входные данные] Идентификатор программы поставщика данных.

*pPropset*<br/>
[in] Указатель на массив [DBPROPSET](/previous-versions/windows/desktop/ms714367) структур, содержащих свойства и значения, которые можно установить. См. в разделе [наборов свойств и группы свойств](/previous-versions/windows/desktop/ms713696) в *справочнике программиста OLE DB* в Windows SDK. При инициализации объекта источника данных свойства должны принадлежать к группе свойств источника данных. Если в то же свойство указано более одного раза *pPropset*, то используется значение, которое зависит от поставщика. Если *ulPropSets* равен нулю, этот параметр учитывается.

*ulPropSets*<br/>
[in] Число [DBPROPSET](/previous-versions/windows/desktop/ms714367) структуры, передаются в *pPropSet* аргумент. Если это равно нулю, поставщик не учитывает *pPropset*.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB в [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)