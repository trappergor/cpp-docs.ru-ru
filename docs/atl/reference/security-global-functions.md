---
title: Глобальные функции безопасности | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2cdeef97b92550731b06dcb4a1d425d77f5920a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075166"
---
# <a name="security-global-functions"></a>Глобальные функции безопасности

Эти функции обеспечивают поддержку Изменение SID и список управления Доступом объектов.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

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

##  <a name="atlgetdacl"></a>  AtlGetDacl

Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, для которого требуется извлечь сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*pDacl*<br/>
Указатель на объект списка DACL, который будет содержать сведения о полученных безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если параметр *hObject* или *pDacl* является недопустимым.

##  <a name="atlsetdacl"></a>  AtlSetDacl

Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, для которого устанавливаются сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*rDacl*<br/>
Список DACL, содержащий новые сведения о безопасности.

*dwInheritanceFlowControl*<br/>
Управление потоком наследования. Это значение может быть 0 (по умолчанию), PROTECTED_DACL_SECURITY_INFORMATION или UNPROTECTED_DACL_SECURITY_INFORMATION.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если *hObject* является недопустимым, или если *dwInheritanceFlowControl* не является одним из трех разрешенных значений.
### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlgetgroupsid"></a>  AtlGetGroupSid

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, из которого требуется извлечь сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*pSid*<br/>
Указатель на `CSid` объект, который будет содержать новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlsetgroupsid"></a>  AtlSetGroupSid

Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, для которого устанавливаются сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*rSid*<br/>
`CSid` Объект, содержащий новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlgetownersid"></a>  AtlGetOwnerSid

Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, из которого требуется извлечь сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*pSid*<br/>
Указатель на `CSid` объект, который будет содержать новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlsetownersid"></a>  AtlSetOwnerSid

Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, для которого устанавливаются сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*rSid*<br/>
`CSid` Объект, содержащий новые сведения о безопасности.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlgetsacl"></a>  AtlGetSacl

Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>Параметры

*hObject*<br/>
Дескриптор объекта, из которого требуется извлечь сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*pSacl*<br/>
Указатель на объект системного списка управления ДОСТУПОМ, который будет содержать сведения о полученных безопасности.

*bRequestNeededPrivileges*<br/>
Если значение равно true, функция попытается включить привилегией SE_SECURITY_NAME — в и восстановить его после завершения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Если `AtlGetSacl` вызывается много раз на множество разных объектов, он будет более эффективной, чтобы включить привилегией SE_SECURITY_NAME — в один раз перед вызовом функции, с помощью *bRequestNeededPrivileges* значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlsetsacl"></a>  AtlSetSacl

Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

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
Дескриптор объекта, для которого устанавливаются сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *hObject* параметра.

*rSacl*<br/>
Системный список управления ДОСТУПОМ, информацией безопасности.

*dwInheritanceFlowControl*<br/>
Управление потоком наследования. Это значение может быть 0 (по умолчанию), PROTECTED_SACL_SECURITY_INFORMATION или UNPROTECTED_SACL_SECURITY_INFORMATION.

*bRequestNeededPrivileges*<br/>
Если значение равно true, функция попытается включить привилегией SE_SECURITY_NAME — в и восстановить его после завершения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если *hObject* является недопустимым, или если *dwInheritanceFlowControl* не является одним из трех разрешенных значений.

Если `AtlSetSacl` вызывается много раз на множество разных объектов, он будет более эффективной, чтобы включить привилегией SE_SECURITY_NAME — в один раз перед вызовом функции, с помощью *bRequestNeededPrivileges* значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h 

##  <a name="atlgetsecuritydescriptor"></a>  AtlGetSecurityDescriptor

Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

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
Указатель на заканчивающуюся нулем строку, указывающее имя объекта, из которого требуется извлечь сведения о безопасности.

*Тип объекта*<br/>
Указывает значение из [работать пример](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type) перечисление, указывающее тип объекта, идентифицируемое по *pszObjectName* параметра.

*pSecurityDescriptor*<br/>
Объект, который получает дескриптор запрошенного типа безопасности.

*requestedInfo*<br/>
Набор [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) битовые флаги, указывающие тип извлекаемых данных безопасности. Этот параметр может быть сочетанием следующих значений.

*bRequestNeededPrivileges*<br/>
Если значение равно true, функция попытается включить привилегией SE_SECURITY_NAME — в и восстановить его после завершения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Если `AtlGetSecurityDescriptor` вызывается много раз на множество разных объектов, он будет более эффективной, чтобы включить привилегией SE_SECURITY_NAME — в один раз перед вызовом функции, с помощью *bRequestNeededPrivileges* значение false.  

### <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
