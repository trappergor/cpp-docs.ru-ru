---
title: Класс CPrivateObjectSecurityDesc
ms.date: 11/04/2016
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
ms.openlocfilehash: 2fcfdfecab649b571047613ec0889b02d2c7a7a0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331416"
---
# <a name="cprivateobjectsecuritydesc-class"></a>Класс CPrivateObjectSecurityDesc

Этот класс представляет собой объект дескриптора безопасности частного объекта.

## <a name="syntax"></a>Синтаксис

```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Конструктор.|
|[CPrivateObjectSecurityDesc:: :: »CPrivateObjectSecurityDesc](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPrivateObjectSecurityDesc::ConvertToAutoНаследовайте](#converttoautoinherit)|Вызовите этот метод для преобразования дескриптора безопасности и его списков контроля доступа (ACLs) в формат, поддерживающий автоматическое распространение наследственных записей управления доступом (ACE).|
|[CPrivateObjectSecurityDesc::Создание](#create)|Вызовите этот метод, чтобы выделить и инициализировать самородственники дескриптора безопасности для частного объекта, созданного менеджером ресурсов вызова.|
|[CPrivateObjectSecurityDesc::: Получить](#get)|Вызовите этот метод для извлечения информации из дескриптора безопасности частного объекта.|
|[CPrivateObjectSecurityDesc::Set](#set)|Вызовите этот метод, чтобы изменить дескриптор безопасности частного объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Remarks

Этот класс, полученный из [CSecurityDesc,](../../atl/reference/csecuritydesc-class.md)предоставляет методы создания и управления дескриптором безопасности частного объекта.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

`CPrivateObjectSecurityDesc`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoНаследовайте

Вызовите этот метод для преобразования дескриптора безопасности и его списков контроля доступа (ACLs) в формат, поддерживающий автоматическое распространение наследственных записей управления доступом (ACE).

```
bool ConvertToAutoInherit(
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
Указатель на объект [CSecurityDesc,](../../atl/reference/csecuritydesc-class.md) ссылающийся на родительский контейнер объекта. Если нет родительского контейнера, этот параметр является NULL.

*Objecttype*<br/>
Указатель на `GUID` структуру, идентифицирующую тип объекта, связанного с текущим объектом. Установите *ObjectType* в NULL, если объект не имеет GUID.

*bIsDirectoryObject*<br/>
Определяет, может ли новый объект содержать другие объекты. Значение истины указывает на то, что новый объект является контейнером. Значение ложного указывает на то, что новый объект не является контейнером.

*GenericMapping*<br/>
Указатель на [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) структуру, которая определяет отображение от каждого общего права на конкретные права объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Этот метод пытается определить, были ли ACE в дискреционном списке контроля доступа (DACL) и списке управления доступом системы (SACL) текущего дескриптора безопасности унаследованы от дескриптора родительской безопасности. Он вызывает [функцию ConvertToAutoInheritPrivateObjectSecurity.](/windows/win32/api/securitybaseapi/nf-securitybaseapi-converttoautoinheritprivateobjectsecurity)

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc

Конструктор.

```
CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Remarks

Инициализирует объект `CPrivateObjectSecurityDesc`.

## <a name="cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>CPrivateObjectSecurityDesc:: :: »CPrivateObjectSecurityDesc

Деструктор

```
~CPrivateObjectSecurityDesc() throw();
```

### <a name="remarks"></a>Remarks

Деструктор освобождает все выделенные ресурсы и удаляет дескриптор безопасности частного объекта.

## <a name="cprivateobjectsecuritydesccreate"></a><a name="create"></a>CPrivateObjectSecurityDesc::Создание

Вызовите этот метод, чтобы выделить и инициализировать самородственники дескриптора безопасности для частного объекта, созданного менеджером ресурсов вызова.

```
bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
Указатель на объект [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) ссылается на родительский каталог, в котором создается новый объект. Установите NULL, если нет родительского каталога.

*pCreator*<br/>
Указатель на дескриптор безопасности, предоставленный создателем объекта. Если создатель объекта явно не передает информацию о безопасности для нового объекта, установите этот параметр в NULL.

*bIsDirectoryObject*<br/>
Определяет, может ли новый объект содержать другие объекты. Значение истины указывает на то, что новый объект является контейнером. Значение ложного указывает на то, что новый объект не является контейнером.

*токен*.<br/>
Ссылка на объект [CAccessToken](../../atl/reference/caccesstoken-class.md) для процесса клиента, от имени которого создается объект.

*GenericMapping*<br/>
Указатель на [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) структуру, которая определяет отображение от каждого общего права на конкретные права объекта.

*Objecttype*<br/>
Указатель на `GUID` структуру, идентифицирующую тип объекта, связанного с текущим объектом. Установите *ObjectType* в NULL, если объект не имеет GUID.

*bIsContainerObject*<br/>
Определяет, может ли новый объект содержать другие объекты. Значение истины указывает на то, что новый объект является контейнером. Значение ложного указывает на то, что новый объект не является контейнером.

*АвтонаследыФлаги*<br/>
Набор битовых флагов, которые контролируют, как записи контроля доступа (ACEs) наследуются от *pParent.* Более подробную информацию можно узнать на [примере CreatePrivateObjectSecurityEx.](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Этот метод вызывает [CreatePrivateObjectSercurity](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurity) или [CreatePrivateObjectSecurityEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex).

Второй метод позволяет указывать тип объекта GUID нового объекта или контролировать, как наследуются АКЕ.

> [!NOTE]
> Самородственники безопасности дескриптор является дескрипторбезопасности безопасности, который хранит всю свою информацию о безопасности в сопредельном блоке памяти.

## <a name="cprivateobjectsecuritydescget"></a><a name="get"></a>CPrivateObjectSecurityDesc::: Получить

Вызовите этот метод для извлечения информации из дескриптора безопасности частного объекта.

```
bool Get(
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```

### <a name="parameters"></a>Параметры

*Si*<br/>
Набор битовых флагов, указывающих на части дескриптора безопасности для извлечения. Это значение может быть сочетанием [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) бит флагов.

*pResult*<br/>
Указатель на объект [CSecurityDesc,](../../atl/reference/csecuritydesc-class.md) который получает копию запрошенной информации из указанного дескриптора безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Дескриптор безопасности — это структура и связанные с ними данные, содержащие информацию о безопасности для охраняемого объекта.

## <a name="cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>CPrivateObjectSecurityDesc::оператор

Оператор присвоения.

```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект `CPrivateObjectSecurityDesc`, который присваивается текущему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CPrivateObjectSecurityDesc` объект.

## <a name="cprivateobjectsecuritydescset"></a><a name="set"></a>CPrivateObjectSecurityDesc::Set

Вызовите этот метод, чтобы изменить дескриптор безопасности частного объекта.

```
bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```

### <a name="parameters"></a>Параметры

*Si*<br/>
Набор битовых флагов, указывающих на части дескриптора безопасности для установки. Это значение может быть сочетанием [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) бит флагов.

*Изменение*<br/>
Указатель на объект [CSecurityDesc.](../../atl/reference/csecuritydesc-class.md) Части этого дескриптора безопасности, указанные параметром *si,* применяются к дескриптору безопасности объекта.

*GenericMapping*<br/>
Указатель на [GENERIC_MAPPING](/windows/win32/api/winnt/ns-winnt-generic_mapping) структуру, которая определяет отображение от каждого общего права на конкретные права объекта.

*токен*.<br/>
Ссылка на объект [CAccessToken](../../atl/reference/caccesstoken-class.md) для процесса клиента, от имени которого создается объект.

*АвтонаследыФлаги*<br/>
Набор битовых флагов, которые контролируют, как записи контроля доступа (ACEs) наследуются от *pParent.* Более подробную информацию можно узнать на [примере CreatePrivateObjectSecurityEx.](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createprivateobjectsecurityex)

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Второй метод позволяет указывать тип объекта GUID объекта или контролировать, как наследуются АКЕ.

## <a name="see-also"></a>См. также раздел

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)<br/>
[Класс CSecurityDesc](../../atl/reference/csecuritydesc-class.md)
