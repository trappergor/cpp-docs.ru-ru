---
title: Класс CAcl
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 458f7cd50462a145d005f3f81d87cc06fc7e01b1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748771"
---
# <a name="cacl-class"></a>Класс CAcl

Этот класс представляет собой `ACL` обертку для (список контроля доступа) структуры.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAcl
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Массив ACCESS_MASKs.|
|[CAcl::CAceFlagArray](#caceflagarray)|Массив BYTEs.|
|[CAcl::CAceTypeArray](#cacetypearray)|Массив BYTEs.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|Конструктор.|
|[CAcl::»CAcl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAcl:GetAceCount](#getacecount)|Возвращает количество объектов входа в систему управления доступом (ACE).|
|[CAcl:GetAclE записи](#getaclentries)|Извлекает записи списка контроля доступа (ACL) с `CAcl` объекта.|
|[CAcl:GetAclentry](#getaclentry)|Извлекает всю информацию о записи в объекте. `CAcl`|
|[CAcl::GetLength](#getlength)|Возвращает длину ACL.|
|[CAcl:GetPACL](#getpacl)|Возвращает PACL (указатель на ACL).|
|[CAcl::Isempty](#isempty)|Тестирует `CAcl` объект для записей.|
|[CAcl::Isnull](#isnull)|Возвращает состояние `CAcl` объекта.|
|[CAcl::RemoveAce](#removeace)|Удаляет с `CAcl` объекта определенный ACE (вход управления доступом).|
|[CAcl::RemoveAces](#removeaces)|Удаляет все ACEs (записи контроля доступа) из, `CAcl` `CSid`которые применяются к данному .|
|[CAcl::SetEmpty](#setempty)|Отметурует `CAcl` объект как пустой.|
|[CAcl::SetNull](#setnull)|Отметурует `CAcl` объект как NULL.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAcl:оператор const ACL](#operator_const_acl__star)|Отбрасывает `CAcl` объект в `ACL` структуру.|
|[CAcl::оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Remarks

Структура `ACL` является заголовком ACL (список контроля доступа). ACL включает в себя последовательный список нулевых или более [ACE](/windows/win32/SecAuthZ/access-control-entries) (записи контроля доступа). Индивидуальные ACEs в ACL пронумерованы от 0 до *n-1*, где *n* является числом ACEs в ACL. При редактировании ACL приложение ссылается на вход управления доступом (ACE) в ACL по своему индексу.

Есть два типа ACL:

- Дискреционные

- Система

Дискреционный ACL контролируется владельцем объекта или любым лицом, получивающим WRITE_DAC доступ к объекту. В нем указывается, что доступ к объекту может иметь определенные пользователи и группы. Например, владелец файла может использовать дискреционный ACL для контроля, какие пользователи и группы могут и не могут иметь доступ к файлу.

Объект может также иметь системную информацию безопасности, связанную с ним, в виде системы ACL, контролируемой системным администратором. Система ACL может позволить системного администратору проводить аудит любых попыток получить доступ к объекту.

Для получения более подробной информации смотрите обсуждение [ACL](/windows/win32/SecAuthZ/access-control-lists) в SDK Windows.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a>CAcl::CAccessMaskArray

Массив ACCESS_MASK объектов.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Remarks

Этот тип определяет тип массива, который может быть использован для хранения прав доступа, используемых в записях управления доступом (ACEs).

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a>CAcl::CAceFlagArray

Массив BYTEs.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Remarks

Этот тип определяет тип массива, используемый для определения флагов элемента управления доступом (ACE) типа управления. Ознакомьтесь с определением [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) для полного списка возможных флагов.

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a>CAcl::CAceTypeArray

Массив BYTEs.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Remarks

Этот тип определяет тип массива, используемый для определения характера объектов входа в элементы управления доступом (ACE), таких как ACCESS_ALLOWED_ACE_TYPE или ACCESS_DENIED_ACE_TYPE. Ознакомьтесь с определением [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) для полного списка возможных типов.

## <a name="caclcacl"></a><a name="cacl"></a>CAcl::CAcl

Конструктор.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующий объект `CAcl`.

### <a name="remarks"></a>Remarks

Объект `CAcl` может быть дополнительно создан `CAcl` с помощью существующего объекта.

## <a name="caclcacl"></a><a name="dtor"></a>CAcl::»CAcl

Деструктор

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Remarks

Деструктор освобождает любые ресурсы, приобретенные объектом.

## <a name="caclgetacecount"></a><a name="getacecount"></a>CAcl:GetAceCount

Возвращает количество объектов входа в систему управления доступом (ACE).

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей ACE `CAcl` в объекте.

## <a name="caclgetaclentries"></a><a name="getaclentries"></a>CAcl:GetAclE записи

Извлекает записи списка контроля доступа (ACL) с `CAcl` объекта.

```cpp
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSids*<br/>
Указатель на массив объектов [CSid.](../../atl/reference/csid-class.md)

*pAccessМаскМаски*<br/>
Маски доступа.

*pAceTypes*<br/>
Типы входа в элементы управления доступом (ACE).

*pAceFlags*<br/>
Флаги ACE.

### <a name="remarks"></a>Remarks

Этот метод заполняет параметры массива деталями каждого объекта `CAcl` ACE, содержащегося в объекте. Используйте NULL, когда детали для этого конкретного массива не требуются.

Содержимое каждого массива соответствует друг другу, то есть `CAccessMaskArray` первый элемент массива `CSidArray` соответствует первому элементу массива и так далее.

Более подробную информацию о типах и флагах ACE можно узнать [ACE_HEADER.](/windows/win32/api/winnt/ns-winnt-ace_header)

## <a name="caclgetaclentry"></a><a name="getaclentry"></a>CAcl:GetAclentry

Извлекает всю информацию о записи в списке контроля доступа (ACL).

```cpp
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс на вход ACL для получения.

*Psid*<br/>
Объект [CSid,](../../atl/reference/csid-class.md) к которому применяется запись ACL.

*pМаск*<br/>
Маска с указанием разрешений на предоставление или отказ в доступе.

*pType*<br/>
Тип ACE.

*pФлаги*<br/>
Флаги ACE.

*pObjectType*<br/>
Тип объекта. Это будет установлено для GUID_NULL если тип объекта не указан в ACE, или если ACE не является OBJECT ACE.

*pУнаследовалныйОбъектТип*<br/>
Тип объекта наследования. Это будет установлено для GUID_NULL если тип унаследованного объекта не указан в ACE, или если ACE не является OBJECT ACE.

### <a name="remarks"></a>Remarks

Этот метод будет получать всю информацию об отдельном ACE, предоставляя больше информации, чем [CAcl::GetAclE записи](#getaclentries) только делает доступными.

Более подробную информацию о типах и флагах ACE можно узнать [ACE_HEADER.](/windows/win32/api/winnt/ns-winnt-ace_header)

## <a name="caclgetlength"></a><a name="getlength"></a>CAcl::GetLength

Возвращает длину списка контроля доступа (ACL).

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает требуемую длину в байтах, необходимых для удержания `ACL` структуры.

## <a name="caclgetpacl"></a><a name="getpacl"></a>CAcl:GetPACL

Возвращает указатель в список контроля доступа (ACL).

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель в `ACL` структуру.

## <a name="caclisempty"></a><a name="isempty"></a>CAcl::Isempty

Тестирует `CAcl` объект для записей.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Remarks

Возвращает TRUE, `CAcl` если объект не является NULL, и не содержит записей. Возвращает FALSE, `CAcl` если объект либо NULL, или содержит по крайней мере одну запись.

## <a name="caclisnull"></a><a name="isnull"></a>CAcl::Isnull

Возвращает состояние `CAcl` объекта.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, `CAcl` если объект NULL, FALSE в противном случае.

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a>CAcl:оператор const ACL

Отбрасывает `CAcl` объект в `ACL` структуру (список контроля доступа).

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Remarks

Возвращает адрес `ACL` структуры.

## <a name="cacloperator-"></a><a name="operator_eq"></a>CAcl::оператор

Оператор присвоения.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Назначить `CAcl` существующий объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на `CAcl` обновленный объект.

## <a name="caclremoveace"></a><a name="removeace"></a>CAcl::RemoveAce

Удаляет с `CAcl` объекта определенный ACE (вход управления доступом).

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс на вход ACE для удаления.

### <a name="remarks"></a>Remarks

Этот метод получен из [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

## <a name="caclremoveaces"></a><a name="removeaces"></a>CAcl::RemoveAces

Удаляет все ACEs (записи контроля доступа) `CAcl` из данных `CSid`.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Параметры

*Rsid*<br/>
Ссылка на объект `CSid`.

## <a name="caclsetempty"></a><a name="setempty"></a>CAcl::SetEmpty

Отметурует `CAcl` объект как пустой.

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>Remarks

Можно `CAcl` установить на пустое или NULL: два состояния различны.

## <a name="caclsetnull"></a><a name="setnull"></a>CAcl::SetNull

Отметурует `CAcl` объект как NULL.

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>Remarks

Можно `CAcl` установить на пустое или NULL: два состояния различны.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
