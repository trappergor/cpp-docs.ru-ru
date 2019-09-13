---
title: CSettingsStore Class
ms.date: 11/04/2016
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
ms.openlocfilehash: 75d86b81d9651e5892913af5919ae0a78fe6bbc5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502925"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class

Создает программу-оболочку для API-функций Windows, обеспечивая объектно-ориентированный интерфейс, который используется для доступа к реестру.

## <a name="syntax"></a>Синтаксис

```
class CSettingsStore : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ксеттингссторе:: Ксеттингссторе](#csettingsstore)|Создает объект `CSettingsStore`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ксеттингссторе:: Close](#close)|Закрывает раздел реестра Open.|
|[Ксеттингссторе:: CreateKey](#createkey)|Открывает указанный ключ или создает его, если он не существует.|
|[Ксеттингссторе::D Елетекэй](#deletekey)|Удаляет указанный ключ и все его дочерние элементы.|
|[Ксеттингссторе::D Елетевалуе](#deletevalue)|Удаляет указанное значение открытого ключа.|
|[Ксеттингссторе:: Open](#open)|Открывает указанный ключ.|
|[Ксеттингссторе:: Read](#read)|Извлекает данные для указанного значения ключа.|
|[Ксеттингссторе:: Write](#write)|Записывает значение в реестр при открытии ключа.|

## <a name="remarks"></a>Примечания

Функции `CreateKey` элементов и `Open` очень похожи. Если раздел реестра уже существует `CreateKey` и `Open` работает аналогичным образом. Однако если раздел реестра не существует, создаст его, `CreateKey` `Open` тогда как вернет значение ошибки.

## <a name="example"></a>Пример

В следующем примере показано, как использовать методы `CSettingsStore` открытия и чтения класса. Этот фрагмент кода является частью демонстрационного [примера всплывающей подсказки](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Требования

**Заголовок:** афкссеттингссторе. h

##  <a name="close"></a>Ксеттингссторе:: Close

Закрывает раздел реестра Open.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод вызывается из деструктора [класса ксеттингссторе](../../mfc/reference/csettingsstore-class.md).

##  <a name="createkey"></a>Ксеттингссторе:: CreateKey

Открывает раздел реестра или создает его, если он не существует.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*псзпас*<br/>
окне Указывает имя создаваемого или открываемого ключа.

### <a name="return-value"></a>Возвращаемое значение

0 в случае успеха; в противном случае — ненулевое значение.

### <a name="remarks"></a>Примечания

`CreateKey`использует `m_hKey` в качестве корня запросов реестра. Он выполняет поиск *псзпас* в качестве подраздела `m_hKey`. Если раздел не существует, `CreateKey` создает его. В противном случае он открывает ключ. `CreateKey`затем присваивается `m_hKey` созданному или открытому ключу.

##  <a name="csettingsstore"></a>Ксеттингссторе:: Ксеттингссторе

Создает объект `CSettngsStore`.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Параметры

*бадмин*<br/>
окне Логический параметр, указывающий, `CSettingsStore` работает ли объект в режиме администратора.

*бреадонли*<br/>
окне Логический параметр, указывающий, `CSettingsStore` создается ли объект в режиме только для чтения.

### <a name="remarks"></a>Примечания

Если для *бадмин* задано значение true, `m_hKey` то переменной-члену присваивается значение **HKEY_LOCAL_MACHINE**. Если для *бадмин* задано значение false `m_hKey` , то для параметра задается значение **HKEY_CURRENT_USER**.

Доступ к безопасности зависит от параметра *бреадонли* . Если *бреадонли* имеет значение false, то для доступа к безопасности будет задано значение **KEY_ALL_ACCESS**. Если *бреадйонли* имеет значение true, для доступа к безопасности будет задано сочетание **KEY_QUERY_VALUE, KEY_NOTIFY** и **KEY_ENUMERATE_SUB_KEYS**. Дополнительные сведения о безопасности доступа вместе с реестром см. в разделе раздел [реестра Security and Access Rights](/windows/win32/SysInfo/registry-key-security-and-access-rights).

Деструктор для `CSettingsStore` выпусков `m_hKey` автоматически.

##  <a name="deletekey"></a>Ксеттингссторе::D Елетекэй

Удаляет ключ и все его дочерние элементы из реестра.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Параметры

*псзпас*<br/>
окне Имя удаляемого ключа.

*бадмин*<br/>
окне Параметр, указывающий расположение удаляемого ключа.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод завершится ошибкой, `CSettingsStore` если объект находится в режиме только для чтения.

Если параметр *бадмин* равен нулю, `DeleteKey` ищет ключ для удаления в разделе **HKEY_CURRENT_USER**. Если *бадмин* имеет ненулевое значение, `DeleteKey` ищет ключ для удаления в разделе **HKEY_LOCAL_MACHINE**.

##  <a name="deletevalue"></a>Ксеттингссторе::D Елетевалуе

Удаляет значение из `m_hKey`.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Параметры

*псзвалуе*<br/>
окне Указывает поле значения для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="open"></a>Ксеттингссторе:: Open

Открывает раздел реестра.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*псзпас*<br/>
окне Имя раздела реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После того как этот метод успешно откроет указанный ключ, `m_hKey` он задается в качестве маркера этого ключа.

##  <a name="read"></a>Ксеттингссторе:: Read

Считывает значение из ключа в реестре.

```
virtual BOOL Read(
    LPCTSTR pszKey,
    int& iVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    DWORD& dwVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CString& sVal);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Read(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Read(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Read(
    LPCTSTR pszKey,
    CRect& rect);

virtual BOOL Read(
    LPCTSTR pszKey,
    BYTE** ppData,
    UINT* pBytes);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Read(
    LPCTSTR pszKey,
    CObject*& pObj);
```

### <a name="parameters"></a>Параметры

*псзкэй*<br/>
окне Указатель на строку, завершающуюся нулем, которая содержит имя значения для чтения из реестра.

*ивал*<br/>
заполняет Ссылка на целочисленную переменную, которая получает значение, считанное из раздела реестра.

*дввал*<br/>
заполняет Ссылка на переменную с 32-разрядным двойным словом, которая получает значение, считанное из раздела реестра.

*свал*<br/>
заполняет Ссылка на строковую переменную, которая получает значение, считанное из раздела реестра.

*скстринглист*<br/>
заполняет Ссылка на переменную списка строк, которая получает значение, считанное из раздела реестра.

*скаррай*<br/>
заполняет Ссылка на переменную массива строк, которая получает значение, считанное из раздела реестра.

*двкаррай*<br/>
заполняет Ссылка на 32-разрядную переменную массива двойных слов, которая получает значение, считанное из раздела реестра.

*вкаррай*<br/>
заполняет Ссылка на 16-разрядную переменную массива Word, которая получает значение, считанное из раздела реестра.

*бкаррай*<br/>
заполняет Ссылка на переменную массива байтов, которая получает значение, считанное из раздела реестра.

*лппоинт*<br/>
заполняет Ссылка на указатель на `POINT` структуру, получающую значение, считанное из раздела реестра.

*rect*<br/>
заполняет Ссылка на переменную [крект](../../atl-mfc-shared/reference/crect-class.md) , которая получает значение, считанное из раздела реестра.

*ппдата*<br/>
заполняет Указатель на указатель на данные, которые получают значение, считанное из раздела реестра.

*пбитес*<br/>
заполняет Указатель на целочисленную переменную без знака. Эта переменная получает размер буфера, на который указывает *ппдата* .

*list*<br/>
заполняет Ссылка на переменную [коблист](../../mfc/reference/coblist-class.md) , которая получает значение, считанное из раздела реестра.

*obj*<br/>
заполняет Ссылка на переменную [CObject](../../mfc/reference/cobject-class.md) , которая получает значение, считанное из раздела реестра.

*побж*<br/>
заполняет Ссылка на указатель на `CObject` переменную, которая получает значение, считанное из раздела реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Read`проверяет наличие *псзкэй* в качестве подраздела `m_hKey`.

##  <a name="write"></a>Ксеттингссторе:: Write

Записывает значение в реестр при открытии ключа.

```
virtual BOOL Write(
    LPCTSTR pszKey,
    int iVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    DWORD dwVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPCTSTR pszVal);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringList& scStringList);

virtual BOOL Write(
    LPCTSTR pszKey,
    CByteArray& bcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CStringArray& scArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CDWordArray& dwcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    CWordArray& wcArray);

virtual BOOL Write(
    LPCTSTR pszKey,
    const CRect& rect);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPPOINT& lpPoint);

virtual BOOL Write(
    LPCTSTR pszKey,
    LPBYTE pData,
    UINT nBytes);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObList& list);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject& obj);

virtual BOOL Write(
    LPCTSTR pszKey,
    CObject* pObj);
```

### <a name="parameters"></a>Параметры

*псзкэй*<br/>
окне Указатель на строку, содержащую имя заданной величины.

*ивал*<br/>
окне Ссылка на целочисленную переменную, содержащую данные для хранения.

*дввал*<br/>
окне Ссылка на 32-разрядную переменную двойного слова, которая содержит данные для хранения.

*псзвал*<br/>
окне Указатель на строковую переменную, завершающуюся нулем, которая содержит данные для хранения.

*скстринглист*<br/>
окне Ссылка на переменную [кстринглист](../../mfc/reference/cstringlist-class.md) , содержащую данные для хранения.

*бкаррай*<br/>
окне Ссылка на переменную массива байтов, содержащую данные для хранения.

*скаррай*<br/>
окне Ссылка на переменную массива строк, содержащую данные для хранения.

*двкаррай*<br/>
окне Ссылка на 32-разрядную переменную массива двойных слов, содержащую данные для хранения.

*вкаррай*<br/>
окне Ссылка на 16-разрядную переменную массива Word, которая содержит данные для хранения.

*rect*<br/>
окне Ссылка на переменную [крект](../../atl-mfc-shared/reference/crect-class.md) , содержащую данные для хранения.

*лппоинт*<br/>
окне Ссылка на указатель на `POINT` переменную, содержащую данные для хранения.

*pData*<br/>
окне Указатель на буфер, содержащий данные для хранения.

*nBytes*<br/>
окне Задает размер (в байтах) данных, на которые указывает параметр *pData* .

*list*<br/>
окне Ссылка на переменную [коблист](../../mfc/reference/coblist-class.md) , содержащую данные для хранения.

*obj*<br/>
окне Ссылка на переменную [CObject](../../mfc/reference/cobject-class.md) , которая содержит данные для хранения.

*побж*<br/>
окне Указатель на указатель на `CObject` переменную, содержащую данные для хранения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Для записи в реестр необходимо установить *бреадонли* в ненулевое значение при создании объекта [ксеттингссторе](../../mfc/reference/csettingsstore-class.md) . Дополнительные сведения см. в разделе [ксеттингссторе:: ксеттингссторе](#csettingsstore).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
