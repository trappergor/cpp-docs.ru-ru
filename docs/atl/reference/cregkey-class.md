---
title: Класс CRegKey | Документация Майкрософт
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
ms.openlocfilehash: b2f295b6bf54077ad131176092b06dbeca7a2201
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572889"
---
# <a name="cregkey-class"></a>Класс CRegKey
Этот класс содержит методы для работы записей в системном реестре.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CRegKey
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|Конструктор.|  
|[CRegKey:: ~ CRegKey](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|Вызовите этот метод для присоединения открываемый раздел HKEY `CRegKey` объекта, задав [m_hKey](#m_hkey) член дескриптор `hKey`.|  
|[CRegKey::Close](#close)|Вызовите этот метод для освобождения [m_hKey](#m_hkey) член обработки и ему присвоено значение NULL.|  
|[CRegKey::Create](#create)|Вызовите этот метод для создания указанным ключом, если он отсутствует в виде подраздела `hKeyParent`.|  
|[CRegKey::DeleteSubKey](#deletesubkey)|Этот метод используется для удаления указанного ключа из реестра.|  
|[CRegKey::DeleteValue](#deletevalue)|Вызовите этот метод, чтобы удалить поле из значения [m_hKey](#m_hkey).|  
|[CRegKey::Detach](#detach)|Вызовите этот метод для отсоединения [m_hKey](#m_hkey) дескриптор член из `CRegKey` и задайте `m_hKey` значение NULL.|  
|[CRegKey::EnumKey](#enumkey)|Вызовите этот метод, чтобы пронумеровать подключи открыть раздел реестра.|  
|[CRegKey::Flush](#flush)|Вызовите этот метод для записи всех атрибутов открыть раздел реестра в реестр.|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|Вызовите этот метод, чтобы извлечь копию дескриптора безопасности, защищающий ключ открыть реестр.|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Этот метод уведомляет вызывающего о внесении изменений в атрибуты или содержимое открыть раздел реестра.|  
|[CRegKey::Open](#open)|Вызовите этот метод, чтобы открыть указанный ключ и значение [m_hKey](#m_hkey) для обработки этого ключа.|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Этот метод используется для получения двоичных данных для имени указанного значения.|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Этот метод используется для получения данных DWORD для имени указанного значения.|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Этот метод используется для получения данных GUID для имени указанного значения.|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Этот метод используется для получения состоящие из нескольких строк данных для имени указанного значения.|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Этот метод используется для получения данных QWORD для имени указанного значения.|  
|[CRegKey::QueryStringValue](#querystringvalue)|Этот метод используется для извлечения строковых данных для имени указанного значения.|  
|[CRegKey::QueryValue](#queryvalue)|Вызовите этот метод для извлечения данных для поля указанное значение [m_hKey](#m_hkey). Более ранних версиях этот метод больше не поддерживаются и помечаются как ATL_DEPRECATED.|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Вызовите этот метод для удаления указанного ключа из реестра и явным образом удалить все разделы.|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Вызовите этот метод, чтобы задать двоичное значение раздела реестра.|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|Вызовите этот метод, чтобы задать значение DWORD раздела реестра.|  
|[CRegKey::SetGUIDValue](#setguidvalue)|Этот метод используется для задания значения GUID раздела реестра.|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|Вызовите этот метод для настройки безопасности реестра.|  
|[CRegKey::SetKeyValue](#setkeyvalue)|Этот метод используется для хранения данных в поле заданное значение указанного ключа.|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Этот метод используется для задания multistring значения раздела реестра.|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|Этот метод используется для задания значения реестра QWORD.|  
|[CRegKey::SetStringValue](#setstringvalue)|Вызовите этот метод, чтобы задать строковое значение реестра.|  
|[CRegKey::SetValue](#setvalue)|Вызовите этот метод для хранения данных в поле указанного значения [m_hKey](#m_hkey). Более ранних версиях этот метод больше не поддерживаются и помечаются как ATL_DEPRECATED.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|Преобразует `CRegKey` объект HKEY.|  
|[CRegKey::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|Содержит дескриптор раздела реестра, связанные с `CRegKey` объекта.|  
|[CRegKey::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект|  
  
## <a name="remarks"></a>Примечания  
 `CRegKey` Предоставляет методы для создания и удаления ключей и значений в системном реестре. Реестр содержит набор определений для компонентов системы, такие как номера версий программного обеспечения, логических физических сопоставлений установленном оборудовании и COM-объектов, связанных с установкой.  
  
 `CRegKey` предоставляет интерфейс программирования для системного реестра для данного компьютера. Например, чтобы открыть определенного раздела реестра, вызвать `CRegKey::Open`. Чтобы получить или изменять значения данных, вызовите `CRegKey::QueryValue` или `CRegKey::SetValue`, соответственно. Чтобы закрыть ключ, вызовите `CRegKey::Close`.  
  
 Если закрыть ключ, его данные реестра записывается (Сброс) на жесткий диск. Этот процесс может занять несколько секунд. Если приложение должно явным образом записывать данные реестра на жесткий диск, можно вызвать [функция RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) функции Win32. Тем не менее `RegFlushKey` использует много системных ресурсов и должен вызываться только в том случае, если это абсолютно необходимо.  
  
> [!IMPORTANT]
>  Все методы, позволяющие вызывающему объекту указать расположение в реестре существует возможность считывать данные, которые не могут быть доверенными. Методы, которые позволяют использовать [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) следует принять во внимание, что эта функция явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>  CRegKey::Attach  
 Вызовите этот метод для присоединения открываемый раздел HKEY `CRegKey` объекта, задав [m_hKey](#m_hkey) член дескриптор *hKey*.  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *открываемый раздел hKey*  
 Дескриптор раздела реестра.  
  
### <a name="remarks"></a>Примечания  
 `Attach` проверяет Если `m_hKey` отлично от NULL.  
  
##  <a name="close"></a>  CRegKey::Close  
 Вызовите этот метод для освобождения [m_hKey](#m_hkey) член обработки и ему присвоено значение NULL.  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае возвращает значение ошибки.  
  
##  <a name="create"></a>  CRegKey::Create  
 Вызовите этот метод для создания указанным ключом, если он отсутствует в виде подраздела *hKeyParent*.  
  
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
 *hKeyParent*  
 Дескриптор открытый ключ.  
  
 *lpszKeyName*  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом *hKeyParent*.  
  
 *lpszClass*  
 Указывает класс ключа, который требуется создать или открыть. Значение по умолчанию — REG_NONE.  
  
 *dwOptions*  
 Параметры для ключа. Значение по умолчанию — REG_OPTION_NON_VOLATILE. Список возможных значений и описаний, см. в разделе [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) в пакете Windows SDK.  
  
 *samDesired*  
 Безопасный доступ для ключа. Значение по умолчанию — KEY_READ &#124; KEY_WRITE. Список возможных значений и описаний, см. в разделе `RegCreateKeyEx`.  
  
 *lpSecAttr*  
 Указатель на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структуру, которая указывает, может ли дескриптор ключа наследоваться дочерним процессом. По умолчанию этот параметр имеет значение NULL (что означает, что дескриптор не наследуется).  
  
 *lpdwDisposition*  
 [out] Если не NULL, извлекает REG_CREATED_NEW_KEY (если ключ не существовал и был создан) или REG_OPENED_EXISTING_KEY (если ключ существовал и был открыт).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS и открывает ключ. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 `Create` Задает [m_hKey](#m_hkey) члена для обработки этого ключа.  
  
##  <a name="cregkey"></a>  CRegKey::CRegKey  
 Конструктор.  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *key*  
 Ссылка на объект `CRegKey`.  
  
 *открываемый раздел hKey*  
 Дескриптор раздела реестра.  
  
 *pTM*  
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
 *lpszSubKey*  
 Имя удаляемого раздела. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 `DeleteSubKey` можно удалить только ключ, который не имеет подразделов. Если раздел содержит подразделы, вызовите [RecurseDeleteKey](#recursedeletekey) вместо этого.  
  
##  <a name="deletevalue"></a>  CRegKey::DeleteValue  
 Вызовите этот метод, чтобы удалить поле из значения [m_hKey](#m_hkey).  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszValue*  
 Задает поле значений для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
##  <a name="detach"></a>  CRegKey::Detach  
 Вызовите этот метод для отсоединения [m_hKey](#m_hkey) дескриптор член из `CRegKey` и задайте `m_hKey` значение NULL.  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Открываемый раздел HKEY связанные с `CRegKey` объекта.  
  
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
 *iIndex*  
 Индекс подраздела. Этот параметр должен быть равен нулю, при первом вызове и затем увеличивается на единицу при последующих вызовах  
  
 *pszName*  
 Указатель на буфер, получающий имя подраздела, включая завершающий нуль-символ. Только имя подраздела копируется в буфер, а не полного ключа иерархию.  
  
 *pnNameLength*  
 Указатель на переменную, которая задает размер в TCHARs из буфера, заданного *pszName* параметра. Размер должен учитывать завершающий нуль-символ. Когда этот метод возвращает, переменной, на которые указывают *pnNameLength* содержит число символов, сохраненных в буфере. Возвращенное число не включает завершающий нуль-символ.  
  
 *pftLastWriteTime*  
 Указатель на переменную, которая получает время перечисляемых подраздел последней операции записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Чтобы пронумеровать подключи, вызовите `CRegKey::EnumKey` с нулевой индекс. Увеличьте значение индекса и повторите этот метод возвращает ERROR_NO_MORE_ITEMS. Дополнительные сведения см. в разделе [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) в пакете Windows SDK.  
  
##  <a name="flush"></a>  CRegKey::Flush  
 Вызовите этот метод для записи всех атрибутов открыть раздел реестра в реестр.  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) в пакете Windows SDK.  
  
##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity  
 Вызовите этот метод, чтобы извлечь копию дескриптора безопасности, защищающий ключ открыть реестр.  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *SI*  
 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) значение, указывающее сведения запрошенного типа безопасности.  
  
 *PSD*  
 Указатель на буфер, получающий копию дескриптора запрошенного типа безопасности.  
  
 *pnBytes*  
 Размер в байтах буфера, на которые указывают *psd*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращаемое значение — ненулевой код ошибки, определенный в WINERROR. З.  
  
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
 Этот метод уведомляет вызывающего о внесении изменений в атрибуты или содержимое открыть раздел реестра.  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *bWatchSubtree*  
 Задает флаг, указывающий, следует ли сообщать изменения в указанные ключ и все его подразделы или только указанный ключ. Если этот параметр имеет значение TRUE, метод сообщает об изменениях и подразделах реестра. Если параметр имеет значение FALSE, метод сообщает об изменениях только ключ.  
  
 *dwNotifyFilter*  
 Указывает, что набор флагов, определяющие, какие изменения должны выводиться. Этот параметр может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|Уведомить вызывающий объект, если при добавлении или удалении подраздела.|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|Уведомить вызывающий объект изменения в атрибутах ключа, например данные дескриптора безопасности.|  
|REG_NOTIFY_CHANGE_LAST_SET|Уведомить вызывающий объект изменений в значение ключа. Это могут быть Добавление или удаление значения или изменения существующего значения.|  
|REG_NOTIFY_CHANGE_SECURITY|Уведомить вызывающий объект изменений в дескриптор безопасности ключа.|  
  
 *hEvent*  
 Дескриптор события. Если *bAsync* параметр имеет значение TRUE, метод немедленно возвращает и изменения передаются, обмениваясь сигналами это событие. Если *bAsync* имеет значение FALSE, *hEvent* учитывается.  
  
 *bAsync*  
 Задает флаг, указывающий, как метод сообщает об изменениях. Если этот параметр имеет значение TRUE, метод возвращается немедленно и сообщает об изменениях, обмениваясь сигналами указанное событие. Если этот параметр имеет значение FALSE, метод не возвращает пока не произошло изменение. Если *hEvent* не содержит допустимого события, *bAsync* параметр не может иметь значение TRUE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот метод не уведомляет вызывающего объекта, если указанный ключ удаляется.  
  
 Дополнительные сведения и пример программы, см. в разделе [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892).  
  
##  <a name="open"></a>  CRegKey::Open  
 Вызовите этот метод, чтобы открыть указанный ключ и значение [m_hKey](#m_hkey) для обработки этого ключа.  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hKeyParent*  
 Дескриптор открытый ключ.  
  
 *lpszKeyName*  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом *hKeyParent*.  
  
 *samDesired*  
 Безопасный доступ для ключа. Значение по умолчанию — KEY_ALL_ACCESS. Список возможных значений и описаний, см. в разделе [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае — значение ошибки, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Если *lpszKeyName* параметр имеет значение NULL или точки пустую строку, `Open` открывает новый дескриптор ключа определяется *hKeyParent*, но не закрывает любой ранее открытый дескриптор.  
  
 В отличие от [CRegKey::Create](#create), `Open` не создаст указанным ключом, если он не существует.  
  
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
 *key*  
 Ключ для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на новый ключ.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор отсоединяет *ключ* из его текущего объекта и присваивает его `CRegKey` вместо этого объекта.  
  
##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue  
 Этот метод используется для получения двоичных данных для имени указанного значения.  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *pValue*  
 Указатель на буфер, получающий его значение.  
  
 *pnBytes*  
 Указатель на переменную, которая указывает размер в байтах буфера, на которые указывают *pValue* параметра. При возвращении метода эта переменная содержит размер данных, копируемых в буфер.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если соответствующими данными не типа REG_BINARY, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `RegQueryValueEx` и подтверждает, что возвращается правильный тип данных. См. в разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue  
 Этот метод используется для получения данных DWORD для имени указанного значения.  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *dwValue*  
 Указатель на буфер, получающий DWORD.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если соответствующими данными не типа REG_DWORD, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `RegQueryValueEx` и подтверждает, что возвращается правильный тип данных. См. в разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue  
 Этот метод используется для получения данных GUID для имени указанного значения.  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *guidValue*  
 Указатель на переменную, которая получает идентификатор GUID.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если данных не является допустимым идентификатором GUID, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `CRegKey::QueryStringValue` и преобразует строку в идентификатор GUID с помощью [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589).  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным.  
  
##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue  
 Этот метод используется для получения состоящие из нескольких строк данных для имени указанного значения.  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *размер pszValue*  
 Указатель на буфер, получающий данные, состоящие из нескольких строк. Мультистрока представляет собой массив строк, завершающаяся нулем, завершаемый двумя символами null.  
  
 *pnChars*  
 Размер в TCHARs буфера, на которые указывают *размер pszValue*. При возвращении метода *pnChars* содержит размер в TCHARs из мультистрока извлечена, включая завершающий нуль-символ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если данных не имеет тип REG_MULTI_SZ, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `RegQueryValueEx` и подтверждает, что возвращается правильный тип данных. См. в разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue  
 Этот метод используется для получения данных QWORD для имени указанного значения.  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *qwValue*  
 Указатель на буфер, получающий QWORD.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если данных не имеет тип REG_QWORD, возвращается ERROR_INVALID_DATA.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `RegQueryValueEx` и подтверждает, что возвращается правильный тип данных. См. в разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue  
 Этот метод используется для извлечения строковых данных для имени указанного значения.  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса.  
  
 *размер pszValue*  
 Указатель на буфер, получающий данные строки.  
  
 *pnChars*  
 Размер в TCHARs буфера, на которые указывают *размер pszValue*. При возвращении метода *pnChars* содержит размер в TCHARs строки извлечена, включая завершающий нуль-символ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается ERROR_SUCCESS. Если не удается прочитать значение метод, он возвращает код ненулевого значения ошибки, определенный в WINERROR. З. Если данных не имеет тип REG_SZ, возвращается ERROR_INVALID_DATA. Если метод возвращает ERROR_MORE_DATA, *pnChars* равно нулю, не необходимый размер буфера в байтах.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `RegQueryValueEx` и подтверждает, что возвращается правильный тип данных. См. в разделе [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) для получения дополнительных сведений.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) функция, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="queryvalue"></a>  CRegKey::QueryValue  
 Вызовите этот метод для извлечения данных для поля указанное значение [m_hKey](#m_hkey). Более ранних версиях этот метод больше не поддерживаются и помечаются как ATL_DEPRECATED.  
  
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
 *pszValueName*  
 Указатель на заканчивающуюся нулем строку, содержащая имя значения для запроса. Если *pszValueName* имеет значение NULL или пустая строка, «», метод возвращает тип и данных для ключа неименованными или значение по умолчанию, если таковое имеется.  
  
 *pdwType*  
 Указатель на переменную, которая получает код, указывающий тип данных, хранящихся в указанное значение. *PdwType* параметр может иметь значение NULL, если код типа не требуется.  
  
 *pData*  
 Указатель на буфер, получающий его значение. Этот параметр может иметь значение NULL, если данные не требуется.  
  
 *pnBytes*  
 Указатель на переменную, которая указывает размер в байтах буфера, на которые указывают *pData* параметра. При возвращении метода эта переменная содержит размер данных, копируемых в *pData.*  
  
 *dwValue*  
 Поле значения числовых данных.  
  
 *lpszValueName*  
 Задает поле значений должны запрашиваться.  
  
 *szValue*  
 Поле значения строковых данных.  
  
 *pdwCount*  
 Размер строковых данных. Его значение первоначально задается размер *szValue* буфера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае ненулевой код ошибки, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Две исходные версии `QueryValue` больше не поддерживаются и помечаются как ATL_DEPRECATED. Компилятор выдаст предупреждение, если используются эти формы.  
  
 Оставшиеся вызовы методов RegQueryValueEx.  
  
> [!IMPORTANT]
>  Этот метод позволяет вызывающему объекту указывать любое расположение реестра, возможно чтение данных, который не может быть доверенным. Кроме того функция RegQueryValueEx, используемая этим методом явно не обрабатывает строки, которые являются НУЛЕВЫМ байтом. Оба условия должны проверяться вызывающим кодом.  
  
##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey  
 Вызовите этот метод для удаления указанного ключа из реестра и явным образом удалить все разделы.  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszKey*  
 Имя удаляемого раздела. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае — значение ошибки, определенные в WINERROR. З.  
  
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
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *pValue*  
 Указатель на буфер, содержащий данные для хранения с именем указанного значения.  
  
 *nBytes*  
 Указывает размер в байтах информации, на которые указывают *pValue* параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue  
 Вызовите этот метод, чтобы задать значение DWORD раздела реестра.  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *dwValue*  
 Данные DWORD для хранения с именем указанного значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue  
 Этот метод используется для задания значения GUID раздела реестра.  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *guidValue*  
 Ссылка на идентификатор GUID для хранения с именем указанного значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует `CRegKey::SetStringValue` и преобразует GUID в строку с помощью [StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893).  
  
##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue  
 Этот метод используется для хранения данных в поле заданное значение указанного ключа.  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszKeyName*  
 Задает имя ключа, который требуется создать или открыть. Это имя должно быть подразделом [m_hKey](#m_hkey).  
  
 *lpszValue*  
 Указывает данные для сохранения. Этот параметр должен иметь отличное от NULL.  
  
 *lpszValueName*  
 Задает поле значение, устанавливаемое значение. Если значение поля с таким именем еще не существует в ключе, он добавляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае ненулевой код ошибки, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для создания или открытия *lpszKeyName* ключа и хранить *lpszValue* данные в *lpszValueName* поле значения.  
  
##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity  
 Вызовите этот метод для настройки безопасности реестра.  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *SI*  
 Указывает компоненты дескриптора безопасности для задания. Значение может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|Задает список управления доступом для ключа (DACL). Ключ должен иметь доступа WRITE_DAC или вызывающий процесс должен быть владельцем объекта.|  
|GROUP_SECURITY_INFORMATION|Задает ключ основной групповой идентификатор безопасности (SID). Ключ должен иметь доступ WRITE_OWNER или вызывающий процесс должен быть владельцем объекта.|  
|OWNER_SECURITY_INFORMATION|Задает владельца для ключа безопасности. Ключ должен иметь доступ WRITE_OWNER или вызывающий процесс должен быть владельцем объекта или иметь активировать права SE_TAKE_OWNERSHIP_NAME.|  
|SACL_SECURITY_INFORMATION|Задает список управления доступом (SACL) для ключа системы. Ключ должен иметь доступ ACCESS_SYSTEM_SECURITY. Правильный способ получить такой доступ является возможность SE_SECURITY_NAME [привилегий](http://msdn.microsoft.com/library/windows/desktop/aa379306) в вызывающей стороны текущего маркера доступа, открыть дескриптор ACCESS_SYSTEM_SECURITY доступ, а затем отключить привилегии.|  
  
 *PSD*  
 Указатель на [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) структура, задающая атрибуты безопасности для задания для указанного ключа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Задает атрибуты для ключа безопасности. См. в разделе [RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314) для получения дополнительных сведений.  
  
##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue  
 Этот метод используется для задания multistring значения раздела реестра.  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *размер pszValue*  
 Указатель на данные, состоящие из нескольких строк для хранения с именем указанного значения. Мультистрока представляет собой массив строк, завершающаяся нулем, завершаемый двумя символами null.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) для записи значения в реестр.  
  
##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue  
 Этот метод используется для задания значения реестра QWORD.  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *qwValue*  
 QWORD данные, сохраняемые с именем указанного значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
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
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем не существует, метод добавляет его к ключу.  
  
 *размер pszValue*  
 Указатель на строку данных для хранения с именем указанного значения.  
  
 *dwType*  
 Тип строка для записи в реестр: REG_SZ (по умолчанию) или REG_EXPAND_SZ (для нескольких строк).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращаемое значение равно ERROR_SUCCESS. При сбое метода, возвращается код ненулевого значения ошибки, определенный в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) для записи значения в реестр.  
  
##  <a name="setvalue"></a>  CRegKey::SetValue  
 Вызовите этот метод для хранения данных в поле указанного значения [m_hKey](#m_hkey). Более ранних версиях этот метод больше не поддерживаются и помечаются как ATL_DEPRECATED.  
  
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
 *pszValueName*  
 Указатель на строку, содержащую имя присваиваемое значение. Если значение с таким именем уже отсутствует в ключе, метод добавляет его к ключу. Если *pszValueName* имеет значение NULL или пустая строка, «», метод устанавливает тип и данных для ключа неименованными или значение по умолчанию.  
  
 *dwType*  
 Указывает код, указывающий тип данных, на которые указывают *pValue* параметра.  
  
 *pValue*  
 Указатель на буфер, содержащий данные для хранения с именем указанного значения.  
  
 *nBytes*  
 Указывает размер в байтах информации, на которые указывают *pValue* параметра. Если данные имеют тип REG_SZ, REG_EXPAND_SZ или REG_MULTI_SZ, *nBytes* должен включать размер завершающего нуль-символа.  
  
 *hKeyParent*  
 Дескриптор открытый ключ.  
  
 *lpszKeyName*  
 Указывает имя ключа для создания или открытия. Это имя должно быть подразделом *hKeyParent*.  
  
 *lpszValue*  
 Указывает данные для сохранения. Этот параметр должен иметь отличное от NULL.  
  
 *lpszValueName*  
 Задает поле значение, устанавливаемое значение. Если значение поля с таким именем еще не существует в ключе, он добавляется.  
  
 *dwValue*  
 Указывает данные для сохранения.  
  
 *bMulti*  
 Если значение равно false, указывает, что строка имеет тип REG_SZ. Если значение равно true, указывает, что строка является мультистрока типа REG_MULTI_SZ.  
  
 *nValueLen*  
 Если *bMulti* имеет значение true, *nValueLen* длина *lpszValue* строки в символах. Если *bMulti* имеет значение false, значение -1 указывает, что метод будет вычислять длину автоматически.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ERROR_SUCCESS; в противном случае ненулевой код ошибки, определенные в WINERROR. З.  
  
### <a name="remarks"></a>Примечания  
 Две исходные версии `SetValue` отмечены как ATL_DEPRECATED и больше не используется. Компилятор выдаст предупреждение, если используются эти формы.  
  
 Третий метод вызовы [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923).  
  
## <a name="see-also"></a>См. также  
 [Образец DCOM](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
