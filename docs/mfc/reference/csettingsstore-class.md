---
title: "Класс CSettingsStore | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8ed7cc6c6671e85c21379c4804df4d2f3e3d99d
ms.sourcegitcommit: 2aeb507a426fc7881ea59115b1d5139c0a30ba91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2018
---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Создает программу-оболочку для API-функций Windows, обеспечивая объектно-ориентированный интерфейс, который используется для доступа к реестру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Создает объект `CSettingsStore`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Закрывает открыть раздел реестра.|  
|[CSettingsStore::CreateKey](#createkey)|Открывает указанный ключ или создает ее, если она не существует.|  
|[CSettingsStore::DeleteKey](#deletekey)|Удаляет указанный ключ и все его дочерние элементы.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Удаляет указанное значение открытым ключом.|  
|[CSettingsStore::Open](#open)|Открывает указанный ключ.|  
|[CSettingsStore::Read](#read)|Извлекает данные для указанного значения ключа.|  
|[CSettingsStore::Write](#write)|Записывает значение в реестр с открытым ключом.|  
  
## <a name="remarks"></a>Примечания  
 Функции-члены `CreateKey` и `Open` очень похожи. Если раздел реестра уже существует, `CreateKey` и `Open` функция таким же образом. Тем не менее, если раздел реестра не существует, `CreateKey` он будет создан в то время как `Open` вернет код ошибки.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование методов открытия и чтения `CSettingsStore` класса. Этот фрагмент кода является частью [совет демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsettingsstore.h  
  
##  <a name="close"></a>CSettingsStore::Close  
 Закрывает открыть раздел реестра.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывается из деструктора объекта [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="createkey"></a>CSettingsStore::CreateKey  
 Открывает раздел реестра или создает ее, если она не существует.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszPath`  
 Указывает имя ключа для создания или открытия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 0 в случае успешного выполнения; в противном случае ненулевое значение.  
  
### <a name="remarks"></a>Примечания  
 `CreateKey`использует `m_hKey` как корень реестра запросы. Он выполняет поиск `pszPath` виде подраздела `m_hKey`. Если ключ не существует, `CreateKey` его создает. В противном случае он открывает ключ. `CreateKey`Затем задает `m_hKey` для созданного или открытого ключа.  
  
##  <a name="csettingsstore"></a>CSettingsStore::CSettingsStore  
 Создает объект `CSettngsStore`.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAdmin`  
 Логический параметр, указывает ли `CSettingsStore` объект действует в режиме администратора.  
  
 [in] `bReadOnly`  
 Логический параметр, указывает ли `CSettingsStore` объект создается в режиме только для чтения.  
  
### <a name="remarks"></a>Примечания  
 Если `bAdmin` равно `true`, `m_hKey` присвоено переменной-члена `HKEY_LOCAL_MACHINE`. Если задать `bAdmin` для `false`, `m_hKey` равно `HKEY_CURRENT_USER`.  
  
 Зависит от прав доступа `bReadOnly` параметра. Если `bReadonly` — `false`, безопасный доступ будет присвоено `KEY_ALL_ACCESS`. Если `bReadyOnly` — `true`, безопасный доступ будет присвоено сочетание `KEY_QUERY_VALUE, KEY_NOTIFY` и `KEY_ENUMERATE_SUB_KEYS`. Дополнительные сведения о безопасности доступа вместе с реестра см. в разделе [безопасности ключ реестра и права доступа](http://msdn.microsoft.com/library/windows/desktop/ms724878).  
  
 Деструктор для `CSettingsStore` освобождает `m_hKey` автоматически.  
  
##  <a name="deletekey"></a>CSettingsStore::DeleteKey  
 Удаляет ключ и все его дочерние элементы из реестра.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszPath`  
 Имя ключа для удаления.  
  
 [in] `bAdmin`  
 Параметр, задающий расположение ключа для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершится ошибкой, если `CSettingsStore` объект находится в режиме только для чтения.  
  
 Если параметр `bAdmin` равен нулю, `DeleteKey` ищет ключ для удаления в разделе `HKEY_CURRENT_USER`. Если `bAdmin` отлично от нуля, `DeleteKey` ищет ключ для удаления в разделе `HKEY_LOCAL_MACHINE`.  
  
##  <a name="deletevalue"></a>CSettingsStore::DeleteValue  
 Удаляет значение из `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszValue`  
 Задает значение поля для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="open"></a>CSettingsStore::Open  
 Открывает раздел реестра.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszPath`  
 Имя раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 После этого метода успешно открывает указанный ключ, он задает `m_hKey` дескриптор этого ключа.  
  
##  <a name="read"></a>CSettingsStore::Read  
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
 [in] `pszKey`  
 Указатель на строку, завершающуюся значением null, содержащая имя значения, которое необходимо считать из реестра.  
  
 [выходной] `iVal`  
 Ссылка на целочисленную переменную, получающий значение из раздела реестра.  
  
 [выходной] `dwVal`  
 Ссылка на 32-разрядных двойное слово переменной, которая получает значение, считанное из реестра.  
  
 [выходной] `sVal`  
 Ссылка на строковую переменную, которая получает значение, считанное из реестра.  
  
 [выходной] `scStringList`  
 Ссылка на список строковую переменную, которая получает значение, считанное из реестра.  
  
 [выходной] `scArray`  
 Ссылка на массив строковую переменную, которая получает значение, считанное из реестра.  
  
 [выходной] `dwcArray`  
 Ссылка на переменную массива 32-разрядных двойное слово, получающий значение из раздела реестра.  
  
 [выходной] `wcArray`  
 Ссылка на переменную массива 16-разрядное слово, которая получает значение, считанное из реестра.  
  
 [выходной] `bcArray`  
 Ссылка на переменную массива байтов, которая получает значение, считанное из реестра.  
  
 [выходной] `lpPoint`  
 Ссылка на указатель `POINT` структуру, которая получает значение, прочитать из реестра.  
  
 [выходной] `rect`  
 Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) считать переменную, которая получает значение из раздела реестра.  
  
 [выходной] `ppData`  
 Указатель на указатель на данные, которые получает значение чтения из раздела реестра.  
  
 [выходной] `pBytes`  
 Указатель на переменную целого числа без знака. Эта переменная принимает размер буфера, `ppData` указывает.  
  
 [выходной] `list`  
 Ссылка на [CObList](../../mfc/reference/coblist-class.md) считать переменную, которая получает значение из раздела реестра.  
  
 [выходной] `obj`  
 Ссылка на [CObject](../../mfc/reference/cobject-class.md) считать переменную, которая получает значение из раздела реестра.  
  
 [выходной] `pObj`  
 Ссылка на указатель `CObject` считать переменную, которая получает значение из раздела реестра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 `Read`проверяет наличие `pszKey` виде подраздела `m_hKey`.  
  
##  <a name="write"></a>CSettingsStore::Write  
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
 [in] `pszKey`  
 Указатель на строку, содержащую имя задаваемое значение.  
  
 [in] `iVal`  
 Ссылка на целочисленная переменная, содержащая данные для хранения.  
  
 [in] `dwVal`  
 Ссылка на 32-разрядных двойное слово переменную, которая содержит данные для хранения.  
  
 [in] `pszVal`  
 Указатель на строку, завершающуюся значением null переменную, которая содержит данные для хранения.  
  
 [in] `scStringList`  
 Ссылка на [CStringList](../../mfc/reference/cstringlist-class.md) переменную, которая содержит данные для хранения.  
  
 [in] `bcArray`  
 Ссылка на переменную массива байтов, содержащий данные для хранения.  
  
 [in] `scArray`  
 Ссылка на массив строковую переменную, которая содержит данные для хранения.  
  
 [in] `dwcArray`  
 Ссылка на переменную массива 32-разрядных двойное слово, содержащий данные для хранения.  
  
 [in] `wcArray`  
 Ссылка на переменную массива 16-разрядное слово, которая содержит данные для хранения.  
  
 [in] `rect`  
 Ссылка на [CRect](../../atl-mfc-shared/reference/crect-class.md) переменную, которая содержит данные для хранения.  
  
 [in] `lpPoint`  
 Ссылка на указатель `POINT` переменную, которая содержит данные для хранения.  
  
 [in] `pData`  
 Указатель на буфер, содержащий данные для хранения.  
  
 [in] `nBytes`  
 Указывает размер в байтах данных, к которому `pData` параметр точек.  
  
 [in] `list`  
 Ссылка на [CObList](../../mfc/reference/coblist-class.md) переменную, которая содержит данные для хранения.  
  
 [in] `obj`  
 Ссылка на [CObject](../../mfc/reference/cobject-class.md) переменную, которая содержит данные для хранения.  
  
 [in] `pObj`  
 Указатель на указатель на `CObject` переменную, которая содержит данные для хранения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для записи в реестр, необходимо задать `bReadOnly` ненулевое значение, при создании [CSettingsStore](../../mfc/reference/csettingsstore-class.md) объекта. Дополнительные сведения см. в разделе [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
