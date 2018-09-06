---
title: Класс CTokenPrivileges | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98fb1c50b6bdd46cc6cf0efe7739e8ada60f3274
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762639"
---
# <a name="ctokenprivileges-class"></a>Класс CTokenPrivileges

Этот класс является оболочкой для `TOKEN_PRIVILEGES` структуры.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CTokenPrivileges
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Конструктор.|
|[CTokenPrivileges::~CTokenPrivileges](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|Добавляет один или несколько прав для `CTokenPrivileges` объекта.|
|[CTokenPrivileges::Delete](#delete)|Удаляет привилегию с `CTokenPrivileges` объекта.|
|[CTokenPrivileges::DeleteAll](#deleteall)|Удаляет все привилегии из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetCount](#getcount)|Возвращает число записей привилегий в `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Извлекает отображаемые имена для прав доступа, содержащихся в `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetLength](#getlength)|Возвращает размер буфера в байтах, необходимый для хранения `TOKEN_PRIVILEGES` представленный структуры `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Извлекает имена привилегий и флаги атрибутов из `CTokenPrivileges` объекта.|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Возвращает указатель на `TOKEN_PRIVILEGES` структуры.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Получает атрибут, связанный с именем конкретное право доступа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Приводит значение к указателю на `TOKEN_PRIVILEGES` структуры.|
|[CTokenPrivileges::operator =](#operator_eq)|Оператор присвоения.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделяется для каждого вошедшего в систему Windows.

Маркер доступа используется для описания различных прав безопасности, предоставленные каждому пользователю. Права доступа состоит из 64-разрядное число, вызывается локальный уникальный идентификатор ( [LUID](/windows/desktop/api/winnt/ns-winnt-_luid)) и дескриптора строки.

`CTokenPrivileges` Класс является оболочкой для [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуру и содержит 0 или больше прав доступа. Можно добавить привилегии, удаляется или запрашиваемые, используя предоставленный класс методы.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="add"></a>  CTokenPrivileges::Add

Добавляет один или несколько прав для `CTokenPrivileges` объекта маркера доступа.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*  
Указатель на заканчивающуюся нулем строку, указывающее имя права, как определено в WINNT. Файл заголовка.

*bEnable*  
Значение true, если включена право доступа. Если значение равно false, привилегии отключен.

*rPrivileges*  
Ссылка на [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуры. Права и атрибуты, копируемых из этой структуры и добавляются в `CTokenPrivileges` объекта.

### <a name="return-value"></a>Возвращаемое значение

В первой форме этот метод возвращает значение true, если привилегии успешно добавлены, значение false в противном случае.

##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges

Конструктор.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>Параметры

*правая часть*  
`CTokenPrivileges` Объекта, чтобы назначить новый объект.

*rPrivileges*  
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуры, чтобы назначить новый `CTokenPrivileges` объекта.

### <a name="remarks"></a>Примечания

`CTokenPrivileges` Объекта при необходимости могут создаваться с использованием `TOKEN_PRIVILEGES` структуры или ранее определенную `CTokenPrivileges` объекта.

##  <a name="dtor"></a>  CTokenPrivileges:: ~ CTokenPrivileges

Деструктор

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Примечания

Деструктор освобождает все выделенные ресурсы.

##  <a name="delete"></a>  CTokenPrivileges::Delete

Удаляет привилегию с `CTokenPrivileges` объекта маркера доступа.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>Параметры

*pszPrivilege*  
Указатель на заканчивающуюся нулем строку, указывающее имя права, как определено в WINNT. Файл заголовка. Например этот параметр может указать константой SE_SECURITY_NAME или его соответствующую строку «SeSecurityPrivilege.»

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если право доступа успешно удален, и false в противном случае.

### <a name="remarks"></a>Примечания

Этот метод полезен, как это средство для создания маркеров ограниченного доступа.

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

Удаляет все привилегии из `CTokenPrivileges` объекта маркера доступа.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Примечания

Удаляет все привилегии, содержащихся в `CTokenPrivileges` объекта маркера доступа.

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

Извлекает отображаемые имена для прав доступа, содержащихся в `CTokenPrivileges` объекта маркера доступа.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>Параметры

*pDisplayNames*  
Указатель на массив объектов `CString`. `CNames` определяется как определение типа: `CTokenPrivileges::CAtlArray<CString>`.

### <a name="remarks"></a>Примечания

Параметр `pDisplayNames` является указателем на массив `CString` объектов, которые будут получать отображаемые имена, соответствующие привилегии, содержащихся в `CTokenPrivileges` объекта. Этот метод извлекает отображаемые имена только для указанных в разделе определенные привилегии WINNT полномочий. З.

Этот метод получает отображаемое имя: например, если имя атрибута SE_REMOTE_SHUTDOWN_NAME, отображаемое имя — «Принудительное завершение работы из удаленной системы.» Чтобы получить имя системы, используйте [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

Возвращает число записей привилегий в `CTokenPrivileges` объекта.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество привилегии, содержащихся в `CTokenPrivileges` объекта.

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

Возвращает длину `CTokenPrivileges` объекта.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число байтов, необходимое для хранения `TOKEN_PRIVILEGES` представленный структуры `CTokenPrivileges` объекта, включая все записи прав доступа, он содержит.

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pPrivileges*  
Указатель на массив [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) объектов. `CLUIDArray` typedef определяется как `CAtlArray<LUID> CLUIDArray`.

*pAttributes*  
Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, то атрибуты не извлекаются. `CAttributes` typedef определяется как `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Примечания

Данный метод перечисляет все привилегии, содержащихся в `CTokenPrivileges` доступа объекта маркера и поместить отдельных LUID и (необязательно) флаги атрибутов в массиве объектов.

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

Извлекает флаги из имени и атрибуту `CTokenPrivileges` объекта.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pNames*  
Указатель на массив `CString` объектов. `CNames` typedef определяется как `CAtlArray <CString> CNames`.

*pAttributes*  
Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, то атрибуты не извлекаются. `CAttributes` typedef определяется как `CAtlArray <DWORD> CAttributes`.

### <a name="remarks"></a>Примечания

Данный метод перечисляет все привилегии, содержащихся в `CTokenPrivileges` объекта, поместив имя и (необязательно) флаги атрибутов в массив объектов.

Этот метод получает имя атрибута, а не отображаемое имя: например, если имя атрибута SE_REMOTE_SHUTDOWN_NAME, системное имя — «SeRemoteShutdownPrivilege.» Чтобы получить отображаемое имя, используйте метод [CTokenPrivileges::GetDisplayNames](#getdisplaynames).

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

Возвращает указатель на `TOKEN_PRIVILEGES` структуры.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуры.

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

Получает атрибут, связанный с именем конкретное право доступа.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Параметры

*pszPrivilege*  
Указатель на заканчивающуюся нулем строку, указывающее имя права, как определено в WINNT. Файл заголовка. Например этот параметр может указать константой SE_SECURITY_NAME или его соответствующую строку «SeSecurityPrivilege.»

*pdwAttributes*  
Указатель на переменную, получающую атрибуты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если атрибут успешно извлечен, и false в противном случае.

##  <a name="operator_eq"></a>  CTokenPrivileges::operator =

Оператор присвоения.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>Параметры

*rPrivileges*  
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуры, чтобы назначить `CTokenPrivileges` объекта.

*правая часть*  
`CTokenPrivileges` Для присваивания объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CTokenPrivileges` объекта.

##  <a name="operator_const_token_privileges__star"></a>  CTokenPrivileges::operator const TOKEN_PRIVILEGES \*

Приводит значение к указателю на `TOKEN_PRIVILEGES` структуры.

```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Примечания

Приводит значение к указателю на [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) структуры.

## <a name="see-also"></a>См. также

[Образец безопасности](../../visual-cpp-samples.md)   
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)   
[LUID](/windows/desktop/api/winnt/ns-winnt-_luid)   
[ПОДРОБНОСТИ](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes)   
[Общие сведения о классе](../../atl/atl-class-overview.md)   
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
