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
ms.openlocfilehash: 05d9d5fe9cc344be3f903f247f34003056404c9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247656"
---
# <a name="cacl-class"></a>Класс CAcl

Этот класс является оболочкой для `ACL` структуры (список управления доступом).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAcl
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Массив ACCESS_MASKs.|
|[CAcl::CAceFlagArray](#caceflagarray)|Массив байтов.|
|[CAcl::CAceTypeArray](#cacetypearray)|Массив байтов.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|Конструктор.|
|[CAcl:: ~ CAcl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|Возвращает количество управления доступом объектов управления доступом.|
|[CAcl::GetAclEntries](#getaclentries)|Получает записи списка управления Доступом управления доступом из `CAcl` объекта.|
|[CAcl::GetAclEntry](#getaclentry)|Извлекает все сведения о записи в `CAcl` объекта.|
|[CAcl::GetLength](#getlength)|Возвращает длину списка управления Доступом.|
|[CAcl::GetPACL](#getpacl)|Возвращает ПАКЕТА (указатель на список управления Доступом).|
|[CAcl::IsEmpty](#isempty)|Тесты `CAcl` объект для записи.|
|[CAcl::IsNull](#isnull)|Возвращает состояние `CAcl` объекта.|
|[CAcl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CAcl` объекта.|
|[CAcl::RemoveAces](#removeaces)|Удаляет все элементы управления доступом (элементы управления доступом) из `CAcl` , применяемые к данной `CSid`.|
|[CAcl::SetEmpty](#setempty)|Метки `CAcl` объекта считается пустым.|
|[CAcl::SetNull](#setnull)|Метки `CAcl` объект как NULL.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CAcl::operator const ACL *](#operator_const_acl__star)|Приведения `CAcl` объект `ACL` структуры.|
|[CAcl::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

`ACL` Структуры является заголовком списков ACL (список управления доступом). Список ACL содержит последовательный список из нуля или более [записи ACE](/windows/desktop/SecAuthZ/access-control-entries) (элементы управления доступом). Отдельные ACE в списке ACL нумеруются от 0 до *n-1*, где *n* — количество записей ACE в списке управления Доступом. При редактировании ACL, приложение обращается к записи управления доступом (ACE) в список управления Доступом по его индексу.

Существует два типа ACL:

- На уровне пользователей

- Система

Таблицы управления Доступом контролируется владельцем объекта или любой пользователь предоставил WRITE_DAC доступ к объекту. Он указывает на объект может иметь доступ конкретными пользователями и группами. Например владелец файла можно использовать таблицы управления Доступом к элементу управления, каким пользователям и группам можно и не может иметь доступ к файлу.

Объект также может иметь сведения системного уровня безопасности, связанные с ним, в форме системы ACL, управляются системным администратором. Список управления Доступом системы можно разрешить системному администратору, чтобы любые попытки получить доступ к объекту аудита.

Дополнительные сведения см. в разделе [ACL](/windows/desktop/SecAuthZ/access-control-lists) обсуждения в пакете Windows SDK.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray

Массив объектов ACCESS_MASK.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Примечания

Это определение типа задает тип массива, который может использоваться для хранения используются права доступа в записи управления доступом (ACE).

##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray

Массив байтов.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Примечания

Это определение типа задает тип массива, используемый для определения флагов управления конкретного типа управления доступом управления доступом. См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) определение для получения полного списка флаги.

##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray

Массив байтов.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Примечания

Это определение типа задает тип массива, используемый для определения природы управления доступом (ACE) запись такие объекты, как ACCESS_ALLOWED_ACE_TYPE или ACCESS_DENIED_ACE_TYPE. См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) определения для получения полного списка возможных типов.

##  <a name="cacl"></a>  CAcl::CAcl

Конструктор.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
Существующий объект `CAcl`.

### <a name="remarks"></a>Примечания

`CAcl` Можно при необходимости создать объект с помощью существующего `CAcl` объекта.

##  <a name="dtor"></a>  CAcl:: ~ CAcl

Деструктор

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все ресурсы, полученные объектом.

##  <a name="getacecount"></a>  CAcl::GetAceCount

Возвращает количество управления доступом объектов управления доступом.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число записей ACE в `CAcl` объекта.

##  <a name="getaclentries"></a>  CAcl::GetAclEntries

Получает записи списка управления Доступом управления доступом из `CAcl` объекта.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSids*<br/>
Указатель на массив [CSid](../../atl/reference/csid-class.md) объектов.

*pAccessMasks*<br/>
Маски доступа.

*pAceTypes*<br/>
Управление доступом (ACE) типы.

*pAceFlags*<br/>
Флаги элементов управления ДОСТУПОМ.

### <a name="remarks"></a>Примечания

Этот метод заполняет параметров массива с описанием каждого элемента управления ДОСТУПОМ объекта, содержащегося в `CAcl` объекта. Используйте значение NULL, если подробные сведения о конкретной массива не являются обязательными.

Содержимое каждого массива соответствуют друг к другу, то есть первый элемент `CAccessMaskArray` соответствует на первый элемент в массиве `CSidArray` массива и т. д.

См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Дополнительные сведения о типах элементов управления ДОСТУПОМ и флагами.

##  <a name="getaclentry"></a>  CAcl::GetAclEntry

Извлекает все сведения о записи в списке управления доступом (ACL).

```
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

*nIndex*<br/>
Индекс извлекаемой записи ACL.

*pSid*<br/>
[CSid](../../atl/reference/csid-class.md) объекта, к которому относится запись ACL.

*pMask*<br/>
Маска, задающая разрешения, чтобы предоставить или запретить доступ.

*pType*<br/>
Тип элемента управления ДОСТУПОМ.

*pFlags*<br/>
Флаги элементов управления ДОСТУПОМ.

*pObjectType*<br/>
Тип объекта. Это будет присвоено значение GUID_NULL, если тип объекта не указан в записи ACE, или в том случае, если элемент управления ДОСТУПОМ не запись ACE для ОБЪЕКТА.

*pInheritedObjectType*<br/>
Типом наследуемого объекта. Это будут устанавливаться значение GUID_NULL, если типом наследуемого объекта не указан в записи ACE, или в том случае, если элемент управления ДОСТУПОМ не элемент управления ДОСТУПОМ ОБЪЕКТА.

### <a name="remarks"></a>Примечания

Этот метод извлечет все сведения об отдельных ACE, предоставляя больше информации, чем [CAcl::GetAclEntries](#getaclentries) отдельно делает доступными.

См. в разделе [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) Дополнительные сведения о типах элементов управления ДОСТУПОМ и флагами.

##  <a name="getlength"></a>  CAcl::GetLength

Возвращает длину в список управления доступом (ACL).

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает требуемую длину в байтах, необходимого для хранения `ACL` структуры.

##  <a name="getpacl"></a>  CAcl::GetPACL

Возвращает указатель на список управления доступом (ACL).

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на `ACL` структуры.

##  <a name="isempty"></a>  CAcl::IsEmpty

Тесты `CAcl` объект для записи.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает значение TRUE, если `CAcl` объект не имеет значение NULL и не содержит записей. Возвращает значение FALSE, если `CAcl` объект имеет значение NULL или содержит по крайней мере одну запись.

##  <a name="isnull"></a>  CAcl::IsNull

Возвращает состояние `CAcl` объекта.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если `CAcl` объект имеет значение NULL, и FALSE в противном случае.

##  <a name="operator_const_acl__star"></a>  CAcl::operator const ACL *

Приведения `CAcl` объект `ACL` структуры (список управления доступом).

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Примечания

Возвращает адрес `ACL` структуры.

##  <a name="operator_eq"></a>  CAcl::operator =

Оператор присвоения.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*<br/>
`CAcl` Для назначения к существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CAcl` объекта.

##  <a name="removeace"></a>  CAcl::RemoveAce

Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CAcl` объекта.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс записи ACE, которую требуется удалить.

### <a name="remarks"></a>Примечания

Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeaces"></a>  CAcl::RemoveAces

Удаляет записи ACE alls (элементы управления доступом) из `CAcl` , применяемые к данной `CSid`.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Параметры

*rSid*<br/>
Ссылка на объект `CSid`.

##  <a name="setempty"></a>  CAcl::SetEmpty

Метки `CAcl` объекта считается пустым.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Примечания

`CAcl` Можно задать пустой или значение NULL: два состояния отличаются.

##  <a name="setnull"></a>  CAcl::SetNull

Метки `CAcl` объект как NULL.

```
void SetNull() throw();
```

### <a name="remarks"></a>Примечания

`CAcl` Можно задать пустой или значение NULL: два состояния отличаются.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
