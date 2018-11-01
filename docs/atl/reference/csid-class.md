---
title: Класс CSid
ms.date: 11/04/2016
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
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: 57edb46047021d0ede04164584e79748028e05b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465368"
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

|Имя|Описание|
|----------|-----------------|
|[CSid::CSidArray](#csidarray)|Массив объектов `CSid`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSid::CSid](#csid)|Конструктор.|
|[CSid::~CSid](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSid::AccountName](#accountname)|Возвращает имя учетной записи, связанной с `CSid` объекта.|
|[CSid::Domain](#domain)|Возвращает имя домена, связанного с `CSid` объекта.|
|[CSid::EqualPrefix](#equalprefix)|Тесты `SID` префиксы (идентификатором безопасности) на предмет равенства.|
|[CSid::GetLength](#getlength)|Возвращает длину `CSid` объекта.|
|[CSid::GetPSID](#getpsid)|Возвращает указатель на `SID` структуры.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуры.|
|[CSid::GetSubAuthority](#getsubauthority)|Возвращает указанный защитного кода в `SID` структуры.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Возвращает количество защитного кода.|
|[CSid::IsValid](#isvalid)|Тесты `CSid` объекта на допустимость.|
|[CSid::LoadAccount](#loadaccount)|Обновления `CSid` объекта по заданному имени учетной записи и домену или существующий `SID` структуры.|
|[CSid::Sid](#sid)|Возвращает строку идентификатора.|
|[CSid::SidNameUse](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](#operator_eq)|Оператор присвоения.|
|[оператор const ИД безопасности *](#operator_const_sid__star)|Приведения `CSid` объекта в указатель на `SID` структуры.|

### <a name="global-operators"></a>Глобальных операторов

|||
|-|-|
|[оператор ==](#operator_eq_eq)|Проверяет два объекта дескриптора безопасности для проверки на равенство|
|[оператор! =](#operator_neq)|Проверяет два объекта дескриптора безопасности для проверки на неравенство|
|[Оператор \<](#operator_lt_)|Сравнивает относительные значения двух объектов дескриптора безопасности.|
|[оператор >](#operator_gt_)|Сравнивает относительные значения двух объектов дескриптора безопасности.|
|[Оператор \<=](#operator_lt__eq)|Сравнивает относительные значения двух объектов дескриптора безопасности.|
|[оператор > =](#operator_gt__eq)|Сравнивает относительные значения двух объектов дескриптора безопасности.|

## <a name="remarks"></a>Примечания

`SID` Структуры является структурой переменной длины, используемые для уникальной идентификации пользователей или групп.

Приложения не следует изменять `SID` структура напрямую, но вместо этого используйте методы, предоставленные в этот класс-оболочка. См. также [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), и [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="accountname"></a>  CSid::AccountName

Возвращает имя учетной записи, связанной с `CSid` объекта.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя учетной записи.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатором безопасности). Дополнительные сведения см. в разделе [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Если нет имени учетной записи для `SID` можно найти, `AccountName` возвращает пустую строку. Это может произойти, если время ожидания сети предотвращающее нахождение имя этого метода. Она также проводится для идентификаторов безопасности без соответствующего имени учетной записи, такие как имя входа `SID` , идентифицирующий сеанс входа в систему.

##  <a name="csid"></a>  CSid::CSid

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

*правая часть*<br/>
Существующий `CSid` объекта или `SID` структуры (идентификатором безопасности).

*IdentifierAuthority*<br/>
Центр сертификации.

*nSubAuthorityCount*<br/>
Счетчик защитного кода.

*pszAccountName*<br/>
Имя учетной записи.

*pszSystem*<br/>
Системное имя. Эта строка может быть имя удаленного компьютера. Если эта строка имеет значение NULL, вместо него используется локальной системе.

*pSid*<br/>
Указатель на `SID` структуры.

### <a name="remarks"></a>Примечания

Конструктор инициализирует `CSid` объект, значение члена внутренние данные *SidTypeInvalid*, или копируя параметры из существующего `CSid`, `SID`, или существующую учетную запись.

В случае сбоя инициализации конструктор выдаст [класс CAtlException](../../atl/reference/catlexception-class.md).

##  <a name="dtor"></a>  CSid::~CSid

Деструктор

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом.

##  <a name="csidarray"></a>  CSid::CSidArray

Массив [CSid](../../atl/reference/csid-class.md) объектов.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Примечания

Это определение типа задает тип массива, который может использоваться для получения идентификаторов безопасности из ACL (список управления доступом). См. в разделе [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).

##  <a name="domain"></a>  CSid::Domain

Возвращает имя домена, связанного с `CSid` объекта.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `LPCTSTR` указывает на домен.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатором безопасности). Дополнительные сведения см. в разделе [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida).

Если нет имени учетной записи для `SID` можно найти, `Domain` Возвращает домен, как пустая строка. Это может произойти, если время ожидания сети предотвращающее нахождение имя этого метода. Она также проводится для идентификаторов безопасности без соответствующего имени учетной записи, такие как имя входа `SID` , идентифицирующий сеанс входа в систему.

##  <a name="equalprefix"></a>  CSid::EqualPrefix

Тесты `SID` префиксы (идентификатором безопасности) на предмет равенства.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`SID` Структуры (идентификатором безопасности) или `CSid` объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

См. в разделе [EqualPrefixSid](https://msdn.microsoft.com/library/windows/desktop/aa446621) в пакете SDK Windows для получения дополнительных сведений.

##  <a name="getlength"></a>  CSid::GetLength

Возвращает длину `CSid` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину в байтах `CSid` объекта.

### <a name="remarks"></a>Примечания

Если `CSid` структура не является допустимой, возвращаемое значение не определено. Перед вызовом `GetLength`, использовать [CSid::IsValid](#isvalid) убедитесь, что функция-член `CSid` является допустимым.

> [!NOTE]
>  В отладочных сборках, функция будет вызывать ASSERT, если `CSid` объект не является допустимым.

##  <a name="getpsid"></a>  CSid::GetPSID

Возвращает указатель на `SID` структуры (идентификатором безопасности).

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `CSid` основным `SID` структуры.

##  <a name="getpsid_identifier_authority"></a>  CSid::GetPSID_IDENTIFIER_AUTHORITY

Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуры.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, он возвращает адрес `SID_IDENTIFIER_AUTHORITY` структуры. Если происходит сбой, возвращаемое значение не определено. Сбой может возникать при `CSid` недопустимый объект, в этом случае [CSid::IsValid](#isvalid) метод возвращает значение FALSE. Функция `GetLastError` может вызываться для расширенные сведения об ошибке.

> [!NOTE]
>  В отладочных сборках, функция будет вызывать ASSERT, если `CSid` объект не является допустимым.

##  <a name="getsubauthority"></a>  CSid::GetSubAuthority

Возвращает указанный защитного кода в `SID` структуры (идентификатором безопасности).

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Параметры

*nSubAuthority*<br/>
Защитного кода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает защитного кода, ссылается *nSubAuthority.* Значение защитного кода является относительным идентификатором (RID).

### <a name="remarks"></a>Примечания

*NSubAuthority* параметр указывает определение элемента массива защитного кода, метод возвращает значение индекса. Этот метод выполняет проверочные тесты на это значение. Приложение может вызвать [CSid::GetSubAuthorityCount](#getsubauthoritycount) для обнаружения диапазон допустимых значений.

> [!NOTE]
>  В отладочных сборках, функция будет вызывать ASSERT, если `CSid` объект не является допустимым.

##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount

Возвращает количество защитного кода.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращаемое значение является счетчиком защитного кода.

При сбое метода, возвращаемое значение не определено. Если происходит сбой метода `CSid` объекта является недопустимым. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

> [!NOTE]
>  В отладочных сборках, функция будет вызывать ASSERT, если `CSid` объект не является допустимым.

##  <a name="isvalid"></a>  CSid::IsValid

Тесты `CSid` объекта на допустимость.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если `CSid` объект является допустимым, FALSE Если это не так. Нет информации об ошибке для данного метода; Не вызывайте `GetLastError`.

### <a name="remarks"></a>Примечания

`IsValid` Метод проверяет `CSid` объекта, проверяя, что номер редакции в известном диапазоне и что число поля меньше максимального.

##  <a name="loadaccount"></a>  CSid::LoadAccount

Обновления `CSid` объекта по заданному имени учетной записи и домену или по существующей структуре идентификатора безопасности (SID).

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*pszAccountName*<br/>
Имя учетной записи.

*pszSystem*<br/>
Системное имя. Эта строка может быть имя удаленного компьютера. Если эта строка имеет значение NULL, вместо него используется локальной системе.

*pSid*<br/>
Указатель на [SID](/windows/desktop/api/winnt/ns-winnt-_sid) структуры.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

`LoadAccount` пытается найти идентификатор безопасности для указанного имени. См. в разделе [LookupAccountSid](/windows/desktop/api/winbase/nf-winbase-lookupaccountsida) для получения дополнительных сведений.

##  <a name="operator_eq"></a>  CSid::operator =

Оператор присвоения.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` присваиваемое `CSid` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CSid` объекта.

##  <a name="operator_eq_eq"></a>  CSid::operator ==

Проверяет два объекта дескриптора безопасности для проверки на равенство.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части оператора ==.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части оператора ==.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если идентичны, в противном случае значение FALSE, то дескрипторы безопасности.

##  <a name="operator_neq"></a>  CSid::operator! =

Проверяет два объекта дескриптора безопасности для проверки на неравенство.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части! =-оператор.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части! =-оператор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если дескрипторы безопасности не равны, в противном случае — значение FALSE.

##  <a name="operator_lt"></a>  CSid::operator &lt;

Сравнивает относительные значения двух объектов дескриптора безопасности.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части! =-оператор.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части! =-оператор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *lhs* — меньше, чем *rhs*, в противном случае — значение FALSE.

##  <a name="operator_lt__eq"></a>  CSid::operator &lt;=

Сравнивает относительные значения двух объектов дескриптора безопасности.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части! =-оператор.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части! =-оператор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *lhs* меньше или равно *rhs*, в противном случае — значение FALSE.

##  <a name="operator_gt"></a>  CSid::operator &gt;

Сравнивает относительные значения двух объектов дескриптора безопасности.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части! =-оператор.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части! =-оператор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *lhs* больше, чем *rhs*, в противном случае — значение FALSE.

##  <a name="operator_gt__eq"></a>  CSid::operator &gt;=

Сравнивает относительные значения двух объектов дескриптора безопасности.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в левой части! =-оператор.

*правая часть*<br/>
`SID` (Идентификатором безопасности) или `CSid` , отображаемый в правой части! =-оператор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *lhs* больше или равно *rhs*, в противном случае — значение FALSE.

##  <a name="operator_const_sid__star"></a>  CSid::operator const SID \*

Приведения `CSid` объекта в указатель на `SID` структуры (идентификатором безопасности).

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Примечания

Возвращает адрес `SID` структуры.

##  <a name="sid"></a>  CSid::Sid

Возвращает `SID` структуры (идентификатором безопасности) как строка.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `SID` структура в виде строки в формате, удобном для отображения, сохранения или передачи. Эквивалентно [функция ConvertSidToStringSid](/windows/desktop/api/sddl/nf-sddl-convertsidtostringsida).

##  <a name="sidnameuse"></a>  CSid::SidNameUse

Возвращает описание состояния `CSid` объекта.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение элемента данных, который хранит значение, описывающее состояние `CSid` объекта.

|Значение|Описание|
|-----------|-----------------|
|SidTypeUser|Указывает пользователя `SID` (идентификатором безопасности).|
|SidTypeGroup|Указывает группу `SID`.|
|SidTypeDomain|Указывает домен `SID`.|
|SidTypeAlias|Указывает псевдоним `SID`.|
|SidTypeWellKnownGroup|Указывает `SID` для хорошо известных группы.|
|SidTypeDeletedAccount|Указывает `SID` для удаленной учетной записи.|
|SidTypeInvalid|Указывает на недопустимый `SID`.|
|SidTypeUnknown|Показывает неизвестное `SID` типа.|
|SidTypeComputer|Указывает `SID` для компьютера.|

### <a name="remarks"></a>Примечания

Вызовите [CSid::LoadAccount](#loadaccount) обновить `CSid` объект перед вызовом `SidNameUse` для возврата состояния. `SidNameUse` не изменяет состояние объекта (вызовом `LookupAccountName` или `LookupAccountSid`), но только возвращает текущее состояние.

## <a name="see-also"></a>См. также

[Образец безопасности](../../visual-cpp-samples.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Операторы](../../atl/reference/atl-operators.md)
