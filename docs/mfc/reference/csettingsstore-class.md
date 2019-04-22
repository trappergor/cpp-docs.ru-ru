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
ms.openlocfilehash: 1e1373da86c1c3fea3b1ddd6ff17f0fac4f76980
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770399"
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
|[CSettingsStore::CSettingsStore](#csettingsstore)|Создает объект `CSettingsStore`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSettingsStore::Close](#close)|Закрывает открыть раздел реестра.|
|[CSettingsStore::CreateKey](#createkey)|Открывает указанный ключ, или создает ее, если она не существует.|
|[CSettingsStore::DeleteKey](#deletekey)|Удаляет указанный ключ и все его дочерние узлы.|
|[CSettingsStore::DeleteValue](#deletevalue)|Удаляет указанное значение открытым ключом.|
|[CSettingsStore::Open](#open)|Открывает указанный ключ.|
|[CSettingsStore::Read](#read)|Извлекает данные для указанного значения ключа.|
|[CSettingsStore::Write](#write)|Записывает значение в реестр с открытым ключом.|

## <a name="remarks"></a>Примечания

Функции-члены `CreateKey` и `Open` очень похожи. Если раздел реестра уже существует, `CreateKey` и `Open` функция таким же образом. Тем не менее, если раздел реестра не существует, `CreateKey` создаст ее в то время как `Open` будет возвращать значение ошибки.

## <a name="example"></a>Пример

Следующий пример демонстрирует использование методов Open и чтения `CSettingsStore` класса. Этот фрагмент кода является частью [средство совет демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CSettingsStore`

## <a name="requirements"></a>Требования

**Заголовок:** afxsettingsstore.h

##  <a name="close"></a>  CSettingsStore::Close

Закрывает открыть раздел реестра.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод вызывается из деструктора объекта [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).

##  <a name="createkey"></a>  CSettingsStore::CreateKey

Открывает раздел реестра или создает ее, если она не существует.

```
virtual BOOL CreateKey(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
[in] Указывает имя ключа для создания или открытия.

### <a name="return-value"></a>Возвращаемое значение

0, если выполнение прошло успешно; в противном случае ненулевое значение.

### <a name="remarks"></a>Примечания

`CreateKey` использует `m_hKey` как корень реестра запросы. Он выполняет поиск *pszPath* виде подраздела `m_hKey`. Если ключ не существует, `CreateKey` создает ее. В противном случае он открывает ключ. `CreateKey` Затем задает `m_hKey` для созданного или открытого ключа.

##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore

Создает объект `CSettngsStore`.

```
CSettingsStore(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>Параметры

*bAdmin*<br/>
[in] Логический параметр, указывает ли `CSettingsStore` объект действует в режиме администратора.

*bReadOnly*<br/>
[in] Логический параметр, указывает ли `CSettingsStore` объект создается в режиме только для чтения.

### <a name="remarks"></a>Примечания

Если *bAdmin* имеет значение TRUE, `m_hKey` присваивается переменной-члена **HKEY_LOCAL_MACHINE**. Если задать *bAdmin* значение false, `m_hKey` присваивается **HKEY_CURRENT_USER**.

Зависит от прав доступа *bReadOnly* параметра. Если *bReadonly* имеет значение FALSE, будет присвоено прав доступа **KEY_ALL_ACCESS**. Если *bReadyOnly* имеет значение TRUE, прав доступа будет присвоено сочетание **KEY_QUERY_VALUE, KEY_NOTIFY** и **KEY_ENUMERATE_SUB_KEYS**. Дополнительные сведения о безопасности доступа вместе с реестром, см. в разделе [безопасности ключ реестра и права доступа](/windows/desktop/SysInfo/registry-key-security-and-access-rights).

Деструктор для `CSettingsStore` освобождает `m_hKey` автоматически.

##  <a name="deletekey"></a>  CSettingsStore::DeleteKey

Удаляет ключ и все его дочерние узлы из реестра.

```
virtual BOOL DeleteKey(
    LPCTSTR pszPath,
    BOOL bAdmin = FALSE);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
[in] Имя удаляемого раздела.

*bAdmin*<br/>
[in] Переключатель, указывающий расположение удаляемого раздела.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод завершится ошибкой, если `CSettingsStore` объект находится в режиме только для чтения.

Если параметр *bAdmin* равен нулю, `DeleteKey` ищет ключ для удаления в разделе **HKEY_CURRENT_USER**. Если *bAdmin* не равно нулю, `DeleteKey` ищет ключ для удаления в разделе **HKEY_LOCAL_MACHINE**.

##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue

Удаляет значение из `m_hKey`.

```
virtual BOOL DeleteValue(LPCTSTR pszValue);
```

### <a name="parameters"></a>Параметры

*pszValue*<br/>
[in] Задает поле значений для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="open"></a>  CSettingsStore::Open

Открывает раздел реестра.

```
virtual BOOL Open(LPCTSTR pszPath);
```

### <a name="parameters"></a>Параметры

*pszPath*<br/>
[in] Имя раздела реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После этого метод успешно открывает указанный ключ, он задает `m_hKey` для обработки этого ключа.

##  <a name="read"></a>  CSettingsStore::Read

Считывает значение из раздела в реестре.

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

*pszKey*<br/>
[in] Указатель на заканчивающуюся нулем строку, содержащую имя значения, которое необходимо считать из реестра.

*iVal*<br/>
[out] Ссылка на переменную integer, который получает значение, считанное из реестра.

*dwVal*<br/>
[out] Ссылка на переменную 32-разрядных двойное слово, который получает значение, считанное из реестра.

*sVal*<br/>
[out] Ссылка на строковую переменную, которая получает значение, считанное из реестра.

*scStringList*<br/>
[out] Ссылка на список строковую переменную, которая получает значение, считанное из реестра.

*scArray*<br/>
[out] Ссылка на массив строковую переменную, которая получает значение, считанное из реестра.

*dwcArray*<br/>
[out] Ссылка на переменную массива 32-разрядных двойное слово, который получает значение, считанное из реестра.

*wcArray*<br/>
[out] Ссылка на переменную массива 16-разрядное слово, который получает значение, считанное из реестра.

*bcArray*<br/>
[out] Ссылка на переменную массива байтов, которая получает значение, считанное из реестра.

*lpPoint*<br/>
[out] Ссылка на указатель на `POINT` структуры, который получает значение, чтение из реестра.

*rect*<br/>
[out] Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) переменную, которая получает значение, чтение из реестра.

*ppData*<br/>
[out] Указатель на указатель на данные, который получает значение, чтение из реестра.

*pBytes*<br/>
[out] Указатель на переменную целого числа без знака. Эта переменная принимает размер буфера, *ppData* указывает.

*list*<br/>
[out] Ссылка на [CObList](../../mfc/reference/coblist-class.md) переменную, которая получает значение, чтение из реестра.

*obj*<br/>
[out] Ссылка на [CObject](../../mfc/reference/cobject-class.md) переменную, которая получает значение, чтение из реестра.

*pObj*<br/>
[out] Ссылка на указатель на `CObject` переменную, которая получает значение, чтение из реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Read` проверяет наличие *pszKey* виде подраздела `m_hKey`.

##  <a name="write"></a>  CSettingsStore::Write

Записывает значение в реестр с открытым ключом.

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

*pszKey*<br/>
[in] Указатель на строку, содержащую имя присваиваемое значение.

*iVal*<br/>
[in] Ссылка на целочисленную переменную, содержащий сохраняемые данные.

*dwVal*<br/>
[in] Ссылка на переменную 32-разрядных двойное слово, которая содержит сохраняемые данные.

*pszVal*<br/>
[in] Указатель на переменную заканчивающуюся нулем строку, содержащую данные для хранения.

*scStringList*<br/>
[in] Ссылка на [CStringList](../../mfc/reference/cstringlist-class.md) переменную, содержащую данные для хранения.

*bcArray*<br/>
[in] Ссылка на переменную массива байтов, содержащий сохраняемые данные.

*scArray*<br/>
[in] Ссылка на строковую переменную массива, содержащий сохраняемые данные.

*dwcArray*<br/>
[in] Ссылка на переменную массива 32-разрядных двойное слово, которая содержит сохраняемые данные.

*wcArray*<br/>
[in] Ссылка на переменную массива 16-разрядное слово, которая содержит сохраняемые данные.

*rect*<br/>
[in] Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) переменную, содержащую данные для хранения.

*lpPoint*<br/>
[in] Ссылка на указатель на `POINT` переменную, содержащую данные для хранения.

*pData*<br/>
[in] Указатель на буфер, который содержит сохраняемые данные.

*nBytes*<br/>
[in] Указывает размер в байтах данных, к которому *pData* указывает параметр.

*list*<br/>
[in] Ссылка на [CObList](../../mfc/reference/coblist-class.md) переменную, содержащую данные для хранения.

*obj*<br/>
[in] Ссылка на [CObject](../../mfc/reference/cobject-class.md) переменную, содержащую данные для хранения.

*pObj*<br/>
[in] Указатель на указатель на `CObject` переменную, содержащую данные для хранения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Для записи в реестр, необходимо задать *bReadOnly* ненулевое значение при создании [CSettingsStore](../../mfc/reference/csettingsstore-class.md) объекта. Дополнительные сведения см. в разделе [CSettingsStore::CSettingsStore](#csettingsstore).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
