---
title: Глобальные функции безопасности | Документы Microsoft
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
ms.openlocfilehash: ad9ad170706b72c9d236e095db0e2b6df00031ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365058"
---
# <a name="security-global-functions"></a>Глобальные функции безопасности
Эти функции предоставляют поддержку для изменения ИД безопасности и ACL объекта.  
  
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
 `hObject`  
 Дескриптор объекта, для которого требуется получить сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `pDacl`  
 Указатель на объект DACL, который будет содержать полученную информацию безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если параметр `hObject` или `pDacl` является недопустимым.  
  
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
 `hObject`  
 Дескриптор объекта, для которого устанавливаются сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `rDacl`  
 Список DACL, содержащий новые сведения о безопасности.  
  
 `dwInheritanceFlowControl`  
 Управление потоком наследования. Это значение может быть 0 (по умолчанию), PROTECTED_DACL_SECURITY_INFORMATION или UNPROTECTED_DACL_SECURITY_INFORMATION.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `hObject` является недопустимым, или если `dwInheritanceFlowControl` не является одним из трех допустимых значений.  
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
 `hObject`  
 Дескриптор объекта, из которого требуется извлечь сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `pSid`  
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
 `hObject`  
 Дескриптор объекта, для которого устанавливаются сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `rSid`  
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
 `hObject`  
 Дескриптор объекта, из которого требуется извлечь сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `pSid`  
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
 `hObject`  
 Дескриптор объекта, для которого устанавливаются сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `rSid`  
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
 `hObject`  
 Дескриптор объекта, из которого требуется извлечь сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 `pSacl`  
 Указатель на объект системного списка управления ДОСТУПОМ, который будет содержать полученную информацию безопасности.  
  
 `bRequestNeededPrivileges`  
 Если значение равно true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить его при завершении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Если `AtlGetSacl` должна быть вызвана несколько раз на множество разных объектов, он будет лучше, чтобы включить привилегию SE_SECURITY_NAME один раз перед вызовом функции, с `bRequestNeededPrivileges` значение false.  

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
 `hObject`  
 Дескриптор объекта, для которого устанавливаются сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в `hObject` параметра.  
  
 *rSacl*  
 Системный список управления ДОСТУПОМ, содержащий новые сведения о безопасности.  
  
 `dwInheritanceFlowControl`  
 Управление потоком наследования. Это значение может быть 0 (по умолчанию), PROTECTED_SACL_SECURITY_INFORMATION или UNPROTECTED_SACL_SECURITY_INFORMATION.  
  
 `bRequestNeededPrivileges`  
 Если значение равно true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить его при завершении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет ошибка утверждения, если `hObject` является недопустимым, или если `dwInheritanceFlowControl` не является одним из трех допустимых значений.  
  
 Если `AtlSetSacl` должна быть вызвана несколько раз на множество разных объектов, он будет лучше, чтобы включить привилегию SE_SECURITY_NAME один раз перед вызовом функции, с `bRequestNeededPrivileges` значение false.  

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
 *pszObjectName*  
 Указатель на строку с завершающим нулем, указывающее имя объекта, из которого требуется извлечь сведения о безопасности.  
  
 `ObjectType`  
 Указывает значение из [работать пример](http://msdn.microsoft.com/library/windows/desktop/aa379593) перечисления, указывающее тип объекта, указанного в *pszObjectName* параметра.  
  
 *pSecurityDescriptor*  
 Объект, который получает дескриптор безопасности.  
  
 *requestedInfo*  
 Набор [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) битовые флаги, указывающие тип извлекаемых данных безопасности. Этот параметр может быть сочетанием следующих значений.  
  
 `bRequestNeededPrivileges`  
 Если значение равно true, функция попытается включить привилегию SE_SECURITY_NAME и восстановить его при завершении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Если `AtlGetSecurityDescriptor` должна быть вызвана несколько раз на множество разных объектов, он будет лучше, чтобы включить привилегию SE_SECURITY_NAME один раз перед вызовом функции, с `bRequestNeededPrivileges` значение false.  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h 
   
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
