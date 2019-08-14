---
title: Класс Ксакл
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
ms.openlocfilehash: b75dc4110b785f0ab1f55ba5c31df7d3fc6fbd37
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915746"
---
# <a name="csacl-class"></a>Класс Ксакл

Этот класс является оболочкой для структуры SACL (системный доступ к списку управления).

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSacl : public CAcl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|Конструктор.|
|[CSacl::~CSacl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ксакл:: Аддаудитаце](#addauditace)|Добавляет запись управления доступом (ACE) аудита в `CSacl` объект.|
|[CSacl::GetAceCount](#getacecount)|Возвращает число записей управления доступом (ACE) в `CSacl` объекте.|
|[CSacl::RemoveAce](#removeace)|Удаляет конкретный элемент ACE (запись управления доступом) из `CSacl` объекта.|
|[Ксакл:: Ремовеаллацес](#removeallaces)|Удаляет все элементы ACE, содержащиеся в `CSacl` объекте.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ксакл:: operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

Список SACL содержит записи управления доступом (ACE), которые указывают типы попыток доступа, которые создают записи аудита в журнале событий безопасности контроллера домена. Обратите внимание, что список SACL создает записи журнала только на контроллере домена, где произошла попыток доступа, а не на каждом контроллере домена, содержащем реплику объекта.

Чтобы задать или получить список SACL в дескрипторе безопасности объекта, необходимо включить право SE_SECURITY_NAME в маркере доступа запрашивающего потока. Эта привилегия предоставляется группе "Администраторы" по умолчанию и может быть предоставлена другим пользователям или группам. Предоставление предоставленной привилегии не является обязательным: перед выполнением операции, определяемой привилегией, необходимо включить ее в маркере доступа безопасности, чтобы она вступила в силу. Модель позволяет включать привилегии только для конкретных операций системы, а затем отключена, когда они больше не нужны. Примеры включения SE_SECURITY_NAME см. в разделе [атлжетсакл](security-global-functions.md#atlgetsacl) и [атлсетсакл](security-global-functions.md#atlsetsacl) .

Используйте методы класса, предоставляемые для добавления, удаления, создания и удаления записей ACE из `SACL` объекта. См. также [атлжетсакл](security-global-functions.md#atlgetsacl) и [атлсетсакл](security-global-functions.md#atlsetsacl).

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/desktop/SecAuthZ/access-control) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[какл](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="addauditace"></a>Ксакл:: Аддаудитаце

Добавляет запись управления доступом (ACE) аудита в `CSacl` объект.

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

*рсид*<br/>
Объект [CSid](../../atl/reference/csid-class.md) .

*AccessMask*<br/>
Указывает маску прав доступа для аудита для указанного `CSid` объекта.

*бсукцесс*<br/>
Указывает, разрешены ли аудит попыток доступа. Установите для этого флага значение true, чтобы включить аудит. в противном случае задайте для него значение false.

*бфаилуре*<br/>
Указывает, следует ли выполнять аудит попыток отказа в доступе. Установите для этого флага значение true, чтобы включить аудит. в противном случае задайте для него значение false.

*AceFlags*<br/>
Набор битовых флагов, управляющих наследованием ACE.

*побжекттипе*<br/>
Тип объекта.

*пинхеритедобжекттипе*<br/>
Тип наследуемого объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если ACE добавляется к `CSacl` объекту, и false при сбое.

### <a name="remarks"></a>Примечания

`CSacl` Объект содержит записи управления доступом (ACE), которые указывают типы попыток доступа, которые создают записи аудита в журнале событий безопасности. Этот метод добавляет такой элемент управления доступом к `CSacl` объекту.

Описание различных флагов, которые можно задать в параметре *AceFlags* , см. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header) .

##  <a name="csacl"></a>  CSacl::CSacl

Конструктор.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующая `ACL` структура (список управления доступом).

### <a name="remarks"></a>Примечания

При необходимости можно создать `ACL` объектспомощьюсуществующейструктуры.`CSacl` Убедитесь, что этот параметр является системным списком управления доступом (SACL), а не списком управления доступом на уровне пользователей (DACL). В отладочных сборках, если указан список DACL, произойдет утверждение. В выпуске сборки все записи из списка DACL игнорируются.

##  <a name="dtor"></a>  CSacl::~CSacl

Деструктор

```
~CSacl() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом, включая все записи управления доступом (ACE).

##  <a name="getacecount"></a>  CSacl::GetAceCount

Возвращает число записей управления доступом (ACE) в `CSacl` объекте.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество записей ACE, содержащихся в `CSacl` объекте.

##  <a name="operator_eq"></a>Ксакл:: operator =

Оператор присвоения.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `ACL` (список управления доступом) для назначения существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CSacl` объект. Убедитесь, что `ACL` параметр на самом деле является системным списком управления доступом (SACL), а не списком управления доступом (DACL). В отладочных сборках выполняется утверждение, и в выпуске сборки `ACL` параметр будет проигнорирован.

##  <a name="removeace"></a>Ксакл:: Ремовеаце

Удаляет конкретный элемент ACE (запись управления доступом) из `CSacl` объекта.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс удаляемой записи ACE.

### <a name="remarks"></a>Примечания

Этот метод является производным от [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeallaces"></a>Ксакл:: Ремовеаллацес

Удаляет все записи управления доступом (ACE), содержащиеся в `CSacl` объекте.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все `ACE` структуры (если таковые имеются) `CSacl` в объекте.

## <a name="see-also"></a>См. также

[Класс CAcl](../../atl/reference/cacl-class.md)<br/>
[Списки](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Туз](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
