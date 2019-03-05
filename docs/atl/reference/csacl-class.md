---
title: Класс CSacl
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: f8820be3073c6ffaffdaa9d04a7338ad584d36ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267303"
---
# <a name="csacl-class"></a>Класс CSacl

Этот класс является оболочкой для структуры системный список управления ДОСТУПОМ (системный список управления доступом).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|Конструктор.|
|[CSacl::~CSacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|Добавляет запись аудита управления доступом (ACE) `CSacl` объекта.|
|[CSacl::GetAceCount](#getacecount)|Возвращает количество элементов управления доступом (ACE) в `CSacl` объекта.|
|[CSacl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CSacl` объекта.|
|[CSacl::RemoveAllAces](#removeallaces)|Удаляет все элементы управления доступом, содержащиеся в `CSacl` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CSacl::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

SACL содержит элементы управления доступом (ACE), указывающих типы попыток доступа, формирующих записи аудита в журнале событий безопасности контроллера домена. Обратите внимание на то, что список SACL создает записи журнала только на контроллере домена, где произошла попытка доступа, а не на каждом контроллере домена, который содержит реплику объекта.

Для задания или извлечения списка SACL в дескрипторе безопасности объекта, необходимо включить привилегией SE_SECURITY_NAME — в маркере доступа запрашивающего потока. Группы "Администраторы" имеет эту привилегию, определенным параметрами по умолчанию, и он может быть предоставлено другим пользователям или группам. Право предоставил не требуется: чтобы можно было выполнять операцию, определенную право, право доступа должно быть включено в маркере безопасности доступа для вступили в силу. Модель позволяет привилегий для включена только для определенной системы операций и затем отключены, когда они больше не требуются. См. в разделе [AtlGetSacl](security-global-functions.md#atlgetsacl) и [AtlSetSacl](security-global-functions.md#atlsetsacl) Примеры включения SE_SECURITY_NAME.

Используйте методы класса, позволяет добавлять, удалять, создавать и удалять элементы управления доступом из `SACL` объекта. См. также [AtlGetSacl](security-global-functions.md#atlgetsacl) и [AtlSetSacl](security-global-functions.md#atlsetsacl).

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="addauditace"></a>  CSacl::AddAuditAce

Добавляет запись аудита управления доступом (ACE) `CSacl` объекта.

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md) объекта.

*AccessMask*<br/>
Указывает маску прав доступа для аудита для указанного `CSid` объекта.

*bSuccess*<br/>
Указывает, являются ли попытки доступа, разрешенных для аудита. Установка этого флага значение true, чтобы включить аудит; в противном случае — значение false.

*bFailure*<br/>
Указывает, попытки запрещен доступ, нужно ли проводить аудит. Установка этого флага значение true, чтобы включить аудит; в противном случае — значение false.

*AceFlags*<br/>
Набор битовых флагов, контролировать и наследование ACE.

*pObjectType*<br/>
Тип объекта.

*pInheritedObjectType*<br/>
Типом наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если добавляется элемент управления ДОСТУПОМ `CSacl` объект, значение FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Объект `CSacl` объект содержит элементы управления доступом (ACE), указывающих типы попыток доступа, формирующих записи аудита в журнале событий безопасности. Этот метод добавляет такие ACE для `CSacl` объекта.

См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Описание различных флагов, которые можно задать в *AceFlags* параметра.

##  <a name="csacl"></a>  CSacl::CSacl

Конструктор.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
Существующий `ACL` структуры (список управления доступом).

### <a name="remarks"></a>Примечания

`CSacl` Можно при необходимости создать объект с помощью существующего `ACL` структуры. Убедитесь, что этот параметр используется системный список управления доступом (SACL), а не список управления доступом (DACL). В отладочных сборках, если список DACL предоставляется утверждение будет выполняться. В сборках выпуска игнорируются все записи из списка DACL.

##  <a name="dtor"></a>  CSacl::~CSacl

Деструктор

```
~CSacl() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все элементы управления доступом (ACE).

##  <a name="getacecount"></a>  CSacl::GetAceCount

Возвращает количество элементов управления доступом (ACE) в `CSacl` объекта.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов управления доступом, содержащиеся в `CSacl` объекта.

##  <a name="operator_eq"></a>  CSacl::operator =

Оператор присвоения.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`ACL` (Список управления доступом) для назначения к существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CSacl` объекта. Убедитесь, что `ACL` параметр имеет фактически system-списка управления доступом (SACL), а не список управления доступом (DACL). В отладочных сборках, утверждение будет выполняться и в сборках выпуска `ACL` параметр будет пропущен.

##  <a name="removeace"></a>  CSacl::RemoveAce

Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CSacl` объекта.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс записи ACE, которую требуется удалить.

### <a name="remarks"></a>Примечания

Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>  CSacl::RemoveAllAces

Удаляет все элементы управления доступом (ACE), содержащихся в `CSacl` объекта.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет каждый `ACE` структуры (если таковые имеются) в `CSacl` объекта.

## <a name="see-also"></a>См. также

[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[Списки управления доступом](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Элементы управления доступом](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
