---
title: Класс CDacl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3d0b817fc080ff81e11e1789387f50cb3e871e5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076013"
---
# <a name="cdacl-class"></a>Класс CDacl

Этот класс является оболочкой для структуры DACL (список управления доступом).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CDacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Конструктор.|
|[CDacl::~CDacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|Добавляет разрешенных ACE (записи управления доступом) `CDacl` объекта.|
|[CDacl::AddDeniedAce](#adddeniedace)|Добавляет запрещенный ACE для `CDacl` объекта.|
|[CDacl::GetAceCount](#getacecount)|Возвращает количество элементов управления доступом (элементы управления доступом) в `CDacl` объекта.|
|[CDacl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CDacl` объекта.|
|[CDacl::RemoveAllAces](#removeallaces)|Удаляет все элементы управления доступом, содержащиеся в `CDacl` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CDacl::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Дескриптор безопасности объекта может содержать список DACL. Список DACL содержит ноль или более записей ACE (элементы управления доступом), которые определяют пользователей и группы, которым разрешен доступ к объекту. Если список DACL пуст (то есть, он содержит ноль элементов управления доступом), нет доступа имеет явные разрешения, поэтому неявно отказано в доступе. Однако если дескриптора безопасности объекта не содержит список DACL, объект не защищен, и у всех есть полный доступ.

Чтобы получить список DACL объекта, необходимо быть владельцем объекта или иметь READ_CONTROL доступ к объекту. Чтобы изменить список DACL объекта, необходимо иметь WRITE_DAC доступ к объекту.

Используйте методы класса, который позволяет создавать, добавлять, удалять и удалить элементы управления доступом из `CDacl` объекта. См. также [AtlGetDacl](security-global-functions.md#atlgetdacl) и [AtlSetDacl](security-global-functions.md#atlsetdacl).

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

Добавляет разрешенных ACE (записи управления доступом) `CDacl` объекта.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
Объект [CSid](../../atl/reference/csid-class.md) объекта.

*AccessMask*<br/>
Указывает маску прав доступа разрешается для указанного `CSid` объекта.

*AceFlags*<br/>
Набор битовых флагов, контролировать и наследование ACE.

*pObjectType*<br/>
Тип объекта.

*pInheritedObjectType*<br/>
Типом наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если добавляется элемент управления ДОСТУПОМ `CDacl` объект, значение FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Объект `CDacl` объект содержит ноль или более записей ACE (элементы управления доступом), которые определяют пользователей и группы, которым разрешен доступ к объекту. Этот метод добавляет элемент управления ДОСТУПОМ, которое разрешает доступ к `CDacl` объекта.

См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Описание различных флагов, которые можно задать в `AceFlags` параметра.

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

Добавляет запрещенный ACE (записи управления доступом) `CDacl` объекта.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
Объект `CSid`.

*AccessMask*<br/>
Указывает маску прав доступа, запрещается для указанного `CSid` объекта.

*AceFlags*<br/>
Набор битовых флагов, контролировать и наследование ACE. По умолчанию равен 0 в первой форме метода.

*pObjectType*<br/>
Тип объекта.

*pInheritedObjectType*<br/>
Типом наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если добавляется элемент управления ДОСТУПОМ `CDacl` объект, значение FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Объект `CDacl` объект содержит ноль или более записей ACE (элементы управления доступом), которые определяют пользователей и группы, которым разрешен доступ к объекту. Этот метод добавляет элемент управления ДОСТУПОМ, которое запрещает доступ к `CDacl` объекта.

См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Описание различных флагов, которые можно задать в `AceFlags` параметра.

##  <a name="cdacl"></a>  CDacl::CDacl

Конструктор.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
Существующий `ACL` структуры (список управления доступом).

### <a name="remarks"></a>Примечания

`CDacl` Можно при необходимости создать объект с помощью существующего `ACL` структуры. Важно отметить, что только список DACL (список управления доступом), а не системный список управления ДОСТУПОМ (список управления доступом системы), должны быть переданы в качестве этого параметра. В отладочных сборках передача SACL вызывает метод ASSERT. В сборках выпуска передав SACL приведет к записи ACE (элементы управления доступом) в списке управления Доступом, пропускаются и ошибок не происходит.

##  <a name="dtor"></a>  CDacl::~CDacl

Деструктор

```
~CDacl () throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все элементы управления доступом (элементы управления доступом) с помощью [CDacl::RemoveAllAces](#removeallaces).

##  <a name="getacecount"></a>  CDacl::GetAceCount

Возвращает количество элементов управления доступом (элементы управления доступом) в `CDacl` объекта.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов управления доступом, содержащиеся в `CDacl` объекта.

##  <a name="operator_eq"></a>  CDacl::operator =

Оператор присвоения.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
ACL (список управления доступом) для назначения к существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CDacl` объекта.

### <a name="remarks"></a>Примечания

Необходимо обеспечить только передать список DACL (список управления доступом) для этой функции. Передача SACL (системный список управления доступом) для этой функции вызовет УТВЕРЖДЕНИЕ в отладочных сборках но приведет к сообщение об ошибке не в сборках выпуска.

##  <a name="removeace"></a>  CDacl::RemoveAce

Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CDacl` объекта.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс записи ACE, которую требуется удалить.

### <a name="remarks"></a>Примечания

Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>  CDacl::RemoveAllAces

Удаляет все элементы ACE (элементы управления доступом), содержащихся в `CDacl` объекта.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет каждый `ACE` структуры (записи управления доступом) (если таковые имеются) в `CDacl` объекта.

## <a name="see-also"></a>См. также

[Образец безопасности](../../visual-cpp-samples.md)<br/>
[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[Списки управления доступом](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Элементы управления доступом](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
