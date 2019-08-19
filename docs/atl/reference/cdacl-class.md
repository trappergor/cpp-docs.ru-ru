---
title: Класс Кдакл
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 2bc962407bac947f475368b43f5039bca3c1da1e
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915818"
---
# <a name="cdacl-class"></a>Класс Кдакл

Этот класс является оболочкой для структуры DACL (список управления доступом на уровне пользователей).

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CDacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|Конструктор.|
|[CDacl::~CDacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|Добавляет разрешенный элемент управления доступом (запись контроля доступа) в `CDacl` объект.|
|[CDacl::AddDeniedAce](#adddeniedace)|Добавляет запрещенный ACE в `CDacl` объект.|
|[CDacl::GetAceCount](#getacecount)|Возвращает количество записей ACE (элементов управления доступом) в `CDacl` объекте.|
|[CDacl::RemoveAce](#removeace)|Удаляет конкретный элемент ACE (запись управления доступом) из `CDacl` объекта.|
|[CDacl::RemoveAllAces](#removeallaces)|Удаляет все элементы ACE, содержащиеся в `CDacl` объекте.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Кдакл:: operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Дескриптор безопасности объекта может содержать список DACL. Список DACL содержит ноль или более записей ACE (элементов управления доступом), которые определяют пользователей и группы, которым разрешен доступ к объекту. Если список DACL пуст (т. е. он содержит ноль ACE), доступ явно не предоставляется, поэтому доступ неявно запрещается. Однако если у дескриптора безопасности объекта нет DACL, объект не защищен и все пользователи имеют полный доступ.

Чтобы получить список DACL объекта, необходимо быть владельцем объекта или иметь READ_CONTROL доступ к объекту. Чтобы изменить список DACL объекта, необходимо иметь WRITE_DAC доступ к объекту.

Используйте предоставляемые методы класса для создания, добавления, удаления и удаления записей ACE из `CDacl` объекта. См. также [атлжетдакл](security-global-functions.md#atlgetdacl) и [атлсетдакл](security-global-functions.md#atlsetdacl).

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/desktop/SecAuthZ/access-control) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[какл](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

Добавляет разрешенный элемент управления доступом (запись контроля доступа) в `CDacl` объект.

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

*рсид*<br/>
Объект [CSid](../../atl/reference/csid-class.md) .

*AccessMask*<br/>
Указывает маску прав доступа для указанного `CSid` объекта.

*AceFlags*<br/>
Набор битовых флагов, управляющих наследованием ACE.

*побжекттипе*<br/>
Тип объекта.

*пинхеритедобжекттипе*<br/>
Тип наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ACE добавляется к `CDacl` объекту, и false при сбое.

### <a name="remarks"></a>Примечания

`CDacl` Объект содержит ноль или более записей ACE (элементов управления доступом), которые определяют пользователей и группы, которые имеют доступ к объекту. Этот метод добавляет запись ACE, которая разрешает доступ к `CDacl` объекту.

Описание различных флагов, которые можно задать в параметре `AceFlags`, см. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header).

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

Добавляет запрещенный ACE (запись управления доступом) в `CDacl` объект.

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

*рсид*<br/>
Объект `CSid`.

*AccessMask*<br/>
Указывает маску прав доступа для указанного `CSid` объекта.

*AceFlags*<br/>
Набор битовых флагов, управляющих наследованием ACE. По умолчанию принимает значение 0 в первой форме метода.

*побжекттипе*<br/>
Тип объекта.

*пинхеритедобжекттипе*<br/>
Тип наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ACE добавляется к `CDacl` объекту, и false при сбое.

### <a name="remarks"></a>Примечания

`CDacl` Объект содержит ноль или более записей ACE (элементов управления доступом), которые определяют пользователей и группы, которые имеют доступ к объекту. Этот метод добавляет запись ACE, запрещающую доступ к `CDacl` объекту.

Описание различных флагов, которые можно задать в параметре `AceFlags`, см. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header).

##  <a name="cdacl"></a>  CDacl::CDacl

Конструктор.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующая `ACL` структура (список управления доступом).

### <a name="remarks"></a>Примечания

При необходимости можно создать `ACL` объектспомощьюсуществующейструктуры.`CDacl` Важно отметить, что в качестве этого параметра следует передавать только списки DACL (избирательный список управления доступом), а не SACL (системный список управления доступом). В отладочных сборках передача списка SACL вызовет утверждение. В сборках выпуска, передача SACL приведет к тому, что элементы ACE (записи управления доступом) в списке ACL будут игнорироваться, и ошибки не будут возникать.

##  <a name="dtor"></a>  CDacl::~CDacl

Деструктор

```
~CDacl () throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом, включая все элементы ACE (записи управления доступом) с помощью [кдакл:: ремовеаллацес](#removeallaces).

##  <a name="getacecount"></a>  CDacl::GetAceCount

Возвращает количество записей ACE (элементов управления доступом) в `CDacl` объекте.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей ACE, содержащихся в `CDacl` объекте.

##  <a name="operator_eq"></a>Кдакл:: operator =

Оператор присвоения.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Список управления доступом (ACL) для назначения существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CDacl` объект.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что этой функции передан только DACL (избирательный список управления доступом). Передача SACL (системный список управления доступом) в эту функцию вызовет утверждение в отладочных сборках, но не приведет к ошибке в сборках выпуска.

##  <a name="removeace"></a>  CDacl::RemoveAce

Удаляет конкретный элемент ACE (запись управления доступом) из `CDacl` объекта.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс удаляемой записи ACE.

### <a name="remarks"></a>Примечания

Этот метод является производным от [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>Кдакл:: Ремовеаллацес

Удаляет все элементы ACE (записи управления доступом), содержащиеся в `CDacl` объекте.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет каждую `ACE` (запись управления доступом) структуру (если она `CDacl` есть) в объекте.

## <a name="see-also"></a>См. также

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[Списки](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Туз](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
