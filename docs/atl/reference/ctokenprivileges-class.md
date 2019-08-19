---
title: Класс Ктокенпривилежес
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 5f8379d20d8c8d525cd645e1d4aa0c751e16f531
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915536"
---
# <a name="ctokenprivileges-class"></a>Класс Ктокенпривилежес

Этот класс является оболочкой для `TOKEN_PRIVILEGES` структуры.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CTokenPrivileges
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Конструктор.|
|[CTokenPrivileges::~CTokenPrivileges](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|Добавляет один или несколько привилегий к `CTokenPrivileges` объекту.|
|[CTokenPrivileges::Delete](#delete)|Удаляет права доступа из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::DeleteAll](#deleteall)|Удаляет все привилегии из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetCount](#getcount)|Возвращает число записей привилегий в `CTokenPrivileges` объекте.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Извлекает отображаемые имена для привилегий, содержащихся в `CTokenPrivileges` объекте.|
|[CTokenPrivileges::GetLength](#getlength)|Возвращает размер буфера в байтах, необходимый для хранения `TOKEN_PRIVILEGES` структуры `CTokenPrivileges` , представленной объектом.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Возвращает имена привилегий и флаги атрибутов из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Возвращает указатель на `TOKEN_PRIVILEGES` структуру.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Извлекает атрибут, связанный с заданным именем привилегии.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ктокенпривилежес:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Приводит значение к указателю на `TOKEN_PRIVILEGES` структуру.|
|[Ктокенпривилежес:: operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, который описывает контекст безопасности процесса или потока и выделяется каждому пользователю, вошедшему в систему Windows.

Маркер доступа используется для описания различных привилегий безопасности, предоставляемых каждому пользователю. Привилегия состоит из 64-разрядного числа, которое называется локальным уникальным идентификатором ( [LUID](/windows/desktop/api/winnt/ns-winnt-luid)) и строкой дескриптора.

Класс `CTokenPrivileges` является оболочкой для структуры [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) и содержит 0 или более привилегий. Права доступа могут добавляться, удаляться или запрашиваться с помощью предоставленных методов класса.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/desktop/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="add"></a>  CTokenPrivileges::Add

Добавляет один или несколько привилегий к `CTokenPrivileges` объекту маркера доступа.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*псзпривилеже*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя привилегии, как определено в WINNT. Файл заголовка H.

*bEnable*<br/>
Если задано значение true, привилегия включена. Если задано значение false, привилегия отключена.

*рпривилежес*<br/>
Ссылка на структуру [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) . Права и атрибуты копируются из этой структуры и добавляются в `CTokenPrivileges` объект.

### <a name="return-value"></a>Возвращаемое значение

Первая форма этого метода возвращает значение true, если привилегии успешно добавлены, и false в противном случае.

##  <a name="ctokenprivileges"></a>Ктокенпривилежес:: Ктокенпривилежес

Конструктор.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*rhs*<br/>
`CTokenPrivileges` Объект, присваиваемый новому объекту.

*рпривилежес*<br/>
Структура [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) , которую нужно назначить новому `CTokenPrivileges` объекту.

### <a name="remarks"></a>Примечания

При необходимости `TOKEN_PRIVILEGES` объект можно создать с помощью структуры или ранее определенного `CTokenPrivileges` объекта. `CTokenPrivileges`

##  <a name="dtor"></a>Ктокенпривилежес:: ~ Ктокенпривилежес

Деструктор

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

##  <a name="delete"></a>  CTokenPrivileges::Delete

Удаляет привилегии из `CTokenPrivileges` объекта маркера доступа.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Параметры

*псзпривилеже*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя привилегии, как определено в WINNT. Файл заголовка H. Например, этот параметр может указывать константу SE_SECURITY_NAME или соответствующую строку «SeSecurityPrivilege».

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если привилегия успешно удалена; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод полезен в качестве средства для создания ограниченных маркеров.

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

Удаляет все привилегии из `CTokenPrivileges` объекта маркера доступа.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все привилегии, `CTokenPrivileges` содержащиеся в объекте маркера доступа.

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

Извлекает отображаемые имена для привилегий, содержащихся в `CTokenPrivileges` объекте маркера доступа.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Параметры

*пдисплайнамес*<br/>
Указатель на массив объектов `CString`. `CNames`определяется как typedef: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Примечания

Параметр `pDisplayNames` является указателем на `CString` массив объектов, которые будут принимать отображаемые имена, соответствующие привилегиям, `CTokenPrivileges` содержащимся в объекте. Этот метод извлекает отображаемые имена только для привилегий, указанных в разделе "определенные привилегии" в WINNT. Высоты.

Этот метод получает отображаемое имя: например, если имя атрибута — SE_REMOTE_SHUTDOWN_NAME, воспроизводимое имя — "принудительное завершение работы от удаленной системы". Чтобы получить имя системы, используйте [ктокенпривилежес:: жетнамесандаттрибутес](#getnamesandattributes).

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

Возвращает число записей привилегий в `CTokenPrivileges` объекте.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество привилегий, `CTokenPrivileges` содержащихся в объекте.

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

Возвращает длину `CTokenPrivileges` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число байтов, необходимое для хранения `TOKEN_PRIVILEGES` структуры, представленной `CTokenPrivileges` объектом, включая все записи прав доступа, которые он содержит.

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*ппривилежес*<br/>
Указатель на массив объектов [LUID](/windows/desktop/api/winnt/ns-winnt-luid) . `CLUIDArray`— Это определение типа, `CAtlArray<LUID> CLUIDArray`определенное как.

*паттрибутес*<br/>
Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, атрибуты не извлекаются. `CAttributes`— Это определение типа, `CAtlArray <DWORD> CAttributes`определенное как.

### <a name="remarks"></a>Примечания

Этот метод выполняет перечисление всех привилегий, содержащихся `CTokenPrivileges` в объекте маркера доступа, и помещает отдельные LUID и (необязательно) флаги атрибута в объекты Array.

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

Извлекает флаги имени и атрибута из `CTokenPrivileges` объекта.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*пнамес*<br/>
Указатель на массив `CString` объектов. `CNames`— Это определение типа, `CAtlArray <CString> CNames`определенное как.

*паттрибутес*<br/>
Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, атрибуты не извлекаются. `CAttributes`— Это определение типа, `CAtlArray <DWORD> CAttributes`определенное как.

### <a name="remarks"></a>Примечания

Этот метод выполняет перечисление всех привилегий, содержащихся `CTokenPrivileges` в объекте, помещая имя и (необязательно) флаги атрибута в объекты Array.

Этот метод получает имя атрибута, а не отображаемое имя: например, если имя атрибута — SE_REMOTE_SHUTDOWN_NAME, системным именем является "Серемотешутдовнпривилеже". Чтобы получить отображаемое имя, используйте метод [ктокенпривилежес::](#getdisplaynames)lt.

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

Возвращает указатель на `TOKEN_PRIVILEGES` структуру.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на структуру [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) .

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

Извлекает атрибут, связанный с заданным именем привилегии.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*псзпривилеже*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя привилегии, как определено в WINNT. Файл заголовка H. Например, этот параметр может указывать константу SE_SECURITY_NAME или соответствующую строку «SeSecurityPrivilege».

*пдваттрибутес*<br/>
Указатель на переменную, которая получает атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если атрибут успешно получен, и false в противном случае.

##  <a name="operator_eq"></a>Ктокенпривилежес:: operator =

Оператор присвоения.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*рпривилежес*<br/>
Структура [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) , которую необходимо назначить `CTokenPrivileges` объекту.

*rhs*<br/>
`CTokenPrivileges` Объект, присваиваемый объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenPrivileges` объект.

##  <a name="operator_const_token_privileges__star"></a>Ктокенпривилежес:: operator const TOKEN_PRIVILEGES\*

Приводит значение к указателю на `TOKEN_PRIVILEGES` структуру.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Примечания

Приводит значение к указателю на структуру [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) .

## <a name="see-also"></a>См. также

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-luid_and_attributes)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
