---
title: "Глобальные функции безопасности | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ff5afaaf2746d9e07eb9e06a079d34adb2f67109
ms.lasthandoff: 04/04/2017

---
# <a name="security-global-functions"></a>Глобальные функции безопасности
Эти функции предоставляют поддержку для изменения ИД безопасности и ACL объекта.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlgetdacl"></a>AtlGetDacl  
 Вызывайте эту функцию для получения данных списка управления доступом на уровне пользователя (DACL) указанного объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
  
##  <a name="atlsetdacl"></a>AtlSetDacl  
 Вызывайте эту функцию для задания данных списка управления доступом на уровне пользователя (DACL) указанного объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlgetgroupsid"></a>AtlGetGroupSid  
 Вызывайте эту функцию для извлечения идентификатора безопасности (SID) группы для объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlsetgroupsid"></a>AtlSetGroupSid  
 Вызывайте эту функцию для задания идентификатора безопасности (SID) группы для объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlgetownersid"></a>AtlGetOwnerSid  
 Вызывайте эту функцию для извлечения идентификатора безопасности (SID) владельца для объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlsetownersid"></a>AtlSetOwnerSid  
 Вызывайте эту функцию для задания идентификатора безопасности (SID) владельца для объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlgetsacl"></a>AtlGetSacl  
 Вызывайте эту функцию для получения данных системного списка управления доступом (SACL) указанного объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlsetsacl"></a>AtlSetSacl  
 Вызывайте эту функцию для задания данных системного списка управления доступом (SACL) указанного объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

##  <a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor  
 Вызывайте эту функцию для извлечения дескриптора безопасности заданного объекта.  
  
> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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

