---
title: Класс CSid
ms.date: 03/27/2019
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
ms.openlocfilehash: 414cf428cebe8105d90b3add93cc7f1e76927c2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330922"
---
# <a name="csid-class"></a>Класс CSid

Этот класс представляет собой `SID` обертку для (идентификатор безопасности) структуры.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

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
|[CSid:::»CSid](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSid::AccountName](#accountname)|Возвращает имя учетной записи, связанной с объектом. `CSid`|
|[CSid::Domain](#domain)|Возвращает имя домена, связанного с объектом. `CSid`|
|[CSid::EqualPrefix](#equalprefix)|Тесты `SID` (идентификатор безопасности) префиксы для равенства.|
|[CSid::GetLength](#getlength)|Возвращает длину `CSid` объекта.|
|[CSid::GetPSID](#getpsid)|Возвращает указатель в `SID` структуру.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель в `SID_IDENTIFIER_AUTHORITY` структуру.|
|[CSid::GetSubAuthority](#getsubauthority)|Возвращает указанную субвласть `SID` в структуру.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Возвращает подсчет субавторитетов.|
|[CSid::IsValid](#isvalid)|Тестирует `CSid` объект на достоверность.|
|[CSid::LoadAccount](#loadaccount)|Обновляет `CSid` объект с учетом имени учетной `SID` записи и домена или существующей структуры.|
|[CSid::Sid](#sid)|Возвращает строку ID.|
|[CSid::SidNameUse](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор](#operator_eq)|Оператор присвоения.|
|[Оператор const SID](#operator_const_sid__star)|Отбрасывает `CSid` объект указателю на `SID` структуру.|

### <a name="global-operators"></a>Глобальные операторы

|||
|-|-|
|[оператор](#operator_eq_eq)|Тесты двух объектов дескриптора безопасности на равенство|
|[оператор !](#operator_neq)|Тесты двух объектов дескриптора безопасности на предмет неравенства|
|[Оператор\<](#operator_lt)|Сравнивает относительную ценность двух объектов дескриптора безопасности.|
|[оператор >](#operator_gt)|Сравнивает относительную ценность двух объектов дескриптора безопасности.|
|[Оператор\<=](#operator_lt__eq)|Сравнивает относительную ценность двух объектов дескриптора безопасности.|
|[оператор >](#operator_gt__eq)|Сравнивает относительную ценность двух объектов дескриптора безопасности.|

## <a name="remarks"></a>Remarks

Структура `SID` представляет собой структуру с переменной длиной, используемую для однозначной идентификации пользователей или групп.

Приложения не должны `SID` изменять структуру напрямую, а вместо этого использовать методы, предусмотренные в этом классе обертки. Смотрите также [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid)и [AtlSetOwnerSid](security-global-functions.md#atlsetownersid).

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="csidaccountname"></a><a name="accountname"></a>CSid::AccountName

Возвращает имя учетной записи, связанной с объектом. `CSid`

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на название учетной записи.

### <a name="remarks"></a>Remarks

Этот метод пытается найти имя для `SID` указанного (идентификатор безопасности). Для получения подробной информации, см [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если имя учетной `SID` записи `AccountName` для неможет быть найдено, возвращаетпустую строку. Это может произойти, если тайм-аут сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, `SID` например, которая идентифицирует сеанс вступления.

## <a name="csidcsid"></a><a name="csid"></a>CSid::CSid

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

*rhs*<br/>
Существующая `CSid` структура `SID` объекта или (идентификатор безопасности).

*ИдентификацияОрганная*<br/>
Власть.

*nSubAuthorityCount*<br/>
Подсчет субавторитетов.

*pszAccountName*<br/>
Имя учетной записи.

*pszSystem*<br/>
Название системы. Эта строка может быть именем удаленного компьютера. Если эта строка NULL, вместо этого используется локальная система.

*Psid*<br/>
Указатель на `SID` структуру.

### <a name="remarks"></a>Remarks

`CSid` Конструктор инициализирует объект, устанавливая внутренний элемент данных на *SidTypeInvalid* `CSid`или `SID`копируя настройки из существующей учетной записи или существующей учетной записи.

Если инициализация не удается, конструктор будет бросать [Класс CAtlException](../../atl/reference/catlexception-class.md).

## <a name="csidcsid"></a><a name="dtor"></a>CSid:::»CSid

Деструктор

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Remarks

Деструктор освобождает любые ресурсы, приобретенные объектом.

## <a name="csidcsidarray"></a><a name="csidarray"></a>CSid::CSidArray

Массив объектов [CSid.](../../atl/reference/csid-class.md)

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Remarks

Этот тип определяет тип массива, который может быть использован для получения идентификаторов безопасности из списка ACL (список контроля доступа). Смотрите [CAcl::GetAclE записи](../../atl/reference/cacl-class.md#getaclentries).

## <a name="csiddomain"></a><a name="domain"></a>CSid::Domain

Возвращает имя домена, связанного с объектом. `CSid`

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `LPCTSTR` указывая на домен.

### <a name="remarks"></a>Remarks

Этот метод пытается найти имя для `SID` указанного (идентификатор безопасности). Для получения подробной информации, см [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если имя учетной `SID` записи `Domain` для неможет быть найдено, возвращает домен в виде пустой строки. Это может произойти, если тайм-аут сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, `SID` например, которая идентифицирует сеанс вступления.

## <a name="csidequalprefix"></a><a name="equalprefix"></a>CSid::EqualPrefix

Тесты `SID` (идентификатор безопасности) префиксы для равенства.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Структура `SID` (идентификатор `CSid` безопасности) или объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Remarks

Подробнее о ней читайте в материале [«EqualPrefixSid»](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) в SDK windows.

## <a name="csidgetlength"></a><a name="getlength"></a>CSid::GetLength

Возвращает длину `CSid` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину байтов `CSid` объекта.

### <a name="remarks"></a>Remarks

Если `CSid` структура недействительна, значение возврата не определено. Перед `GetLength`вызовом используйте функцию [cSid::IsValid](#isvalid) для проверки подлинности. `CSid`

> [!NOTE]
> При отладке создается функция, `CSid` которая вызовет ASSERT, если объект недействителен.

## <a name="csidgetpsid"></a><a name="getpsid"></a>CSid::GetPSID

Возвращает указатель в `SID` структуру (идентификатор безопасности).

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес основной `CSid` `SID` структуры объекта.

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY

Возвращает указатель в `SID_IDENTIFIER_AUTHORITY` структуру.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод удается, он возвращает `SID_IDENTIFIER_AUTHORITY` адрес структуры. Если это не удается, значение возврата не определено. Сбой может `CSid` произойти, если объект недействителен, и в этом случае метод [CSid::IsValid](#isvalid) возвращает FALSE. Функция `GetLastError` может быть вызвана для расширенной информации об ошибках.

> [!NOTE]
> При отладке создается функция, `CSid` которая вызовет ASSERT, если объект недействителен.

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority

Возвращает указанную субвласть `SID` в структуре (идентификатор безопасности).

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Параметры

*nSubAuthority*<br/>
Подвласть.

### <a name="return-value"></a>Возвращаемое значение

Возвращает суборган, на который ссылается *nSubAuthority.* Значение субавторитета является относительным идентификатором (RID).

### <a name="remarks"></a>Remarks

Параметр *nSubAuthority* определяет значение индекса, определяющее элемент субавторитетного массива, который будет возвращать метод. Метод не выполняет тесты проверки на этом значении. Приложение может вызвать [CSid::GetSubAuthorityCount,](#getsubauthoritycount) чтобы обнаружить диапазон приемлемых значений.

> [!NOTE]
> При отладке создается функция, `CSid` которая вызовет ASSERT, если объект недействителен.

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount

Возвращает подсчет субавторитетов.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод успешно, значение возврата является подсчетом субавторитета.

Если метод завершается неудачей, значение возврата не определено. Метод выходит из `CSid` строя, если объект недействителен. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

> [!NOTE]
> При отладке создается функция, `CSid` которая вызовет ASSERT, если объект недействителен.

## <a name="csidisvalid"></a><a name="isvalid"></a>CSid::IsValid

Тестирует `CSid` объект на достоверность.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, `CSid` если объект действителен, FALSE, если нет. Для этого метода нет расширенной информации об ошибках; не звоните `GetLastError`.

### <a name="remarks"></a>Remarks

Метод `IsValid` проверяет `CSid` объект, проверяя, что номер пересмотра находится в пределах известного диапазона и что количество подповмов меньше максимального.

## <a name="csidloadaccount"></a><a name="loadaccount"></a>CSid::LoadAccount

Обновляет `CSid` объект с учетом имени учетной записи и домена, или существующей структуры SID (идентификатор безопасности).

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
Название системы. Эта строка может быть именем удаленного компьютера. Если эта строка NULL, вместо этого используется локальная система.

*Psid*<br/>
Указатель на структуру [SID.](/windows/win32/api/winnt/ns-winnt-sid)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Remarks

`LoadAccount`попытки найти идентификатор безопасности для указанного имени. Более подробную информацию можно найти на [LookupAccountSid.](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)

## <a name="csidoperator-"></a><a name="operator_eq"></a>CSid::оператор

Оператор присвоения.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или назначить `CSid` объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CSid` обновленный объект.

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a>CSid::оператор

Тесты двух объектов дескриптора безопасности на равенство.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификатор `SID` `CSid` безопасности) или отождествляется на левой стороне оператора.

*rhs*<br/>
(идентификатор `SID` `CSid` безопасности) или отождествляется на правой стороне оператора.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если дескрипторы безопасности равны, в противном случае FALSE.

## <a name="csidoperator-"></a><a name="operator_neq"></a>CSid::оператор !

Тесты двух объектов дескриптора безопасности на предмет неравенства.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на левой стороне оператора !

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на правой стороне оператора !

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если дескрипторы безопасности не равны, в противном случае FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt"></a>CSid::оператор&lt;

Сравнивает относительную ценность двух объектов дескриптора безопасности.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на левой стороне оператора !

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на правой стороне оператора !

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *lhs* меньше, чем *rhs*, в противном случае FALSE.

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::оператор&lt;=

Сравнивает относительную ценность двух объектов дескриптора безопасности.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на левой стороне оператора !

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на правой стороне оператора !

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *lhs* меньше, чем или *равна rhs*, в противном случае FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt"></a>CSid::оператор&gt;

Сравнивает относительную ценность двух объектов дескриптора безопасности.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на левой стороне оператора !

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на правой стороне оператора !

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *lhs* больше, чем *rhs*, в противном случае FALSE.

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::оператор&gt;=

Сравнивает относительную ценность двух объектов дескриптора безопасности.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на левой стороне оператора !

*rhs*<br/>
(идентификация `SID` безопасности) `CSid` или то, что появляется на правой стороне оператора !

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *lhs* больше, чем или *равна rhs*, в противном случае FALSE.

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::оператор const SID\*

Отбрасывает `CSid` объект указателю на `SID` (идентификатор безопасности) структуры.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Remarks

Возвращает адрес `SID` структуры.

## <a name="csidsid"></a><a name="sid"></a>CSid::Sid

`SID` Возвращает (идентификатор безопасности) структуру в виде строки.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `SID` структуру в виде строки в формате, пригодном для отображения, хранения или передачи. Эквивалент [convertsidToStringsid](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw).

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a>CSid::SidNameUse

Возвращает описание состояния `CSid` объекта.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение члена данных, который хранит значение, `CSid` описывающее состояние объекта.

|Значение|Описание|
|-----------|-----------------|
|SidTypeUser|Указывает пользователя `SID` (идентификатор безопасности).|
|SidTypeGroup|Указывает группу `SID`.|
|СидДидидДойм|Указывает на `SID`домен .|
|SidTypeAlias|Указывает псевдоним `SID`.|
|SidTypeWellKnownGroup|Указывает `SID` на для известной группы.|
|SidTypeУдаленныйаккаунт|Указывает `SID` на удаленную учетную запись.|
|SidTypeInvalid|Указывает недействительное `SID`.|
|SidTypeНеизвестный|Указывает неизвестный `SID` тип.|
|SidTypeComputer|Указывает `SID` на компьютер.|

### <a name="remarks"></a>Remarks

Позвоните [CSid::LoadAccount](#loadaccount) `CSid` для обновления `SidNameUse` объекта перед вызовом, чтобы вернуть его состояние. `SidNameUse`не изменяет состояние объекта (по `LookupAccountName` звонку или), `LookupAccountSid`а только возвращает текущее состояние.

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Операторы](../../atl/reference/atl-operators.md)
