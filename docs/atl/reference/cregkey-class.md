---
title: Класс CRegKey | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6daec3347aecaed3ba0aba5dec106d049a6a701
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cregkey-class"></a>Класс CRegKey
Этот класс предоставляет методы для управления записей в системном реестре.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CRegKey
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|Конструктор.|  
|[CRegKey:: ~ CRegKey](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|Этот метод вызывается для присоединения к HKEY `CRegKey` , задавая [m_hKey](#m_hkey) дескриптор элемента `hKey`.|  
|[CRegKey::Close](#close)|Вызовите этот метод для освобождения [m_hKey](#m_hkey) член обработки и присвойте ему значение NULL.|  
|[CRegKey::Create](#create)|Этот метод вызывается для создания указанным ключом, если он отсутствует в виде подраздела `hKeyParent`.|  
|[CRegKey::DeleteSubKey](#deletesubkey)|Этот метод используется для удаления указанного ключа из реестра.|  
|[CRegKey::DeleteValue](#deletevalue)|Вызовите этот метод, чтобы удалить поле значение из [m_hKey](#m_hkey).|  
|[CRegKey::Detach](#detach)|Этот метод вызывается для отсоединения [m_hKey](#m_hkey) дескриптор элемента из `CRegKey` и задайте `m_hKey` значение NULL.|  
|[CRegKey::EnumKey](#enumkey)|Вызовите этот метод, чтобы пронумеровать подключи открыть раздел реестра.|  
|[CRegKey::Flush](#flush)|Этот метод используется для записи всех атрибутов открыть раздел реестра в реестр.|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|Этот метод используется для извлечения копии дескриптора безопасности, защищающий ключ открыть реестр.|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Этот метод уведомляет вызывающий объект о внесении изменений в атрибуты или содержимое открыть раздел реестра.|  
|[CRegKey::Open](#open)|Вызовите этот метод, чтобы открыть указанный ключ и задать [m_hKey](#m_hkey) для обработки этого ключа.|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Вызовите этот метод, чтобы получить двоичные данные для имени указанного значения.|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Этот метод вызывается для получения данных DWORD для имени указанного значения.|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Этот метод вызывается для получения данных для имени указанного значения GUID.|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Этот метод используется для получения данных, состоящее из нескольких строк для имени указанного значения.|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Этот метод вызывается для получения данных QWORD для имени указанного значения.|  
|[CRegKey::QueryStringValue](#querystringvalue)|Этот метод используется для извлечения строковых данных для имени указанного значения.|  
|[CRegKey::QueryValue](#queryvalue)|Этот метод вызывается для получения данных для указанного значения поля [m_hKey](#m_hkey). Более ранние версии этот метод больше не поддерживаются и помечаются как **ATL_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Этот метод используется для удаления указанного ключа из реестра и явным образом удалить все разделы.|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Вызовите этот метод, чтобы задать двоичное значение раздела реестра.|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|Этот метод используется для задания значения реестра DWORD.|  
|[CRegKey::SetGUIDValue](#setguidvalue)|Этот метод используется для задания значения GUID раздела реестра.|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|Этот метод используется для настройки безопасности раздела реестра.|  
|[CRegKey::SetKeyValue](#setkeyvalue)|Этот метод используется для хранения данных в поле указанное значение указанного ключа.|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Вызовите этот метод, чтобы задать значение, состоящее из нескольких строк раздела реестра.|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|Этот метод используется для задания значения реестра QWORD.|  
|[CRegKey::SetStringValue](#setstringvalue)|Вызовите этот метод, чтобы задать строковое значение реестра.|  
|[CRegKey::SetValue](#setvalue)|Этот метод вызывается для хранения данных в поле указанного значения [m_hKey](#m_hkey). Более ранние версии этот метод больше не поддерживаются и помечаются как **ATL_DEPRECATED**.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|Преобразует `CRegKey` объект HKEY.|  
|[CRegKey::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|Содержит дескриптор раздела реестра, связанные с `CRegKey` объекта.|  
|[CRegKey::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект|  
  
## <a name="remarks"></a>Примечания  
 `CRegKey` Предоставляет методы для создания и удаления ключей и значений в системном реестре. Реестр содержит набор связанных с установкой определений для системных компонентов, таких как номера версий программного обеспечения, сопоставлений логических физических установленном оборудовании и COM-объектов.  
  
 `CRegKey` предоставляет интерфейс программирования для системного реестра для данного компьютера. Например, чтобы открыть определенного раздела реестра, вызовите `CRegKey::Open`. Чтобы получить или изменять значения данных, вызовите `CRegKey::QueryValue` или `CRegKey::SetValue`соответственно. Чтобы закрыть ключ, вызовите `CRegKey::Close`.  
  
 При закрытии ключа его данных реестра записывается (Сброс) на жесткий диск. Этот процесс может занять несколько секунд. Если приложение необходимо явно указать данные реестра на жестком диске, можно вызвать [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) функции Win32. Тем не менее **RegFlushKey** использует много системных ресурсов и должен вызываться только в случае крайней необходимости.  
  
> [!IMPORTANT]
>  Все методы, позволяющие вызывающему объекту указывать расположение реестра существует возможность считывать данные, которые не могут быть доверенными. Использование методов, которые делают [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) необходимо учитывать, эта функция явным образом не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>  CRegKey::Attach  
 Этот метод вызывается для присоединения к HKEY `CRegKey` , задавая [m_hKey](#m_hkey) дескриптор элемента `hKey`.  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hKey`  
 Дескриптор раздела реестра.  
  
### <a name="remarks"></a>Примечания  
 **Присоединение** проверяет Если `m_hKey` отлично от NULL.  
  
##  <a name="close"></a>  CRegKey::Close  
 Вызовите этот метод для освобождения [m_hKey](#m_hkey) член обработки и присвойте ему значение NULL.  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае возвращает значение ошибки.  
  
##  <a name="create"></a>  CRegKey::Create  
 Этот метод вызывается для создания указанным ключом, если он отсутствует в виде подраздела `hKeyParent`.  
  
```
LONG Create(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyParent`  
 Дескриптор открытый ключ.  
  
 `lpszKeyName`  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом `hKeyParent`.  
  
 `lpszClass`  
 Указывает класс ключа для создания или открытия. Значение по умолчанию — REG_NONE.  
  
 `dwOptions`  
 Параметры для ключа. Значение по умолчанию — REG_OPTION_NON_VOLATILE. Список возможных значений и описаний см. в разделе [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) в Windows SDK.  
  
 `samDesired`  
 Безопасный доступ для ключа. Значение по умолчанию — KEY_READ &#124; KEY_WRITE. Список возможных значений и описаний см. в разделе **RegCreateKeyEx**.  
  
 *lpSecAttr*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуру, которая указывает, является ли дескриптор ключа могут наследоваться дочерним процессом. По умолчанию этот параметр имеет значение NULL (что означает, что дескриптор не наследуется).  
  
 *lpdwDisposition*  
 [out] Если значение NULL, возвращает REG_CREATED_NEW_KEY (если ключ не существовал и был создан) или REG_OPENED_EXISTING_KEY (если ключ существует и был открыт).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS и открывает ключ. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 **Создание** задает [m_hKey](#m_hkey) член для обработки этого ключа.  
  
##  <a name="cregkey"></a>  CRegKey::CRegKey  
 Конструктор.  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ссылка на объект `CRegKey`.  
  
 `hKey`  
 Дескриптор раздела реестра.  
  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="remarks"></a>Примечания  
 Создает новый объект `CRegKey`. Объект может быть создан из существующего `CRegKey` объекта, или из дескриптора для раздела реестра.  
  
##  <a name="dtor"></a>  CRegKey:: ~ CRegKey  
 Деструктор  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор выпуски `m_hKey`.  
  
##  <a name="deletesubkey"></a>  CRegKey::DeleteSubKey  
 Этот метод используется для удаления указанного ключа из реестра.  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSubKey`  
 Указывает имя ключа для удаления. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 `DeleteSubKey` можно удалить только ключ, который не имеет подразделов. Если раздел содержит подразделы, вызовите [RecurseDeleteKey](#recursedeletekey) вместо него.  
  
##  <a name="deletevalue"></a>  CRegKey::DeleteValue  
 Вызовите этот метод, чтобы удалить поле значение из [m_hKey](#m_hkey).  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszValue`  
 Задает значение поля для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
##  <a name="detach"></a>  CRegKey::Detach  
 Этот метод вызывается для отсоединения [m_hKey](#m_hkey) дескриптор элемента из `CRegKey` и задайте `m_hKey` значение NULL.  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Раздел HKEY, КОТОРЫЙ сопоставлен `CRegKey` объекта.  
  
##  <a name="enumkey"></a>  CRegKey::EnumKey  
 Вызовите этот метод, чтобы пронумеровать подключи открыть раздел реестра.  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iIndex`  
 Индекс подразделов. Этот параметр должен быть равен нулю при первом вызове и затем увеличивается на единицу при последующих вызовах  
  
 `pszName`  
 Указатель на буфер, получающий имя раздела, включая завершающий символ null. Имя подраздела копируется в буфер, а не полного ключа иерархию.  
  
 *pnNameLength*  
 Указатель на переменную, указывающее размер в TCHARs буфера, определяемое `pszName` параметра. Размер должен учитывать завершающий символ null. Когда этот метод возвращает, на который указывает переменная *pnNameLength* содержит число символов, сохраненных в буфере. Число, возвращаемое не включает завершающий нуль-символ.  
  
 *pftLastWriteTime*  
 Указатель на переменную, получающую время перечисляемое подраздела последней операции записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Чтобы пронумеровать подключи, вызовите `CRegKey::EnumKey` с индекса 0. Увеличьте значение индекса и повторите, метод возвращает ERROR_NO_MORE_ITEMS. Дополнительные сведения см. в разделе [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) в Windows SDK.  
  
##  <a name="flush"></a>  CRegKey::Flush  
 Этот метод используется для записи всех атрибутов открыть раздел реестра в реестр.  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) в Windows SDK.  
  
##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity  
 Этот метод используется для извлечения копии дескриптора безопасности, защищающий ключ открыть реестр.  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `si`  
 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) значение, указывающее, запрошенная информация о безопасности.  
  
 `psd`  
 Указатель на буфер, получающий копию дескриптора безопасности.  
  
 `pnBytes`  
 Размер в байтах буфера, на который указывает `psd`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенных в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313).  
  
##  <a name="m_hkey"></a>  CRegKey::m_hKey  
 Содержит дескриптор раздела реестра, связанные с `CRegKey` объекта.  
  
```
HKEY m_hKey;
```  
  
##  <a name="m_ptm"></a>  CRegKey::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue  
 Этот метод уведомляет вызывающий объект о внесении изменений в атрибуты или содержимое открыть раздел реестра.  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bWatchSubtree*  
 Задает флаг, указывающий, следует ли отправлять отчет изменения в указанный ключ и все его подразделы или только в указанный ключ. Если этот параметр имеет значение TRUE, метод сообщает об изменениях и его подразделов. Если параметр имеет значение FALSE, метод сообщает об изменениях только ключ.  
  
 *dwNotifyFilter*  
 Указывает, что набор флагов, определяющих, какие изменения, должна быть зарегистрирована. Этот параметр может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|Уведомите вызывающий объект, если при добавлении или удалении подраздела.|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|Уведомите вызывающий объект изменения в атрибутах ключа, например сведения о дескрипторе безопасности.|  
|REG_NOTIFY_CHANGE_LAST_SET|Уведомите вызывающий объект для изменения значения ключа. Это может включать добавление или удаление значения или изменение существующего значения.|  
|REG_NOTIFY_CHANGE_SECURITY|Уведомите вызывающий объект изменений в дескриптор безопасности ключа.|  
  
 `hEvent`  
 Дескриптор события. Если *bAsync* параметр имеет значение TRUE, метод возвращается немедленно, а изменения приводятся путем передачи сигналов это событие. Если `bAsync` имеет значение FALSE, `hEvent` учитывается.  
  
 `bAsync`  
 Задает флаг, указывающий, как метод сообщает об изменениях. Если этот параметр имеет значение TRUE, метод возвращается немедленно и сообщает об изменениях путем передачи сигналов указанного события. Если этот параметр имеет значение FALSE, метод не возвращает до произошли изменения. Если `hEvent` не указывает допустимого события, `bAsync` параметр не может иметь значение TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот метод не уведомить вызывающий объект, если указанный ключ удаляется.  
  
 Дополнительные сведения и пример программы см. в разделе [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892).  
  
##  <a name="open"></a>  CRegKey::Open  
 Вызовите этот метод, чтобы открыть указанный ключ и задать [m_hKey](#m_hkey) для обработки этого ключа.  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hKeyParent`  
 Дескриптор открытый ключ.  
  
 `lpszKeyName`  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом `hKeyParent`.  
  
 `samDesired`  
 Безопасный доступ для ключа. Значение по умолчанию — KEY_ALL_ACCESS. Список возможных значений и описаний см. в разделе [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае ошибка ненулевое значение, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Если `lpszKeyName` параметр имеет значение NULL или указывает на пустую строку, **откройте** открывает новый дескриптор ключ, обозначенный `hKeyParent`, но не закрывает все ранее открытый дескриптор.  
  
 В отличие от [CRegKey::Create](#create), **откройте** не создает указанным ключом, если он не существует.  
  
##  <a name="operator_hkey"></a>  CRegKey::operator HKEY  
 Преобразует `CRegKey` объект HKEY.  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="operator_eq"></a>  CRegKey::operator =  
 Оператор присвоения.  
  
```
CRegKey& operator= (CRegKey& key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на новый ключ.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор отсоединяет `key` из его текущего объекта и присваивает его `CRegKey` вместо этого объекта.  
  
##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue  
 Вызовите этот метод, чтобы получить двоичные данные для имени указанного значения.  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `pValue`  
 Указатель на буфер, получающий его значение.  
  
 `pnBytes`  
 Указатель на переменную, которая указывает размер в байтах буфера, на который указывает `pValue` параметра. Если метод возвращает значение, эта переменная содержит размер данных, копируемых в буфер.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если ссылка на данные, не относится к типу REG_BINARY, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует **RegQueryValueEx** и подтверждает, что возвращается правильный тип данных. В разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue  
 Этот метод вызывается для получения данных DWORD для имени указанного значения.  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `dwValue`  
 Указатель на буфер, получающий DWORD.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если ссылка на данные, не относится к типу REG_DWORD, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует **RegQueryValueEx** и подтверждает, что возвращается правильный тип данных. В разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue  
 Этот метод вызывается для получения данных для имени указанного значения GUID.  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `guidValue`  
 Указатель на переменную, которая получает идентификатор GUID.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если в данных не является допустимым идентификатором GUID, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `CRegKey::QueryStringValue` и преобразует строку в GUID с помощью [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589).  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным.  
  
##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue  
 Этот метод используется для получения данных, состоящее из нескольких строк для имени указанного значения.  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `pszValue`  
 Указатель на буфер, получающий состоящее из нескольких строк данных. Multistring представляет собой массив строк, завершающуюся значением null, заканчивающихся двумя символами null.  
  
 `pnChars`  
 Размер в TCHARs буфера, на который указывает `pszValue`. При возвращении метода `pnChars` содержит размер в TCHARs из multistring извлечения, включая завершающий символ null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если ссылка на данные, не относится к типу REG_MULTI_SZ, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует **RegQueryValueEx** и подтверждает, что возвращается правильный тип данных. В разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue  
 Этот метод вызывается для получения данных QWORD для имени указанного значения.  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `qwValue`  
 Указатель на буфер, получающий QWORD.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если ссылка на данные, не относится к типу REG_QWORD, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует **RegQueryValueEx** и подтверждает, что возвращается правильный тип данных. В разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue  
 Этот метод используется для извлечения строковых данных для имени указанного значения.  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса.  
  
 `pszValue`  
 Указатель на буфер, получающий данные строки.  
  
 `pnChars`  
 Размер в TCHARs буфера, на который указывает `pszValue`. При возвращении метода `pnChars` содержит размер в TCHARs строки извлечения, включая завершающий символ null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метода, возвращается код ошибки ненулевое значение, определенный в WINERROR. З. Если ссылка на данные, не относится к типу REG_SZ, возвращается ERROR_INVALID_DATA. Если метод возвращает ERROR_MORE_DATA, `pnChars` равно нулю, не необходимый размер буфера в байтах.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует **RegQueryValueEx** и подтверждает, что возвращается правильный тип данных. В разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывать строки, которые являются нулем. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryvalue"></a>  CRegKey::QueryValue  
 Этот метод вызывается для получения данных для указанного значения поля [m_hKey](#m_hkey). Более ранние версии этот метод больше не поддерживаются и помечаются как **ATL_DEPRECATED**.  
  
```
LONG QueryValue(  
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель нулем строка, содержащая имя значения для запроса. Если `pszValueName` имеет значение NULL или пустую строку «», метод возвращает значение, тип и данных для ключа неименованными или значение по умолчанию, если какой-либо.  
  
 `pdwType`  
 Указатель на переменную, которая получает код, указывающий тип данных, хранящихся в указанное значение. `pdwType` Параметр может иметь значение NULL, если код типа не требуется.  
  
 `pData`  
 Указатель на буфер, получающий его значение. Этот параметр может иметь значение NULL, если данные не требуется.  
  
 `pnBytes`  
 Указатель на переменную, которая указывает размер в байтах буфера, на который указывает `pData` параметра. Если метод возвращает значение, переменная, которая содержит размер данных, копируемых в *pData.*  
  
 `dwValue`  
 Поле значения числовых данных.  
  
 `lpszValueName`  
 Указывает, должны запрашиваться в поле значение.  
  
 `szValue`  
 Строковые данные в поле значение.  
  
 `pdwCount`  
 Размер строковых данных. Его значение изначально установлено значение размера `szValue` буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае — код ошибки ненулевое значение, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Две версии исходной `QueryValue` больше не поддерживаются и отмечаются как **ATL_DEPRECATED**. Компилятор выдаст предупреждение, если используются эти формы.  
  
 Оставшиеся вызовы метода RegQueryValueEx.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указать любое расположение реестра, возможно чтение данных, которое не может быть доверенным. Кроме того, функция RegQueryValueEx, используемая этим методом не обрабатывает явно строк, являющихся `NULL` завершен. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey  
 Этот метод используется для удаления указанного ключа из реестра и явным образом удалить все разделы.  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszKey*  
 Указывает имя ключа для удаления. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае ошибка ненулевое значение, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Если раздел содержит подразделы, необходимо вызвать этот метод, чтобы удалить ключ.  
  
##  <a name="setbinaryvalue"></a>  CRegKey::SetBinaryValue  
 Вызовите этот метод, чтобы задать двоичное значение раздела реестра.  
  
```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `pValue`  
 Указатель на буфер, содержащий данные для хранения с именем указанное значение.  
  
 `nBytes`  
 Указывает размер в байтах данных, на который указывает `pValue` параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue  
 Этот метод используется для задания значения реестра DWORD.  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `dwValue`  
 Данные DWORD для хранения с именем указанное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue  
 Этот метод используется для задания значения GUID раздела реестра.  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `guidValue`  
 Ссылка на идентификатор GUID для хранения с заданным именем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `CRegKey::SetStringValue` и преобразует GUID в строку с помощью [StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893).  
  
##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue  
 Этот метод используется для хранения данных в поле указанное значение указанного ключа.  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszKeyName`  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
 `lpszValue`  
 Задает данные для хранения. Этот параметр должен быть НЕПУСТЫМ.  
  
 `lpszValueName`  
 Указывает задаваемое полем значения. Если значение поля с таким именем уже существует в ключе, он добавляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае — код ошибки ненулевое значение, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для создания или открытия `lpszKeyName` ключа и сохранения `lpszValue` данные в `lpszValueName` значение поля.  
  
##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity  
 Этот метод используется для настройки безопасности раздела реестра.  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `si`  
 Указывает компоненты дескриптор безопасности для задания. Значение может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|Задает список ключей управления доступом (DACL). Ключ должен иметь доступ WRITE_DAC или вызывающий процесс должен быть владельцем объекта.|  
|GROUP_SECURITY_INFORMATION|Задает ключ основной группы идентификатор безопасности (SID). Ключ должен иметь доступ WRITE_OWNER или вызывающий процесс должен быть владельцем объекта.|  
|OWNER_SECURITY_INFORMATION|Задает ключ владельца SID. Ключ должен иметь доступ WRITE_OWNER или вызывающий процесс должен быть владельцем объекта или иметь привилегию SE_TAKE_OWNERSHIP_NAME включена.|  
|SACL_SECURITY_INFORMATION|Задает ключ system-списка управления доступом (SACL). Ключ должен иметь ACCESS_SYSTEM_SECURITY доступ. Правильный способ получить такой доступ является возможность SE_SECURITY_NAME [прав](http://msdn.microsoft.com/library/windows/desktop/aa379306) в вызывающей текущего маркера доступа, открыть дескриптор для доступа к ACCESS_SYSTEM_SECURITY, а затем отключить право доступа.|  
  
 `psd`  
 Указатель на [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) структура, которая задает атрибуты безопасности для задания для указанного ключа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Задает атрибуты ключа безопасности. В разделе [RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314) для получения дополнительных сведений.  
  
##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue  
 Вызовите этот метод, чтобы задать значение, состоящее из нескольких строк раздела реестра.  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `pszValue`  
 Указатель на данные, состоящее из нескольких строк для хранения с заданным именем. Multistring представляет собой массив строк, завершающуюся значением null, заканчивающихся двумя символами null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue  
 Этот метод используется для задания значения реестра QWORD.  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `qwValue`  
 QWORD данных для хранения с заданным именем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setstringvalue"></a>  CRegKey::SetStringValue  
 Вызовите этот метод, чтобы задать строковое значение реестра.  
  
```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует, метод добавляет к ключу.  
  
 `pszValue`  
 Указатель на данные строки должны храниться с именем указанное значение.  
  
 `dwType`  
 Тип строки для записи в реестр: REG_SZ (по умолчанию) или REG_EXPAND_SZ (для типа multistring).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращаемое значение равно ERROR_SUCCESS. Если метод завершается ошибкой, возвращается код ошибки ненулевое значение, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx) для записи значения в реестр.  
  
##  <a name="setvalue"></a>  CRegKey::SetValue  
 Этот метод вызывается для хранения данных в поле указанного значения [m_hKey](#m_hkey). Более ранние версии этот метод больше не поддерживаются и помечаются как **ATL_DEPRECATED**.  
  
```
LONG SetValue(  
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();
    
static LONG WINAPI SetValue(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(  
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(  
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```  
  
### <a name="parameters"></a>Параметры  
 `pszValueName`  
 Указатель на строку, содержащую имя, значение которого требуется задать. Значение с таким именем не существует в ключе, метод добавляет к ключу. Если `pszValueName` имеет значение NULL или пустую строку «», метод задает тип и данных для ключа неименованными или значение по умолчанию.  
  
 `dwType`  
 Указывает код, указывающий тип данных, на который указывает `pValue` параметра.  
  
 `pValue`  
 Указатель на буфер, содержащий данные для хранения с именем указанное значение.  
  
 `nBytes`  
 Указывает размер в байтах данных, на который указывает `pValue` параметра. Если данные имеют тип REG_SZ, REG_MULTI_SZ или REG_EXPAND_SZ `nBytes` должен включать размер символа завершающего нуля.  
  
 `hKeyParent`  
 Дескриптор открытый ключ.  
  
 `lpszKeyName`  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом `hKeyParent`.  
  
 `lpszValue`  
 Задает данные для хранения. Этот параметр должен быть НЕПУСТЫМ.  
  
 `lpszValueName`  
 Указывает задаваемое полем значения. Если значение поля с таким именем уже существует в ключе, он добавляется.  
  
 `dwValue`  
 Задает данные для хранения.  
  
 `bMulti`  
 Если значение равно false, указывает, что строка имеет тип REG_SZ. Значение true указывает, что строка является multistring типа REG_MULTI_SZ.  
  
 `nValueLen`  
 Если `bMulti` имеет значение true, `nValueLen` длина *lpszValue* строки в символах. Если `bMulti` имеет значение false, значение -1 указывает, что метод будет вычислить длину автоматически.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает ERROR_SUCCESS; в противном случае — код ошибки ненулевое значение, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Две версии исходной `SetValue` , помечаются как **ATL_DEPRECATED** и больше не может использоваться. Компилятор выдаст предупреждение, если используются эти формы.  
  
 Третий метод вызывает [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923).  
  
## <a name="see-also"></a>См. также  
 [Образец DCOM](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
