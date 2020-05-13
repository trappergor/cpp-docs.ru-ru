---
title: Глобальные функции безопасности
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
ms.openlocfilehash: 682d44aa80f5d6de521223dfd67db2813cb6738c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326035"
---
# <a name="security-global-functions"></a>Глобальные функции безопасности

Эти функции обеспечивают поддержку для изменения объектов SID и ACL.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlGetDacl](#atlgetdacl)|Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.|
|[AtlSetDacl](#atlsetdacl)|Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.|
|[AtlGetGroupSid](#atlgetgroupsid)|Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.|
|[AtlSetGroupSid](#atlsetgroupsid)|Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.|
|[AtlGetOwnerSid](#atlgetownersid)|Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.|
|[AtlSetOwnerSid](#atlsetownersid)|Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.|
|[AtlGetSacl](#atlgetsacl)|Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.|
|[AtlSetSacl](#atlsetsacl)|Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a>AtlGetDacl

Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Обработка к объекту, для которого для получения информации о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*pDacl*<br/>
Указатель на объект DACL, который будет содержать полученную информацию о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

В отладке сборки произойдет ошибка утверждения, если *hObject* или *pDacl* недействительны.

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a>AtlSetDacl

Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка к объекту, для которого установить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*rDacl*<br/>
DACL, содержащий новую информацию о безопасности.

*dwInheritanceFlowControl*<br/>
Контроль потока наследования. Это значение может быть 0 (по умолчанию), PROTECTED_DACL_SECURITY_INFORMATION или UNPROTECTED_DACL_SECURITY_INFORMATION.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

В отладке сборки ошибка утверждения возникает, если *hObject* является недействительным, или если *dwInheritanceFlowControl* не является одним из трех разрешенных значений.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a>AtlGetGroupSid

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Обработка к объекту, с которого можно получить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*Psid*<br/>
Указатель на `CSid` объект, который будет содержать новую информацию о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a>AtlSetGroupSid

Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка к объекту, для которого установить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*Rsid*<br/>
Объект, `CSid` содержащий новую информацию о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a>AtlgetOwnerSid

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Обработка к объекту, с которого можно получить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*Psid*<br/>
Указатель на `CSid` объект, который будет содержать новую информацию о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a>AtlSetOwnerSid

Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка к объекту, для которого установить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*Rsid*<br/>
Объект, `CSid` содержащий новую информацию о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a>AtlGetSacl

Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Обработка к объекту, с которого можно получить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*pSacl*<br/>
Указатель на объект SACL, который будет содержать полученную информацию о безопасности.

*bRequestNEEDEDПривилегии*<br/>
Если это так, функция будет пытаться включить SE_SECURITY_NAME привилегию, и восстановить его по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Если `AtlGetSacl` вызвать много раз на разных объектах, то будет более эффективным включить SE_SECURITY_NAME привилегию один раз, прежде чем позвонить функции, с *bRequestNeededPrivileges* установлен на ложные.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a>AtlSetSacl

Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Ручка к объекту, для которого установить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *hObject.*

*rSacl*<br/>
SACL, содержащий новую информацию о безопасности.

*dwInheritanceFlowControl*<br/>
Контроль потока наследования. Это значение может быть 0 (по умолчанию), PROTECTED_SACL_SECURITY_INFORMATION или UNPROTECTED_SACL_SECURITY_INFORMATION.

*bRequestNEEDEDПривилегии*<br/>
Если это так, функция будет пытаться включить SE_SECURITY_NAME привилегию, и восстановить его по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

В отладке сборки ошибка утверждения возникает, если *hObject* является недействительным, или если *dwInheritanceFlowControl* не является одним из трех разрешенных значений.

Если `AtlSetSacl` вызвать много раз на разных объектах, то будет более эффективным включить SE_SECURITY_NAME привилегию один раз, прежде чем позвонить функции, с *bRequestNeededPrivileges* установлен на ложные.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>AtlGetSecurityДескриптор

Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*pszObjectName*<br/>
Указатель на нулевую строку, определяющую имя объекта, из которого можно получить информацию о безопасности.

*Objecttype*<br/>
Определяет значение из [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type) перечисления, которое указывает тип объекта, идентифицированного параметром *pszObjectName.*

*pSecurityДескриптор*<br/>
Объект, который получает запрошенный дескриптор безопасности.

*запрошенныйInfo*<br/>
Набор [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) битом флагов, которые указывают тип информации о безопасности для извлечения. Этот параметр может быть комбинацией следующих значений.

*bRequestNEEDEDПривилегии*<br/>
Если это так, функция будет пытаться включить SE_SECURITY_NAME привилегию, и восстановить его по завершении.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Remarks

Если `AtlGetSecurityDescriptor` вызвать много раз на разных объектах, то будет более эффективным включить SE_SECURITY_NAME привилегию один раз, прежде чем позвонить функции, с *bRequestNeededPrivileges* установлен на ложные.

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
