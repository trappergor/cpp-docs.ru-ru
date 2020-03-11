---
title: Класс Какл
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
ms.openlocfilehash: 5d03154597f800042846e82d0a0cf5e7c46b613f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864909"
---
# <a name="cacl-class"></a>Класс Какл

Этот класс является оболочкой для структуры `ACL` (списка управления доступом).

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAcl
```

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|[Какл:: Какцессмаскаррай](#caccessmaskarray)|Массив ACCESS_MASKs.|
|[Какл:: Кацефлагаррай](#caceflagarray)|Массив байтов.|
|[Какл:: Кацетипеаррай](#cacetypearray)|Массив байтов.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Какл:: Какл](#cacl)|Конструктор.|
|[Какл:: ~ Какл](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Какл:: Жетацекаунт](#getacecount)|Возвращает число объектов записи управления доступом (ACE).|
|[Какл:: Жетаклентриес](#getaclentries)|Извлекает записи списка управления доступом (ACL) из объекта `CAcl`.|
|[Какл:: Жетаклентри](#getaclentry)|Извлекает все сведения о записи в объекте `CAcl`.|
|[Какл:: DATALENGTH](#getlength)|Возвращает длину ACL.|
|[Какл:: Жетпакл](#getpacl)|Возвращает ПАКЛ (указатель на список управления доступом).|
|[Какл:: IsEmpty](#isempty)|Проверяет объект `CAcl` для записей.|
|[Какл:: IsNull](#isnull)|Возвращает состояние объекта `CAcl`.|
|[Какл:: Ремовеаце](#removeace)|Удаляет конкретный элемент ACE (запись управления доступом) из объекта `CAcl`.|
|[Какл:: Ремовеацес](#removeaces)|Удаляет все элементы ACE (записи управления доступом) из `CAcl`, которые применяются к заданному `CSid`.|
|[Какл:: Сетемпти](#setempty)|Помечает `CAcl` объект как пустой.|
|[Какл:: SetNull](#setnull)|Помечает объект `CAcl` как NULL.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Список ACL Какл:: operator const *](#operator_const_acl__star)|Приводит объект `CAcl` к структуре `ACL`.|
|[Какл:: operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Remarks

Структура `ACL` представляет собой заголовок списка ACL (список управления доступом). В список ACL входит последовательный список из нуля или более записей [ACE](/windows/win32/SecAuthZ/access-control-entries) (записи управления доступом). Отдельные элементы ACE в списке ACL нумеруются от 0 до *n – 1*, где *n* — число записей ACE в списке ACL. При редактировании списка управления доступом приложение ссылается на запись управления доступом (ACE) в списке управления доступом по индексу.

Существует два типа списков ACL:

- Разграничительного

- Система

Управление доступом на уровне пользователей осуществляется владельцем объекта или любым пользователем, которому предоставлен доступ к объекту WRITE_DAC. Он указывает, что доступ к конкретному пользователю и группам может иметь объект. Например, владелец файла может использовать избирательный список управления доступом для управления тем, какие пользователи и группы могут и не могут иметь доступ к файлу.

Объект также может иметь связанные с ним сведения о безопасности на уровне системы в виде списка управления доступом системы, управляемого системным администратором. Системный список управления доступом позволяет системному администратору выполнять аудит любых попыток получить доступ к объекту.

Дополнительные сведения см. в обсуждении [ACL](/windows/win32/SecAuthZ/access-control-lists) в Windows SDK.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="caccessmaskarray"></a>Какл:: Какцессмаскаррай

Массив объектов ACCESS_MASK.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Remarks

Это определение типа указывает тип массива, который можно использовать для хранения прав доступа, используемых в записях управления доступом (ACE).

##  <a name="caceflagarray"></a>Какл:: Кацефлагаррай

Массив байтов.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Remarks

Это определение типа определяет тип массива, используемый для определения управляющих флагов, относящихся к типу элемента управления доступом (ACE). Полный список возможных флагов см. в определении [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="cacetypearray"></a>Какл:: Кацетипеаррай

Массив байтов.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Remarks

Это определение типа определяет тип массива, используемый для определения природы объектов записи управления доступом (ACE), таких как ACCESS_ALLOWED_ACE_TYPE или ACCESS_DENIED_ACE_TYPE. Полный список возможных типов см. в определении [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="cacl"></a>Какл:: Какл

Конструктор.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Существующий объект `CAcl`.

### <a name="remarks"></a>Remarks

При необходимости можно создать объект `CAcl` с помощью существующего объекта `CAcl`.

##  <a name="dtor"></a>Какл:: ~ Какл

Деструктор

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Remarks

Деструктор освобождает все ресурсы, полученные объектом.

##  <a name="getacecount"></a>Какл:: Жетацекаунт

Возвращает число объектов записи управления доступом (ACE).

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число записей ACE в объекте `CAcl`.

##  <a name="getaclentries"></a>Какл:: Жетаклентриес

Извлекает записи списка управления доступом (ACL) из объекта `CAcl`.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*псидс*<br/>
Указатель на массив объектов [CSid](../../atl/reference/csid-class.md) .

*пакцессмаскс*<br/>
Маски доступа.

*пацетипес*<br/>
Типы записей управления доступом (ACE).

*пацефлагс*<br/>
Флаги ACE.

### <a name="remarks"></a>Remarks

Этот метод заполняет параметры массива сведениями о каждом объекте ACE, который содержится в объекте `CAcl`. Если сведения для определенного массива не требуются, используйте значение NULL.

Содержимое каждого массива соответствует друг другу, то есть первый элемент массива `CAccessMaskArray` соответствует первому элементу массива `CSidArray` и т. д.

Дополнительные сведения о типах и флагах ACE см. в разделе [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getaclentry"></a>Какл:: Жетаклентри

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

*ниндекс*<br/>
Индекс для извлекаемой записи ACL.

*Пустой pSid*<br/>
Объект [CSid](../../atl/reference/csid-class.md) , к которому применяется запись ACL.

*пмаск*<br/>
Маска, указывающая разрешения для предоставления или запрета доступа.

*птипе*<br/>
Тип ACE.

*пфлагс*<br/>
Флаги ACE.

*побжекттипе*<br/>
Тип объекта. Будет установлено значение GUID_NULL, если тип объекта не указан в элементе управления доступом или ACE не является элементом ACE объекта.

*пинхеритедобжекттипе*<br/>
Тип наследуемого объекта. Будет установлено значение GUID_NULL, если наследуемый тип объекта не указан в элементе управления доступом или элемент управления доступом не является элементом ACE объекта.

### <a name="remarks"></a>Remarks

Этот метод извлечет все сведения об отдельном элементе управления доступом, предоставляя больше информации, чем [какл:: жетаклентриес](#getaclentries) .

Дополнительные сведения о типах и флагах ACE см. в разделе [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) .

##  <a name="getlength"></a>Какл:: DATALENGTH

Возвращает длину списка управления доступом (ACL).

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает необходимую длину в байтах, необходимую для хранения структуры `ACL`.

##  <a name="getpacl"></a>Какл:: Жетпакл

Возвращает указатель на список управления доступом (ACL).

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на структуру `ACL`.

##  <a name="isempty"></a>Какл:: IsEmpty

Проверяет объект `CAcl` для записей.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Remarks

Возвращает значение TRUE, если объект `CAcl` не равен NULL и не содержит записей. Возвращает значение FALSE, если `CAcl` объект имеет значение NULL или содержит хотя бы одну запись.

##  <a name="isnull"></a>Какл:: IsNull

Возвращает состояние объекта `CAcl`.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если `CAcl` объект имеет значение NULL, в противном случае — значение FALSE.

##  <a name="operator_const_acl__star"></a>Список ACL Какл:: operator const *

Приводит объект `CAcl` к структуре `ACL` (списка управления доступом).

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Remarks

Возвращает адрес структуры `ACL`.

##  <a name="operator_eq"></a>Какл:: operator =

Оператор присвоения.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
`CAcl`, присваиваемый существующему объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный объект `CAcl`.

##  <a name="removeace"></a>Какл:: Ремовеаце

Удаляет конкретный элемент ACE (запись управления доступом) из объекта `CAcl`.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс удаляемой записи ACE.

### <a name="remarks"></a>Remarks

Этот метод является производным от [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat).

##  <a name="removeaces"></a>Какл:: Ремовеацес

Удаляет элементы ACE alls (записи управления доступом) из `CAcl`, которые применяются к заданному `CSid`.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Ссылка на объект `CSid`.

##  <a name="setempty"></a>Какл:: Сетемпти

Помечает `CAcl` объект как пустой.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Remarks

`CAcl` может быть пустым или равным NULL: два состояния различаются.

##  <a name="setnull"></a>Какл:: SetNull

Помечает объект `CAcl` как NULL.

```
void SetNull() throw();
```

### <a name="remarks"></a>Remarks

`CAcl` может быть пустым или равным NULL: два состояния различаются.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
