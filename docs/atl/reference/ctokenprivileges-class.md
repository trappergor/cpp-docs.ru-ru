---
title: "Класс CTokenPrivileges | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b6a7d1c76b9ddb0aa555e8856f26da99611f553
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ctokenprivileges-class"></a>Класс CTokenPrivileges
Этот класс является оболочкой для **TOKEN_PRIVILEGES** структуры.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CTokenPrivileges
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|Конструктор.|  
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenPrivileges::Add](#add)|Добавляет один или несколько прав для `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::Delete](#delete)|Удаление прав из `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::DeleteAll](#deleteall)|Удаляет все привилегии из `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetCount](#getcount)|Возвращает число записей прав доступа в `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|Извлекает отображаемые имена для прав доступа, содержащихся в `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetLength](#getlength)|Возвращает размер буфера в байтах, необходимый для хранения **TOKEN_PRIVILEGES** структура представлена `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|Возвращает имена прав доступа и флаги атрибутов из `CTokenPrivileges` объекта.|  
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|Возвращает указатель на **TOKEN_PRIVILEGES** структуры.|  
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|Получает атрибут, связанный с именем конкретное право доступа.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|Приводит значение к указателю на **TOKEN_PRIVILEGES** структуры.|  
|[CTokenPrivileges::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, зарегистрированного в системе Windows NT или Windows 2000.  
  
 Токен доступа используется для описания различных прав доступа безопасности, предоставленных для каждого пользователя. Права доступа состоит из 64-разрядное число, называемое локальный уникальный идентификатор ( [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)) и дескриптора строки.  
  
 `CTokenPrivileges` Класс является оболочкой для [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуру и содержит 0 или больше прав доступа. Можно добавить права, удаляется или запрашиваемые методами указанного класса.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="add"></a>CTokenPrivileges::Add  
 Добавляет один или несколько прав для `CTokenPrivileges` объекта маркера доступа.  
  
```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку с завершающим нулем, указывающее имя права, как определено в WINNT. Файл заголовка.  
  
 `bEnable`  
 Значение true, если включен право доступа. Если значение равно false, право отключен.  
  
 `rPrivileges`  
 Ссылка на [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуры. Права и атрибуты, скопированные из этой структуры и добавляются в `CTokenPrivileges` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой форме этот метод возвращает true, если права успешно добавлены, false в противном случае.  
  
##  <a name="ctokenprivileges"></a>CTokenPrivileges::CTokenPrivileges  
 Конструктор.  
  
```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CTokenPrivileges` Объекта, чтобы назначить новый объект.  
  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуры, чтобы назначить для нового `CTokenPrivileges` объекта.  
  
### <a name="remarks"></a>Примечания  
 `CTokenPrivileges` Можно при необходимости создать объект с помощью **TOKEN_PRIVILEGES** структуры или ранее определенную `CTokenPrivileges` объекта.  
  
##  <a name="dtor"></a>CTokenPrivileges:: ~ CTokenPrivileges  
 Деструктор  
  
```
virtual ~CTokenPrivileges() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы.  
  
##  <a name="delete"></a>CTokenPrivileges::Delete  
 Удаление прав из `CTokenPrivileges` объекта маркера доступа.  
  
```
bool Delete(LPCTSTR pszPrivilege) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку с завершающим нулем, указывающее имя права, как определено в WINNT. Файл заголовка. Например этот параметр может указать константа SE_SECURITY_NAME или его соответствующей строки «SeSecurityPrivilege».  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если право доступа успешно удален, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод полезен в качестве средства создания ограниченных маркеров в среде Windows 2000.  
  
##  <a name="deleteall"></a>CTokenPrivileges::DeleteAll  
 Удаляет все привилегии из `CTokenPrivileges` объекта маркера доступа.  
  
```
void DeleteAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все привилегии, содержащихся в `CTokenPrivileges` объекта маркера доступа.  
  
##  <a name="getdisplaynames"></a>CTokenPrivileges::GetDisplayNames  
 Извлекает отображаемые имена для прав доступа, содержащихся в `CTokenPrivileges` объекта маркера доступа.  
  
```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisplayNames`  
 Указатель на массив объектов `CString`. **Записей CNAME** определяется как typedef: **CTokenPrivileges::CAtlArray\<CString >**.  
  
### <a name="remarks"></a>Примечания  
 Параметр `pDisplayNames` является указателем на массив `CString` объекты, которые будут получать отображаемые имена, соответствующие права доступа, содержащихся в `CTokenPrivileges` объекта. Этот метод получает отображаемые имена только для прав доступа, указанных в разделе определенные права WINNT. З.  
  
 Этот метод возвращает отображаемое имя: например, если имя атрибута SE_REMOTE_SHUTDOWN_NAME, отображаемое имя — «Принудительное завершение работы из удаленной системы.» Чтобы получить имя системы, используйте [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes).  
  
##  <a name="getcount"></a>CTokenPrivileges::GetCount  
 Возвращает число записей прав доступа в `CTokenPrivileges` объекта.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число привилегий, содержащихся в `CTokenPrivileges` объекта.  
  
##  <a name="getlength"></a>CTokenPrivileges::GetLength  
 Возвращает длину `CTokenPrivileges` объекта.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число байтов, необходимое для хранения **TOKEN_PRIVILEGES** структура представлена `CTokenPrivileges` объекта, включая все записи прав доступа, он содержит.  
  
##  <a name="getluidsandattributes"></a>CTokenPrivileges::GetLuidsAndAttributes  
 Извлекает локально уникальные идентификаторы (LUID) и флаги атрибутов из `CTokenPrivileges` объекта.  
  
```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pPrivileges`  
 Указатель на массив [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) объектов. **CLUIDArray** typedef определяется как **CAtlArray\<LUID > CLUIDArray**.  
  
 `pAttributes`  
 Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, нельзя получить атрибуты. **CAttributes** typedef определяется как **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Примечания  
 Данный метод перечисляет все привилегии, содержащихся в `CTokenPrivileges` объекта маркера доступа и поместите отдельных LUID и (необязательно) флаги атрибутов в массив объектов.  
  
##  <a name="getnamesandattributes"></a>CTokenPrivileges::GetNamesAndAttributes  
 Получает флаги из имени и атрибуту `CTokenPrivileges` объекта.  
  
```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *pNames*  
 Указатель на массив `CString` объектов. **Записей CNAME** typedef определяется как **CAtlArray \<CString > записей CNAME**.  
  
 `pAttributes`  
 Указатель на массив объектов типа DWORD. Если этот параметр опущен или имеет значение NULL, нельзя получить атрибуты. **CAttributes** typedef определяется как **CAtlArray \<DWORD > CAttributes**.  
  
### <a name="remarks"></a>Примечания  
 Данный метод перечисляет все привилегии, содержащихся в `CTokenPrivileges` объекта, поместив имя и (необязательно) флаги атрибутов в массив объектов.  
  
 Этот метод получает имя атрибута, а не отображаемое имя: например, если SE_REMOTE_SHUTDOWN_NAME имя атрибута, системное имя — «SeRemoteShutdownPrivilege.» Чтобы получить отображаемое имя, используйте метод [CTokenPrivileges::GetDisplayNames](#getdisplaynames).  
  
##  <a name="getptoken_privileges"></a>CTokenPrivileges::GetPTOKEN_PRIVILEGES  
 Возвращает указатель на **TOKEN_PRIVILEGES** структуры.  
  
```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуры.  
  
##  <a name="lookupprivilege"></a>CTokenPrivileges::LookupPrivilege  
 Получает атрибут, связанный с именем конкретное право доступа.  
  
```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszPrivilege`  
 Указатель на строку с завершающим нулем, указывающее имя права, как определено в WINNT. Файл заголовка. Например этот параметр может указать константа SE_SECURITY_NAME или его соответствующей строки «SeSecurityPrivilege».  
  
 `pdwAttributes`  
 Указатель на переменную, получающую атрибуты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если атрибут успешно извлечен, и false в противном случае.  
  
##  <a name="operator_eq"></a>CTokenPrivileges::operator =  
 Оператор присвоения.  
  
```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rPrivileges`  
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуры, чтобы назначить для `CTokenPrivileges` объекта.  
  
 `rhs`  
 `CTokenPrivileges` Объект для объекта назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CTokenPrivileges` объекта.  
  
##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges::operator const TOKEN_PRIVILEGES *  
 Приводит значение к указателю на **TOKEN_PRIVILEGES** структуры.  
  
```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Приводит значение к указателю на [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) структуры.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [TOKEN_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [ПОДРОБНОСТИ](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
