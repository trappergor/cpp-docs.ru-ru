---
title: Класс Ктокенграупс
ms.date: 11/04/2016
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
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 4e5d06ca01201bf415afedbe6f6e5bca096f68fa
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915581"
---
# <a name="ctokengroups-class"></a>Класс Ктокенграупс

Этот класс является оболочкой для `TOKEN_GROUPS` структуры.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CTokenGroups
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ктокенграупс:: Ктокенграупс](#ctokengroups)|Конструктор.|
|[Ктокенграупс:: ~ Ктокенграупс](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTokenGroups::Add](#add)|Добавляет или существующую `TOKEN_GROUPS` структуру в `CTokenGroups` объект. `CSid`|
|[CTokenGroups::Delete](#delete)|Удаляет объект `CTokenGroups` и связанные с ним атрибуты из объекта. `CSid`|
|[CTokenGroups::DeleteAll](#deleteall)|Удаляет все `CSid` объекты и связанные `CTokenGroups` с ними атрибуты из объекта.|
|[CTokenGroups::GetCount](#getcount)|Возвращает количество `CSid` объектов и связанных атрибутов, содержащихся `CTokenGroups` в объекте.|
|[CTokenGroups::GetLength](#getlength)|Возвращает размер `CTokenGroups` объекта.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|Извлекает указатель на `TOKEN_GROUPS` структуру.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|Извлекает объекты и атрибуты, `CTokenGroups` принадлежащие объекту. `CSid`|
|[CTokenGroups::LookupSid](#lookupsid)|Извлекает атрибуты, связанные с `CSid` объектом.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ктокенграупс:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|Приводит объект к указателю `TOKEN_GROUPS` на структуру. `CTokenGroups`|
|[Ктокенграупс:: operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, который описывает контекст безопасности процесса или потока и выделяется каждому пользователю, вошедшему в систему Windows.

Класс `CTokenGroups` является оболочкой для структуры [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups), содержащей сведения об идентификаторах безопасности групп (SID) в маркере доступа.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/desktop/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="add"></a>  CTokenGroups::Add

Добавляет или существующую `TOKEN_GROUPS` структуру в `CTokenGroups` объект. `CSid`

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Объект [CSid](../../atl/reference/csid-class.md) .

*дваттрибутес*<br/>
Атрибуты, связываемые с `CSid` объектом.

*ртокенграупс*<br/>
Структура [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) .

### <a name="remarks"></a>Примечания

Эти методы добавляют в `CSid` `CTokenGroups` объект один или несколько объектов и связанных с ними атрибутов.

##  <a name="ctokengroups"></a>Ктокенграупс:: Ктокенграупс

Конструктор.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект или структура [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) , с `CTokenGroups` которой создается объект. `CTokenGroups`

### <a name="remarks"></a>Примечания

При необходимости `TOKEN_GROUPS` объект можно создать с помощью структуры или ранее определенного `CTokenGroups` объекта. `CTokenGroups`

##  <a name="dtor"></a>Ктокенграупс:: ~ Ктокенграупс

Деструктор

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

##  <a name="delete"></a>  CTokenGroups::Delete

Удаляет объект `CTokenGroups` и связанные с ним атрибуты из объекта. `CSid`

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Объект [CSid](../../atl/reference/csid-class.md) , для которого необходимо удалить идентификатор безопасности (SID) и атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CSid` если объект удален, и false в противном случае.

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

Удаляет все `CSid` объекты и связанные `CTokenGroups` с ними атрибуты из объекта.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

Возвращает количество `CSid` объектов, содержащихся в `CTokenGroups`.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число объектов [CSid](../../atl/reference/csid-class.md) и связанных с ними атрибутов, содержащихся в `CTokenGroups` объекте.

##  <a name="getlength"></a>  CTokenGroups::GetLength

Возвращает размер `CTokenGroup` объекта.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает общий размер `CTokenGroup` объекта в байтах.

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

Извлекает указатель на `TOKEN_GROUPS` структуру.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель на структуру [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) , принадлежащую `CTokenGroups` объекту маркера доступа.

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

Извлекает объекты и (необязательно) атрибуты, принадлежащие `CTokenGroups` объекту. `CSid`

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*псидс*<br/>
Указатель на массив объектов [CSid](../../atl/reference/csid-class.md) .

*паттрибутес*<br/>
Указатель на массив DWORD. Если этот параметр опущен или имеет значение NULL, атрибуты не извлекаются.

### <a name="remarks"></a>Примечания

Этот метод выполняет перечисление всех `CSid` объектов, содержащихся `CTokenGroups` в объекте, и помещает их и (необязательно) флаги атрибута в объекты Array.

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

Извлекает атрибуты, связанные с `CSid` объектом.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*рсид*<br/>
Объект [CSid](../../atl/reference/csid-class.md) .

*пдваттрибутес*<br/>
Указатель на DWORD, который будет принимать `CSid` атрибут объекта. Если значение не указано или равно NULL, атрибут не будет получен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CSid` если объект найден, и false в противном случае.

### <a name="remarks"></a>Примечания

Установка *пдваттрибутес* в значение NULL позволяет подтвердить существование `CSid` объекта без доступа к атрибуту. Обратите внимание, что этот метод не следует использовать для проверки прав доступа. Вместо этого в приложениях следует использовать метод [CAccessToken:: чекктокенмембершип](../../atl/reference/caccesstoken-class.md#checktokenmembership) .

##  <a name="operator_eq"></a>Ктокенграупс:: operator =

Оператор присвоения.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
Объект или структура [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) `CTokenGroups` для назначения объекту. `CTokenGroups`

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenGroups` объект.

##  <a name="operator_const_token_groups__star"></a>Ктокенграупс:: operator const TOKEN_GROUPS *

Приводит значение к указателю на `TOKEN_GROUPS` структуру.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Примечания

Приводит значение к указателю на структуру [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) .

## <a name="see-also"></a>См. также

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[Класс CSid](../../atl/reference/csid-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
