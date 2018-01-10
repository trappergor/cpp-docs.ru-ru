---
title: "Класс CSid | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs: C++
helpviewer_keywords: CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3915206f0b05e33d5e13e41871a597ea7278ee8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="csid-class"></a>Класс CSid
Этот класс является оболочкой для `SID` структуры (идентификатором безопасности).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSid
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|Массив объектов `CSid`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSid::CSid](#csid)|Конструктор.|  
|[Идентификатор CSid:: ~ CSid](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|Возвращает имя учетной записи, связанной с `CSid` объекта.|  
|[CSid::Domain](#domain)|Возвращает имя домена, связанного с `CSid` объекта.|  
|[CSid::EqualPrefix](#equalprefix)|Тесты `SID` префиксы (идентификатором безопасности) для проверки на равенство.|  
|[CSid::GetLength](#getlength)|Возвращает длину `CSid` объекта.|  
|[CSid::GetPSID](#getpsid)|Возвращает указатель на `SID` структуры.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель на **SID_IDENTIFIER_AUTHORITY** структуры.|  
|[CSid::GetSubAuthority](#getsubauthority)|Возвращает указанный данных неверна в **SID** структуры.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Возвращает число данных неверна.|  
|[CSid::IsValid](#isvalid)|Тесты `CSid` объекта на допустимость.|  
|[CSid::LoadAccount](#loadaccount)|Обновления `CSid` объекта по заданному имени учетной записи и домен или существующий `SID` структуры.|  
|[CSid::Sid](#sid)|Возвращает строку идентификатора.|  
|[CSid::SidNameUse](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Оператор присвоения.|  
|[оператор const SID *](#operator_const_sid__star)|Приведение `CSid` объекта в указатель на `SID` структуры.|  
  
### <a name="global-operators"></a>Глобальные операторы  
  
|||  
|-|-|  
|[оператор ==](#operator_eq_eq)|Проверяет два объекта дескриптора безопасности для проверки на равенство|  
|[оператор! =](#operator_neq)|Проверяет два объекта дескриптора безопасности для проверки на неравенство|  
|[оператор\<](#operator_lt_)|Сравнивает относительные значение два объекта дескриптора безопасности.|  
|[оператор >](#operator_gt_)|Сравнивает относительные значение два объекта дескриптора безопасности.|  
|[оператор\<=](#operator_lt__eq)|Сравнивает относительные значение два объекта дескриптора безопасности.|  
|[оператор > =](#operator_gt__eq)|Сравнивает относительные значение два объекта дескриптора безопасности.|  
  
## <a name="remarks"></a>Примечания  
 `SID` Структуры — это структура переменной длины, используемые для уникальной идентификации пользователей или групп.  
  
 Приложения, которые не следует изменять `SID` структуры непосредственно, но вместо этого используйте методы, предоставленные в данный класс-оболочка. См. также [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), и [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="accountname"></a>CSid::AccountName  
 Возвращает имя учетной записи, связанной с `CSid` объекта.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывает имя учетной записи.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается найти имя для указанного `SID` (идентификатором безопасности). Дополнительные сведения см. в разделе [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Если нет имени учетной записи для `SID` можно найти, `AccountName` возвращает пустую строку. Это может произойти, если время ожидания сети предотвращает определение имени этого метода. Это также справедливо для идентификаторов безопасности без соответствующего имени учетной записи, например входа в систему `SID` , идентифицирующим сеанс входа в систему.  
  
##  <a name="csid"></a>CSid::CSid  
 Конструктор.  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий `CSid` объекта или `SID` структуры (идентификатором безопасности).  
  
 *IdentifierAuthority*  
 Центр сертификации.  
  
 *nSubAuthorityCount*  
 Счетчик данных неверна.  
  
 `pszAccountName`  
 Имя учетной записи.  
  
 `pszSystem`  
 Имя системы. Эта строка может быть имя удаленного компьютера. Если значение свойства равно NULL, вместо него используется локальная система.  
  
 `pSid`  
 Указатель на `SID` структуры.  
  
### <a name="remarks"></a>Примечания  
 Конструктор инициализирует `CSid` объекта, присвоив внутренние данные-член *SidTypeInvalid*, или скопировать параметры из существующего `CSid`, `SID`, или существующую учетную запись.  
  
 Если происходит сбой инициализации, конструктор создаст исключение [CAtlException класса](../../atl/reference/catlexception-class.md).  
  
##  <a name="dtor"></a>Идентификатор CSid:: ~ CSid  
 Деструктор  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные из объекта.  
  
##  <a name="csidarray"></a>CSid::CSidArray  
 Массив [CSid](../../atl/reference/csid-class.md) объектов.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа задает тип массива, который может использоваться для получения идентификаторов безопасности из ACL (список управления доступом). В разделе [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="domain"></a>CSid::Domain  
 Возвращает имя домена, связанного с `CSid` объекта.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывающей на домен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается найти имя для указанного `SID` (идентификатором безопасности). Дополнительные сведения см. в разделе [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Если нет имени учетной записи для `SID` можно найти, **домена** Возвращает домен, как пустая строка. Это может произойти, если время ожидания сети предотвращает определение имени этого метода. Это также справедливо для идентификаторов безопасности без соответствующего имени учетной записи, например входа в систему `SID` , идентифицирующим сеанс входа в систему.  
  
##  <a name="equalprefix"></a>CSid::EqualPrefix  
 Тесты `SID` префиксы (идентификатором безопасности) для проверки на равенство.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `SID` Структуры (идентификатором безопасности) или `CSid` объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при успешном выполнении **false** при сбое.  
  
### <a name="remarks"></a>Примечания  
 В разделе [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) в Windows SDK для получения дополнительных сведений.  
  
##  <a name="getlength"></a>CSid::GetLength  
 Возвращает длину `CSid` объекта.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину в байтах `CSid` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CSid` имеет недопустимую структуру, возвращаемое значение не определено. Перед вызовом метода `GetLength`, используйте [CSid::IsValid](#isvalid) убедитесь, что функция-член `CSid` является допустимым.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="getpsid"></a>CSid::GetPSID  
 Возвращает указатель на `SID` структуры (идентификатором безопасности).  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес `CSid` основным `SID` структуры.  
  
##  <a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Возвращает указатель на **SID_IDENTIFIER_AUTHORITY** структуры.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается адрес **SID_IDENTIFIER_AUTHORITY** структуры. В случае неудачи возвращаемое значение не определено. Ошибка может возникать, если `CSid` недопустимый объект, в этом случае [CSid::IsValid](#isvalid) возвращает **false**. Функция `GetLastError` может быть вызван для расширенные сведения об ошибке.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="getsubauthority"></a>CSid::GetSubAuthority  
 Возвращает указанный данных неверна в `SID` структуры (идентификатором безопасности).  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nSubAuthority*  
 Данных неверна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает данных неверна, ссылается *nSubAuthority.* Значение данных неверна — относительных идентификаторов (RID).  
  
### <a name="remarks"></a>Примечания  
 *NSubAuthority* параметр задает определение элемента массива данных неверна, метод возвращает значение индекса. Этот метод выполняет проверочные тесты на это значение. Приложение может вызвать [CSid::GetSubAuthorityCount](#getsubauthoritycount) для обнаружения диапазон допустимых значений.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Возвращает число данных неверна.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается число данных неверна.  
  
 Если метод завершается ошибкой, возвращаемое значение не определено. Если происходит сбой метода `CSid` недопустимый объект. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="isvalid"></a>CSid::IsValid  
 Тесты `CSid` объекта на допустимость.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CSid` объект является допустимым, **false** в противном случае. Нет сведений об ошибке для этого метода. Не вызывайте `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 `IsValid` Проверяет метод `CSid` объекта путем проверки, номер редакции находится в пределах известного диапазона, а также что количество поля меньше максимального.  
  
##  <a name="loadaccount"></a>CSid::LoadAccount  
 Обновления `CSid` объекта по заданному имени учетной записи и домен или существующую структуру идентификатор защиты (SID).  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszAccountName`  
 Имя учетной записи.  
  
 `pszSystem`  
 Имя системы. Эта строка может быть имя удаленного компьютера. Если значение свойства равно NULL, вместо него используется локальная система.  
  
 `pSid`  
 Указатель на [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при успешном выполнении **false** при сбое. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 `LoadAccount`пытается найти идентификатор безопасности для указанного имени. В разделе [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) для получения дополнительных сведений.  
  
##  <a name="operator_eq"></a>CSid::operator =  
 Оператор присвоения.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` присвоить `CSid` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CSid` объекта.  
  
##  <a name="operator_eq_eq"></a>CSid::operator ==  
 Проверяет два объекта дескриптора безопасности для проверки на равенство.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части оператора ==.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части оператора ==.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если дескрипторы безопасности равны; в противном случае **false**.  
  
##  <a name="operator_neq"></a>CSid::operator! =  
 Проверяет два объекта дескриптора безопасности для проверки на неравенство.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если дескрипторы безопасности не равны; в противном случае **false**.  
  
##  <a name="operator_lt"></a>CSid::operator&lt;  
 Сравнивает относительные значение два объекта дескриптора безопасности.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` — меньше, чем `rhs`, в противном случае **false**.  
  
##  <a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Сравнивает относительные значение два объекта дескриптора безопасности.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` меньше или равно `rhs`, в противном случае **false**.  
  
##  <a name="operator_gt"></a>CSid::operator&gt;  
 Сравнивает относительные значение два объекта дескриптора безопасности.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` больше, чем `rhs`, в противном случае **false**.  
  
##  <a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Сравнивает относительные значение два объекта дескриптора безопасности.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатором безопасности) или `CSid` , которая отображается в правой части! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` больше или равно `rhs`, в противном случае **false**.  
  
##  <a name="operator_const_sid__star"></a>CSid::operator const SID *  
 Приведение `CSid` объекта в указатель на `SID` структуры (идентификатором безопасности).  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает адрес `SID` структуры.  
  
##  <a name="sid"></a>CSid::Sid  
 Возвращает `SID` структуры (идентификатором безопасности) как строка.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `SID` структуру как строку в формате, пригодном для отображения, сохранения или передачи. Эквивалентно [ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), несмотря на то, что эта функция только в Windows 2000 или более поздних версий и поэтому эмулируется операционных систем предыдущих версий.  
  
##  <a name="sidnameuse"></a>CSid::SidNameUse  
 Возвращает описание состояния `CSid` объекта.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение члена данных, в которой хранится значение, описывающее состояние `CSid` объекта.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|SidTypeUser|Указывает пользователя `SID` (идентификатором безопасности).|  
|SidTypeGroup|Указывает группу `SID`.|  
|SidTypeDomain|Указывает домен `SID`.|  
|SidTypeAlias|Указывает псевдоним `SID`.|  
|SidTypeWellKnownGroup|Указывает `SID` для хорошо известная группа.|  
|SidTypeDeletedAccount|Указывает `SID` для удаленной учетной записи.|  
|SidTypeInvalid|Указывает на недопустимый `SID`.|  
|SidTypeUnknown|Указывает Неизвестный `SID` типа.|  
|SidTypeComputer|Указывает `SID` для компьютера.|  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CSid::LoadAccount](#loadaccount) обновление `CSid` объект перед вызовом метода `SidNameUse` для возврата состояния. `SidNameUse`не изменять состояние объекта (путем вызова для **LookupAccountName** или **LookupAccountSid**), но только возвращает текущее состояние.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)   
 [Операторы](../../atl/reference/atl-operators.md)
