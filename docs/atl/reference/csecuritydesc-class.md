---
title: Класс CSecurityDesc | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 591465ed9c16485498174a710d2d37ff68425058
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116871"
---
# <a name="csecuritydesc-class"></a>Класс CSecurityDesc

Этот класс является оболочкой для `SECURITY_DESCRIPTOR` структуры.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSecurityDesc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Конструктор.|
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::FromString](#fromstring)|Преобразует формат строки дескриптора безопасности в дескриптор допустимый, функциональной безопасности.|
|[CSecurityDesc::GetControl](#getcontrol)|Извлекает контролировать данные из дескриптора безопасности.|
|[CSecurityDesc::GetDacl](#getdacl)|Извлекает сведения о списке (DACL) для управления доступом из дескриптора безопасности.|
|[CSecurityDesc::GetGroup](#getgroup)|Извлекает сведения основной группы из дескриптора безопасности.|
|[CSecurityDesc::GetOwner](#getowner)|Получает владельца сведения из дескриптора безопасности.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Возвращает указатель на `SECURITY_DESCRIPTOR` структуры.|
|[CSecurityDesc::GetSacl](#getsacl)|Извлекает сведения о системе управления доступом список управления ДОСТУПОМ из дескриптора безопасности.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Определяет, если список DACL настроен для поддержки автоматического распространения.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Определяет, настроена ли дескриптор безопасности по умолчанию DACL.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Определяет, если дескриптор безопасности содержит список DACL.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Определяет, если список DACL настроен для предотвращения изменений.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Определяет, если дескриптор безопасности групповой идентификатор безопасности (SID) был установлен по умолчанию.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Определяет, если ИД безопасности владельца дескриптора безопасности был установлен по умолчанию.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Определяет, если список SACL настроен для поддержки автоматического распространения.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Определяет, настроена ли дескриптор безопасности по умолчанию системный список управления ДОСТУПОМ.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Определяет, содержит ли дескриптор безопасности системного списка управления ДОСТУПОМ.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Определяет, если список SACL настроена для предотвращения изменения.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Определяет, является ли дескриптор безопасности в относительном формате.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительном формате.|
|[CSecurityDesc::SetControl](#setcontrol)|Устанавливает управляющие биты дескриптора безопасности.|
|[CSecurityDesc::SetDacl](#setdacl)|Задает информацию в список DACL. Если список DACL в дескрипторе безопасности уже присутствует, он заменяется.|
|[CSecurityDesc::SetGroup](#setgroup)|Задает основную группу информацию абсолютном формате дескриптора безопасности, заменив данные основной группы уже присутствует.|
|[CSecurityDesc::SetOwner](#setowner)|Задает сведения о владельце абсолютном формате дескриптора безопасности, заменив все уже присутствует информация о владельце.|
|[CSecurityDesc::SetSacl](#setsacl)|Задает информацию в SACL. Если список SACL в дескрипторе безопасности уже присутствует, он заменяется.|
|[CSecurityDesc::ToString](#tostring)|Преобразует дескриптор безопасности в строковом формате.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Возвращает указатель на `SECURITY_DESCRIPTOR` структуры.|
|[CSecurityDesc::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

`SECURITY_DESCRIPTOR` Структура содержит сведения о безопасности, связанные с объектом. Приложения используют эту структуру для установки и запроса состояния безопасности объекта. См. также [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).

Приложения не следует изменять `SECURITY_DESCRIPTOR` структура напрямую, а вместо этого следует использовать методы класса, предоставляемые.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="csecuritydesc"></a>  CSecurityDesc::CSecurityDesc

Конструктор.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`CSecurityDesc` Объекта или `SECURITY_DESCRIPTOR` структуры, чтобы назначить новый `CSecurityDesc` объекта.

### <a name="remarks"></a>Примечания

`CSecurityDesc` Объекта при необходимости могут создаваться с использованием `SECURITY_DESCRIPTOR` структуры или ранее определенную `CSecurityDesc` объекта.

##  <a name="dtor"></a>  CSecurityDesc:: ~ CSecurityDesc

Деструктор

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

##  <a name="fromstring"></a>  CSecurityDesc::FromString

Преобразует формат строки дескриптора безопасности в дескриптор допустимый, функциональной безопасности.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на заканчивающуюся нулем строку, которая содержит [формат строки дескриптора безопасности](/windows/desktop/SecAuthZ/security-descriptor-string-format) для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true при успешном выполнении. Вызывает исключение в случае сбоя.

### <a name="remarks"></a>Примечания

Строки могут быть созданы с помощью [CSecurityDesc::ToString](#tostring). Преобразование дескриптора безопасности в строку упрощает для хранения и передачи.

Этот метод вызывает метод [функция ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

##  <a name="getcontrol"></a>  CSecurityDesc::GetControl

Извлекает контролировать данные из дескриптора безопасности.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>Параметры

*psdc*<br/>
Указатель на `SECURITY_DESCRIPTOR_CONTROL` структуры, который получает сведения об управлении дескриптор безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [GetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa446647).

##  <a name="getdacl"></a>  CSecurityDesc::GetDacl

Извлекает сведения о списке (DACL) для управления доступом из дескриптора безопасности.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDacl*<br/>
Указатель на `CDacl` структуры, в котором следует сохранить копию списка DACL в дескрипторе безопасности. Если существует таблицы управления Доступом, метод устанавливает *pDacl* адрес дескриптора безопасности списка управления Доступом на уровне пользователей. Если таблицы управления Доступом не существует, значение не сохраняется.

*pbPresent*<br/>
Указатель на значение, указывающее наличие таблицы управления Доступом в дескрипторе безопасности. Если дескриптор безопасности содержит таблицы управления Доступом, этот параметр устанавливается в значение true. Если дескриптор безопасности не содержит таблицы управления Доступом, этот параметр имеет значение false.

*pbDefaulted*<br/>
Указатель на флаг, присвоено значение флага SE_DACL_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры, если существует таблицы управления Доступом для дескриптора безопасности. Если этот флаг имеет значение true, извлекается список управления Доступом на уровне пользователей с помощью механизма по умолчанию; Если значение равно false, таблицы управления Доступом явно указано пользователем.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.

##  <a name="getgroup"></a>  CSecurityDesc::GetGroup

Извлекает сведения основной группы из дескриптора безопасности.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатором безопасности), который получает копию группы, хранящиеся в CDacl.

*pbDefaulted*<br/>
Указатель на флаг, присвоено значение флага SE_GROUP_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры при возврате метода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.

##  <a name="getowner"></a>  CSecurityDesc::GetOwner

Получает владельца сведения из дескриптора безопасности.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSid*<br/>
Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатором безопасности), который получает копию группы, хранящиеся в CDacl.

*pbDefaulted*<br/>
Указатель на флаг, присвоено значение флага SE_OWNER_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры при возврате метода.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.

##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR

Возвращает указатель на `SECURITY_DESCRIPTOR` структуры.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) структуры.

##  <a name="getsacl"></a>  CSecurityDesc::GetSacl

Извлекает сведения о системе управления доступом список управления ДОСТУПОМ из дескриптора безопасности.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSacl*<br/>
Указатель на `CSacl` структуры, в котором следует сохранить копию дескриптора безопасности системного списка управления ДОСТУПОМ. Если существует системы ACL, метод устанавливает *pSacl* адрес системы дескриптора безопасности списка управления Доступом. Если список управления Доступом системы не существует, значение не сохраняется.

*pbPresent*<br/>
Указатель на флаг, метод устанавливает для обозначения присутствия системы ACL в указанного дескриптора безопасности. Если дескриптор безопасности содержит список управления Доступом системы, этот параметр устанавливается в значение true. Если дескриптор безопасности содержит список управления Доступом системы, этот параметр имеет значение false.

*pbDefaulted*<br/>
Указатель на флаг, присвоено значение флага SE_SACL_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры, если список управления Доступом системы для дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.

##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited

Определяет, если список управления доступом (DACL) настроен для поддержки автоматического распространения.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит список DACL, который настроен для поддержки автоматическое распространение наследуемых управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Система устанавливает этот бит, при выполнении алгоритма автоматического наследования для объекта и его существующих дочерних объектов.

##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted

Определяет, настроена ли дескриптор безопасности по умолчанию список управления доступом (DACL).

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию DACL, и false в противном случае.

### <a name="remarks"></a>Примечания

Этот флаг может повлиять на том, как система обрабатывает список DACL, говоря о наследовании записи (ACE) для управления доступом. Например если создатель объекта не указан список DACL, объект получает DACL по умолчанию из маркера доступа создателя. Система пропускает этот флаг, если не установлен флаг SE_DACL_PRESENT.

Этот флаг используется для определения того, как будет вычисляться окончательный список DACL на объекте и физически не хранится в элементе управления дескриптора безопасности защищаемого объекта.

Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.

##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent

Определяет, если дескриптор безопасности содержит список управления доступом (DACL).

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит список DACL, и false в противном случае.

### <a name="remarks"></a>Примечания

Если этот флаг не установлен, или если этот флаг установлен, а DACL равен NULL, дескриптор безопасности полный доступ для всех пользователей.

Этот флаг используется для хранения сведений о безопасности, указанный вызывающим объектом до дескриптор безопасности связан с защищаемого объекта. Когда дескриптор безопасности связан с защищаемого объекта, флаг SE_DACL_PRESENT всегда имеет значение в элементе управления дескриптора безопасности.

Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.

##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected

Определяет, если список управления доступом (DACL) настроен для предотвращения изменений.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если список DACL настроен на предотвращение дескриптор безопасности от изменения наследуемые управления доступом (ACE). В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.

Этот метод поддерживает автоматическое распространение наследуемых ACE.

##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted

Определяет, если дескриптор безопасности групповой идентификатор безопасности (SID) был установлен по умолчанию.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если механизм по умолчанию, а не исходного поставщика дескриптора безопасности, дескриптор безопасности групповой идентификатор безопасности. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте [CSecurityDesc::SetGroup](#setgroup) метод.

##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted

Определяет, если идентификатора безопасности (SID) владельца дескриптора безопасности был установлен по умолчанию.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если механизм по умолчанию, а не исходного поставщика дескриптора безопасности владельца дескриптора безопасности SID. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте [CSecurityDesc::SetOwner](#setowner) метод.

##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited

Определяет, если системный список управления доступом (SACL) настроен для поддержки автоматического распространения.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит системный список управления ДОСТУПОМ, который настроен для поддержки автоматическое распространение наследуемых управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Система устанавливает этот бит, при выполнении алгоритма автоматического наследования для объекта и его существующих дочерних объектов.

##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted

Определяет, настроена ли дескриптор безопасности по умолчанию системный список управления доступом (SACL).

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию системный список управления ДОСТУПОМ, и false в противном случае.

### <a name="remarks"></a>Примечания

Этот флаг может повлиять на том, как система рассматривает SACL, говоря о наследовании записи (ACE) для управления доступом. Система пропускает этот флаг, если не установлен флаг SE_SACL_PRESENT.

Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.

##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent

Определяет, содержит ли дескриптор безопасности системный список управления доступом (SACL).

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности содержит системный список управления ДОСТУПОМ, и false в противном случае.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.

##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected

Определяет, если системный список управления доступом (SACL) настроен для предотвращения изменений.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если список SACL настроен на предотвращение дескриптор безопасности от изменения наследуемые управления доступом (ACE). В противном случае возвращает FALSE.

### <a name="remarks"></a>Примечания

Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.

Этот метод поддерживает автоматическое распространение наследуемых ACE.

##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative

Определяет, является ли дескриптор безопасности в относительном формате.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если дескриптор безопасности в относительном формате с все сведения о безопасности в непрерывном блоке памяти. Возвращает значение false, если дескриптор безопасности в абсолютном формате. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute

Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в противном случае.

### <a name="remarks"></a>Примечания

Дескриптор безопасности в абсолютном формате содержит указатели на сведения, содержащиеся в ней, а не сами сведения. Дескриптор безопасности в относительном формате сведения в непрерывном блоке памяти. В дескрипторе безопасности относительный `SECURITY_DESCRIPTOR` структуры всегда начинается информацию, но дескриптор безопасности и другие компоненты могут иметь структуру, в любом порядке. Вместо использования адресов памяти, компоненты дескриптора безопасности относительный идентифицируются по смещения от начала дескриптор безопасности. Этот формат удобен в тех случаях, когда дескриптор безопасности должен быть на диске или передаются с помощью протокола связи. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative

Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительном формате.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если метод выполнен успешно, значение false в противном случае.

### <a name="remarks"></a>Примечания

Дескриптор безопасности в абсолютном формате содержит указатели на сведения, содержащиеся в ней, а не самой информацией. Дескриптор безопасности в относительном формате сведения в непрерывном блоке памяти. В дескрипторе безопасности относительный `SECURITY_DESCRIPTOR` структуры всегда начинается информацию, но дескриптор безопасности и другие компоненты могут иметь структуру, в любом порядке. Вместо использования адресов памяти, компоненты дескриптора безопасности, идентифицируются по смещения от начала дескриптор безопасности. Этот формат удобен в тех случаях, когда дескриптор безопасности должен быть на диске или передаются с помощью протокола связи. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors).

##  <a name="operator_eq"></a>  CSecurityDesc::operator =

Оператор присвоения.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`SECURITY_DESCRIPTOR` Структуры или `CSecurityDesc` объект для назначения `CSecurityDesc` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CSecurityDesc` объекта.

##  <a name="operator_const_security_descriptor__star"></a>  CSecurityDesc::operator const SECURITY_DESCRIPTOR *

Приводит значение к указателю на `SECURITY_DESCRIPTOR` структуры.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

##  <a name="setcontrol"></a>  CSecurityDesc::SetControl

Устанавливает управляющие биты дескриптора безопасности.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>Параметры

*ControlBitsOfInterest*<br/>
Маска SECURITY_DESCRIPTOR_CONTROL, которая указывает управляющие биты для задания. Список флагов, которые можно задать, см. в разделе [SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).

*ControlBitsToSet*<br/>
SECURITY_DESCRIPTOR_CONTROL маску, которая указывает новые значения управляющих битов, заданных *ControlBitsOfInterest* маски. Этот параметр может быть сочетанием флагов, указанных для *ControlBitsOfInterest* параметра.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).

##  <a name="setdacl"></a>  CSecurityDesc::SetDacl

Задает информацию в список управления доступом (DACL). Если список DACL в дескрипторе безопасности уже присутствует, он заменяется.

```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Dacl*<br/>
Ссылка на `CDacl` объект, указывающий список DACL для дескриптора безопасности. Этот параметр не должен иметь значение NULL. Чтобы задать НУЛЕВОЙ DACL в дескрипторе безопасности, в первой форме метода следует использовать с *bPresent* значение false.

*bPresent*<br/>
Задает флаг, указывающий на наличие списка DACL в дескрипторе безопасности. Если этот параметр имеет значение true, метод устанавливает флаг SE_DACL_PRESENT `SECURITY_DESCRIPTOR_CONTROL` структурировать и использует значения в *Dacl* и *bDefaulted* параметров. Если он имеет значение false, метод очищает флаг SE_DACL_PRESENT и *bDefaulted* учитывается.

*bDefaulted*<br/>
Задает флаг, указывающий источник списка DACL. Если этот флаг имеет значение true, получения списка DACL по какой-либо механизм по умолчанию. Если значение равно false, списка DACL был явно задан пользователем. Метод сохраняет его в флаг SE_DACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` структуры. Если этот параметр не указан, снят флаг SE_DACL_DEFAULTED.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Есть важное различие между пустой и несуществующие DACL. Если список DACL пуст, он содержит без элементов управления доступом и были явно предоставлены права доступа. Таким образом доступ к объекту будет отказано. Если у объекта имеется списки DACL, с другой стороны, без защиты, назначенное объекту, и любой запрос на доступ предоставляется.

##  <a name="setgroup"></a>  CSecurityDesc::SetGroup

Задает основную группу информацию абсолютном формате дескриптора безопасности, заменив данные основной группы уже присутствует.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*ИД безопасности*<br/>
Ссылка на [CSid](../../atl/reference/csid-class.md) объект для новой группы основной дескриптор безопасности. Этот параметр не должен иметь значение NULL. Дескриптор безопасности может быть помечен как не имеющий DACL и SACL, но он должен иметь группу и владелец, даже они являются пустой идентификатор безопасности (который является встроенной безопасности со специальным значением).

*bDefaulted*<br/>
Указывает ли основная группа сведений является производным от механизма по умолчанию. Если это значение равно true, сведения по умолчанию и метод сохраняет это значение как флаг SE_GROUP_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры. Если этот параметр равен нулю, флаг SE_GROUP_DEFAULTED очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

##  <a name="setowner"></a>  CSecurityDesc::SetOwner

Задает данные владельца дескриптора безопасности абсолютном формате. Он заменяет любые уже присутствует информация о владельце.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*ИД безопасности*<br/>
[CSid](../../atl/reference/csid-class.md) объекта для нового основного владельца дескриптора безопасности. Этот параметр не должен иметь значение NULL.

*bDefaulted*<br/>
Указывает, является ли информация о владельце производным от механизма по умолчанию. Если это значение равно true, то сведения по умолчанию. Метод сохраняет это значение как флаг SE_OWNER_DEFAULTED в `SECURITY_DESCRIPTOR_CONTROL` структуры. Если этот параметр равен нулю, флаг SE_OWNER_DEFAULTED очищается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

##  <a name="setsacl"></a>  CSecurityDesc::SetSacl

Задает информацию в системный список управления доступом (SACL). Если список SACL в дескрипторе безопасности уже присутствует, он заменяется.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>Параметры

*Системный список управления доступом*<br/>
Указатель на `CSacl` указании списка SACL для дескриптора безопасности объекта. Этот параметр не должен иметь значение NULL и должен быть объектом CSacl. В отличие от списков DACL нет никакой разницы между NULL и пустые системный список управления ДОСТУПОМ, как системный список управления ДОСТУПОМ объекта задают права доступа, только информации аудита.

*bDefaulted*<br/>
Задает флаг, указывающий источник списка SACL. Если этот флаг имеет значение true, получения списка SACL по какой-либо механизм по умолчанию. Если значение равно false, системный список управления ДОСТУПОМ был явно задан пользователем. Метод сохраняет его в флаг SE_SACL_DEFAULTED `SECURITY_DESCRIPTOR_CONTROL` структуры. Если этот параметр не указан, снят флаг SE_SACL_DEFAULTED.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

##  <a name="tostring"></a>  CSecurityDesc::ToString

Преобразует дескриптор безопасности в строковом формате.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>Параметры

*pstr*<br/>
Указатель на заканчивающуюся нулем строку, которая получит [формат строки дескриптора безопасности](/windows/desktop/SecAuthZ/security-descriptor-string-format).

*SI*<br/>
Задает сочетание SECURITY_INFORMATION битовых флагов, чтобы указать компоненты для включения в выходной строке дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Когда дескриптор безопасности в строковом формате, его можно легко быть хранятся или передаются. Используйте `CSecurityDesc::FromString` метод преобразует строку обратно в дескриптор безопасности.

*Si* параметр может содержать следующие флаги SECURITY_INFORMATION:

|Значение|Значение|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|Включить владельца.|
|GROUP_SECURITY_INFORMATION|Включить основную группу.|
|DACL_SECURITY_INFORMATION|Включить список DACL.|
|SACL_SECURITY_INFORMATION|Включить системный список управления ДОСТУПОМ.|

Если бит управления SE_DACL_PRESENT устанавливается в значение входного дескриптора безопасности списка DACL имеет значение NULL, происходит сбой метода.

Если список DACL равно NULL, а бит управления SE_DACL_PRESENT не установлен в значение входного дескриптора безопасности, результирующие строки дескриптора безопасности не имеет компонент D:. См. в разделе [строковый формат дескриптора безопасности](/windows/desktop/SecAuthZ/security-descriptor-string-format) для получения дополнительных сведений.

Этот метод вызывает метод [функция ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora).

## <a name="see-also"></a>См. также

[Образец безопасности](../../visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
