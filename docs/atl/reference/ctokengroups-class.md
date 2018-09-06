---
title: Класс CTokenGroups | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87109793625435945c45b2643ccd674946acff49
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752649"
---
# <a name="ctokengroups-class"></a>Класс CTokenGroups

Этот класс является оболочкой для `TOKEN_GROUPS` структуры.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CTokenGroups
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|Конструктор.|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups::Add](#add)|Добавляет `CSid` или имеющиеся `TOKEN_GROUPS` структуру `CTokenGroups` объекта.|
|[CTokenGroups::Delete](#delete)|Удаляет `CSid` и связанных с ним атрибутов из `CTokenGroups` объекта.|
|[CTokenGroups::DeleteAll](#deleteall)|Удаляет все `CSid` объекты и связанные с ними атрибуты из `CTokenGroups` объекта.|
|[CTokenGroups::GetCount](#getcount)|Возвращает количество `CSid` объектов и связанных атрибутов, содержащихся в `CTokenGroups` объекта.|
|[CTokenGroups::GetLength](#getlength)|Возвращает размер `CTokenGroups` объекта.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Извлекает указатель на `TOKEN_GROUPS` структуры.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Извлекает `CSid` объекты и атрибуты, относящиеся к `CTokenGroups` объекта.|
|[CTokenGroups::LookupSid](#lookupsid)|Получает атрибуты, связанные с `CSid` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Приведения `CTokenGroups` объекта в указатель на `TOKEN_GROUPS` структуры.|
|[CTokenGroups::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделяется для каждого вошедшего в систему Windows.

`CTokenGroups` Класс является оболочкой для [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структура, содержащая сведения о идентификаторы безопасности (SID) группы в маркере доступа.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="add"></a>  CTokenGroups::Add

Добавляет `CSid` или имеющиеся `TOKEN_GROUPS` структуру `CTokenGroups` объекта.

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Параметры

*rSid*  
Объект [CSid](../../atl/reference/csid-class.md) объекта.

*dwAttributes*  
Атрибуты, связываемые с `CSid` объекта.

*rTokenGroups*  
Объект [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структуры.

### <a name="remarks"></a>Примечания

Эти методы позволяют добавить один или несколько `CSid` объекты и связанные с ними атрибуты для `CTokenGroups` объекта.

##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups

Конструктор.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*  
`CTokenGroups` Объекта или [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структуры с помощью которого создается `CTokenGroups` объекта.

### <a name="remarks"></a>Примечания

`CTokenGroups` Объекта при необходимости могут создаваться с использованием `TOKEN_GROUPS` структуры или ранее определенную `CTokenGroups` объекта.

##  <a name="dtor"></a>  CTokenGroups:: ~ CTokenGroups

Деструктор

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

##  <a name="delete"></a>  CTokenGroups::Delete

Удаляет `CSid` и связанных с ним атрибутов из `CTokenGroups` объекта.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Параметры

*rSid*  
[CSid](../../atl/reference/csid-class.md) объекта, для которого следует удалить идентификатор безопасности (SID) и атрибутов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если `CSid` удаляется, false в противном случае.

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

Удаляет все `CSid` объекты и связанные с ними атрибуты из `CTokenGroups` объекта.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

Возвращает количество `CSid` объектов, содержащихся в `CTokenGroups`.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество [CSid](../../atl/reference/csid-class.md) объекты и связанные с ними атрибуты содержатся в `CTokenGroups` объекта.

##  <a name="getlength"></a>  CTokenGroups::GetLength

Возвращает размер `CTokenGroup` объекта.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает общий размер `CTokenGroup` объекта в байтах.

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

Извлекает указатель на `TOKEN_GROUPS` структуры.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель на [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структуры, принадлежащих `CTokenGroups` объекта маркера доступа.

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

Извлекает `CSid` объектов и (необязательно) атрибуты, относящиеся к `CTokenGroups` объекта.

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pSids*  
Указатель на массив [CSid](../../atl/reference/csid-class.md) объектов.

*pAttributes*  
Указатель на массив DWORD. Если этот параметр опущен или имеет значение NULL, то атрибуты не извлекаются.

### <a name="remarks"></a>Примечания

Данный метод перечисляет все `CSid` объектов, содержащихся в `CTokenGroups` объекта и поместите их и (необязательно флаги атрибутов) в массиве объектов.

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

Получает атрибуты, связанные с `CSid` объекта.

```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*rSid*  
[CSid](../../atl/reference/csid-class.md) объекта.

*pdwAttributes*  
Указатель на значение типа DWORD, который будет принимать `CSid` атрибута объекта. Если опущен, либо значение NULL, не удалось получить атрибут.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если `CSid` найден, значение false в противном случае.

### <a name="remarks"></a>Примечания

Установка *pdwAttributes* для NULL предоставляет способ подтверждения существования `CSid` без доступа к атрибуту. Обратите внимание на то, что этот метод не должен использоваться для проверки прав доступа. Приложения должны вместо этого использовать [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) метод.

##  <a name="operator_eq"></a>  CTokenGroups::operator =

Оператор присвоения.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*  
`CTokenGroups` Объекта или [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структуры, чтобы назначить `CTokenGroups` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenGroups` объекта.

##  <a name="operator_const_token_groups__star"></a>  CTokenGroups::operator const TOKEN_GROUPS *

Приводит значение к указателю на `TOKEN_GROUPS` структуры.

```  
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Примечания

Приводит значение к указателю на [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) структуры.

## <a name="see-also"></a>См. также

[Образец безопасности](../../visual-cpp-samples.md)   
[Класс CSid](../../atl/reference/csid-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)   
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
