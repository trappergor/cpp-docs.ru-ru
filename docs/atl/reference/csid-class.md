---
title: CSid, класс
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
ms.openlocfilehash: ed19ed3cdeb77612e20d826480ab73b9361366e9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496447"
---
# <a name="csid-class"></a>CSid, класс

Этот класс является оболочкой для `SID` структуры идентификатора безопасности.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSid
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CSid::CSidArray](#csidarray)|Массив объектов `CSid`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSid::CSid](#csid)|Конструктор.|
|[CSid::~CSid](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSid::AccountName](#accountname)|Возвращает имя учетной записи, связанной с `CSid` объектом.|
|[CSid::D омаин](#domain)|Возвращает имя домена, связанного с `CSid` объектом.|
|[CSid::EqualPrefix](#equalprefix)|Префиксы (идентификатор безопасности) для проверки `SID` на равенство.|
|[CSid::GetLength](#getlength)|Возвращает длину `CSid` объекта.|
|[CSid::GetPSID](#getpsid)|Возвращает указатель на `SID` структуру.|
|[Код CSid:: GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуру.|
|[Код CSid:: Жетсубаусорити](#getsubauthority)|Возвращает указанную подавторство в `SID` структуре.|
|[Код CSid:: Жетсубаусоритикаунт](#getsubauthoritycount)|Возвращает число подавторов.|
|[Код CSid:: IsValid](#isvalid)|Проверяет правильность `CSid` объекта.|
|[Код CSid:: Лоадаккаунт](#loadaccount)|Обновляет объект, учитывая имя учетной записи и домен, или существующую `SID` структуру. `CSid`|
|[CSid::Sid](#sid)|Возвращает строку идентификатора.|
|[CSid::SidNameUse](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#operator_eq)|Оператор присвоения.|
|[Идентификатор безопасности оператора const *](#operator_const_sid__star)|Приводит объект к указателю `SID` на структуру. `CSid`|

### <a name="global-operators"></a>Глобальные операторы

|||
|-|-|
|[Оператор = =](#operator_eq_eq)|Проверяет два объекта дескриптора безопасности на равенство|
|[operator! =](#operator_neq)|Проверяет два объекта дескриптора безопасности на неравенство|
|[станции\<](#operator_lt)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[Оператор >](#operator_gt)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[станции\<=](#operator_lt__eq)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|
|[Оператор > =](#operator_gt__eq)|Сравнивает относительное значение двух объектов дескрипторов безопасности.|

## <a name="remarks"></a>Примечания

`SID` Структура — это структура переменной длины, используемая для уникальной идентификации пользователей или групп.

Приложения не должны изменять `SID` структуру напрямую, а вместо этого использовать методы, предоставленные этим классом-оболочкой. См. также [атлжетовнерсид](security-global-functions.md#atlgetownersid), [атлсетграупсид](security-global-functions.md#atlsetgroupsid), [атлжетграупсид](security-global-functions.md#atlgetgroupsid)и [атлсетовнерсид](security-global-functions.md#atlsetownersid).

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="accountname"></a>Код CSid:: AccountName

Возвращает имя учетной записи, связанной с `CSid` объектом.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя учетной записи.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатора безопасности). Полные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если не удается найти имя учетной записи для `SID` , `AccountName` возвращает пустую строку. Это может произойти, если время ожидания сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, например `SID` , который идентифицирует сеанс входа.

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

*rhs*<br/>
Существующий `CSid` объект или `SID` структура (идентификатор безопасности).

*идентифиераусорити*<br/>
Центр сертификации.

*нсубаусоритикаунт*<br/>
Число подавторов.

*псзаккаунтнаме*<br/>
Имя учетной записи.

*псзсистем*<br/>
Имя системы. Эта строка может быть именем удаленного компьютера. Если эта строка имеет значение NULL, вместо нее используется локальная система.

*Пустой pSid*<br/>
Указатель на `SID` структуру.

### <a name="remarks"></a>Примечания

Конструктор инициализирует `CSid` объект, настроив внутренний элемент данных на *сидтипеинвалид*или копируя параметры `CSid` `SID`из существующей или существующей учетной записи.

Если инициализация завершается неудачей, конструктор вызывает [класс катлексцептион](../../atl/reference/catlexception-class.md).

##  <a name="dtor"></a>  CSid::~CSid

Деструктор

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом.

##  <a name="csidarray"></a>  CSid::CSidArray

Массив объектов [CSid](../../atl/reference/csid-class.md) .

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>Примечания

Это определение типа определяет тип массива, который можно использовать для получения идентификаторов безопасности из списка ACL (список управления доступом). См. раздел [какл:: жетаклентриес](../../atl/reference/cacl-class.md#getaclentries).

##  <a name="domain"></a>CSid::D омаин

Возвращает имя домена, связанного с `CSid` объектом.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект `LPCTSTR` , указывающий на домен.

### <a name="remarks"></a>Примечания

Этот метод пытается найти имя для указанного `SID` (идентификатора безопасности). Полные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw).

Если не удается найти имя учетной записи для `SID` , `Domain` возвращает домен в виде пустой строки. Это может произойти, если время ожидания сети не позволяет этому методу найти имя. Это также происходит для идентификаторов безопасности без соответствующего имени учетной записи, например `SID` , который идентифицирует сеанс входа.

##  <a name="equalprefix"></a>Код CSid:: Екуалпрефикс

Префиксы (идентификатор безопасности) для проверки `SID` на равенство.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Структура или`CSid` сравниваемый объект (идентификаторбезопасности).`SID`

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [екуалпрефикссид](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) в Windows SDK.

##  <a name="getlength"></a>  CSid::GetLength

Возвращает длину `CSid` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину `CSid` объекта в байтах.

### <a name="remarks"></a>Примечания

`CSid` Если структура недопустима, возвращаемое значение не определено. Перед вызовом метода `GetLength`используйте функцию-член [CSid:: IsValid](#isvalid) , чтобы убедиться `CSid` , что является допустимым.

> [!NOTE]
>  В разделе Отладка сборок функция вызывает Assert, если `CSid` объект является недопустимым.

##  <a name="getpsid"></a>  CSid::GetPSID

Возвращает указатель на `SID` структуру (идентификатор безопасности).

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `CSid` базовой `SID` структуры объекта.

##  <a name="getpsid_identifier_authority"></a>Код CSid:: GetPSID_IDENTIFIER_AUTHORITY

Возвращает указатель на `SID_IDENTIFIER_AUTHORITY` структуру.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, возвращается адрес `SID_IDENTIFIER_AUTHORITY` структуры. В случае сбоя возвращаемое значение не определено. Сбой может произойти, если `CSid` объект является недопустимым. в этом случае метод [CSid:: IsValid](#isvalid) возвращает значение false. Функцию `GetLastError` можно вызывать для получения расширенных сведений об ошибках.

> [!NOTE]
>  В разделе Отладка сборок функция вызывает Assert, если `CSid` объект является недопустимым.

##  <a name="getsubauthority"></a>Код CSid:: Жетсубаусорити

Возвращает указанную подавторство в `SID` структуре (идентификатор безопасности).

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>Параметры

*нсубаусорити*<br/>
Подавтор.

### <a name="return-value"></a>Возвращаемое значение

Возвращает подавтор, на который ссылается *нсубаусорити.* Значение подавтора — это относительный идентификатор (RID).

### <a name="remarks"></a>Примечания

Параметр *нсубаусорити* задает значение индекса, определяющее элемент массива подавторов, который будет возвращен методом. Метод не выполняет проверочные тесты для этого значения. Приложение может вызвать код [CSid:: жетсубаусоритикаунт](#getsubauthoritycount) , чтобы определить диапазон допустимых значений.

> [!NOTE]
>  В разделе Отладка сборок функция вызывает Assert, если `CSid` объект является недопустимым.

##  <a name="getsubauthoritycount"></a>Код CSid:: Жетсубаусоритикаунт

Возвращает число подавторов.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если метод завершился удачно, возвращается значение счетчика подавторов.

Если метод завершается ошибкой, возвращаемое значение не определено. Метод завершается ошибкой, `CSid` если объект является недопустимым. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

> [!NOTE]
>  В разделе Отладка сборок функция вызывает Assert, если `CSid` объект является недопустимым.

##  <a name="isvalid"></a>  CSid::IsValid

Проверяет правильность `CSid` объекта.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CSid` если объект является допустимым, в противном случае — значение false. Расширенные сведения об ошибке для этого метода отсутствуют. не вызывайте `GetLastError`.

### <a name="remarks"></a>Примечания

`IsValid` Метод проверяет`CSid` объект, проверяя, что номер редакции находится в известном диапазоне, а число вложений меньше максимального.

##  <a name="loadaccount"></a>Код CSid:: Лоадаккаунт

`CSid` Обновляет объект, учитывая имя учетной записи и домен, или существующую структуру SID (идентификатор безопасности).

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>Параметры

*псзаккаунтнаме*<br/>
Имя учетной записи.

*псзсистем*<br/>
Имя системы. Эта строка может быть именем удаленного компьютера. Если эта строка имеет значение NULL, вместо нее используется локальная система.

*Пустой pSid*<br/>
Указатель на структуру [идентификатора безопасности](/windows/win32/api/winnt/ns-winnt-sid) .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE при успешном выполнении, FALSE в случае сбоя. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.

### <a name="remarks"></a>Примечания

`LoadAccount`пытается найти идентификатор безопасности для указанного имени. Дополнительные сведения см. в разделе [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) .

##  <a name="operator_eq"></a>CSid:: operator =

Оператор присвоения.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Значение `SID` (идентификатор безопасности) или `CSid` для назначения `CSid` объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CSid` объект.

##  <a name="operator_eq_eq"></a>CSid:: operator = =

Проверяет два объекта дескриптора безопасности на равенство.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора = =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора = =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если дескрипторы безопасности равны; в противном случае — значение FALSE.

##  <a name="operator_neq"></a>CSid:: operator! =

Проверяет два объекта дескриптора безопасности на неравенство.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если дескрипторы безопасности не равны; в противном случае — значение FALSE.

##  <a name="operator_lt"></a>CSid:: operator&lt;

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* меньше *RHS*; в противном случае — значение false.

##  <a name="operator_lt__eq"></a>CSid:: operator&lt;=

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* меньше или равен *RHS*; в противном случае — значение false.

##  <a name="operator_gt"></a>CSid:: operator&gt;

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* больше *RHS*; в противном случае — значение false.

##  <a name="operator_gt__eq"></a>CSid:: operator&gt;=

Сравнивает относительное значение двух объектов дескрипторов безопасности.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
(Идентификатор безопасности) или `CSid` отображается в левой части оператора! =. `SID`

*rhs*<br/>
(Идентификатор безопасности) или `CSid` отображается в правой части оператора! =. `SID`

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *LHS* больше или равен *RHS*; в противном случае — значение false.

##  <a name="operator_const_sid__star"></a>Идентификатор CSid:: operator const\*

Приводит объект к указателю `SID` на структуру (идентификатор безопасности). `CSid`

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>Примечания

Возвращает адрес `SID` структуры.

##  <a name="sid"></a>  CSid::Sid

Возвращает структуру `SID` (идентификатор безопасности) в виде строки.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

`SID` Возвращает структуру в виде строки в формате, подходящем для вывода, хранения или передачи. Эквивалентно [функция ConvertSidToStringSid вернула](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw).

##  <a name="sidnameuse"></a>Код CSid:: Сиднамеусе

Возвращает описание состояния `CSid` объекта.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение элемента данных, в котором хранится значение, описывающее состояние `CSid` объекта.

|Значение|Описание|
|-----------|-----------------|
|сидтипеусер|Указывает пользователя `SID` (идентификатор безопасности).|
|сидтипеграуп|Указывает группу `SID`.|
|сидтипедомаин|Указывает домен `SID`.|
|сидтипеалиас|Указывает псевдоним `SID`.|
|сидтипевеллкновнграуп|`SID` Указывает на хорошо известную группу.|
|сидтипеделетедаккаунт|`SID` Указывает для удаленной учетной записи.|
|сидтипеинвалид|Указывает на недопустимое `SID`.|
|сидтипеункновн|Указывает на неизвестный `SID` тип.|
|сидтипекомпутер|Указывает на `SID` компьютер.|

### <a name="remarks"></a>Примечания

Вызовите код [CSid:: лоадаккаунт](#loadaccount) , `CSid` чтобы обновить объект `SidNameUse` перед вызовом метода, чтобы вернуть его состояние. `SidNameUse`не изменяет состояние объекта (путем вызова метода `LookupAccountName` или `LookupAccountSid`), но возвращает только текущее состояние.

## <a name="see-also"></a>См. также

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Инструкции](../../atl/reference/atl-operators.md)
