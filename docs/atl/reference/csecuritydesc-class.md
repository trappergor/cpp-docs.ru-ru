---
title: "Класс CSecurityDesc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
dev_langs: C++
helpviewer_keywords: CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b199565221173d7664600f2869e079c2f1c95aae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="csecuritydesc-class"></a>Класс CSecurityDesc
Этот класс является оболочкой для **SECURITY_DESCRIPTOR** структуры.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Конструктор.|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|Преобразует формат строки дескриптора безопасности в дескриптор безопасности допустимый, режим работы.|  
|[CSecurityDesc::GetControl](#getcontrol)|Извлекает задать сведения из дескриптора безопасности.|  
|[CSecurityDesc::GetDacl](#getdacl)|Извлекает сведения о списке (DACL) для управления доступом из дескриптора безопасности.|  
|[CSecurityDesc::GetGroup](#getgroup)|Получает основную группу сведения из дескриптора безопасности.|  
|[CSecurityDesc::GetOwner](#getowner)|Извлекает владельца informaton из дескриптора безопасности.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Возвращает указатель на **SECURITY_DESCRIPTOR** структуры.|  
|[CSecurityDesc::GetSacl](#getsacl)|Извлекает сведения о системе управления доступом список управления ДОСТУПОМ из дескриптора безопасности.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Определяет, если список DACL настроена для поддержки автоматического распространения.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Определяет, настроена ли дескриптор безопасности по умолчанию DACL.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Определяет, если дескриптор безопасности содержит список DACL.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Определяет, если список DACL настроен для предотвращения изменений.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Определяет, если идентификатор безопасности группы дескриптора безопасности (SID) был установлен по умолчанию.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Определяет, если владельцем дескриптора безопасности SID был установлен по умолчанию.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Определяет, если список SACL настроен для поддержки автоматического распространения.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Определяет, настроена ли дескриптор безопасности по умолчанию системного списка управления ДОСТУПОМ.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Определяет, содержит ли дескриптор безопасности системного списка управления ДОСТУПОМ.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Определяет, если список SACL настроен для предотвращения изменений.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Определяет, является ли дескриптор безопасности в относительный формат.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительный формат.|  
|[CSecurityDesc::SetControl](#setcontrol)|Устанавливает управляющие биты дескриптора безопасности.|  
|[CSecurityDesc::SetDacl](#setdacl)|Задает сведения в DACL. Если список DACL уже существует в дескрипторе безопасности, он заменяется.|  
|[CSecurityDesc::SetGroup](#setgroup)|Задает основную группу информацию абсолютном формате дескриптора безопасности, заменяя любые основную группу данные уже присутствует.|  
|[CSecurityDesc::SetOwner](#setowner)|Задает сведения о владельце абсолютном формате дескриптора безопасности, заменив все уже имеется информация о владельце.|  
|[CSecurityDesc::SetSacl](#setsacl)|Задает сведения в SACL. Если список SACL в дескрипторе безопасности установлен, он заменяется.|  
|[CSecurityDesc::ToString](#tostring)|Преобразует формат строки дескриптора безопасности.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Возвращает указатель на **SECURITY_DESCRIPTOR** структуры.|  
|[CSecurityDesc::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 **SECURITY_DESCRIPTOR** структура содержит сведения о безопасности, связанные с объектом. Приложениям использовать эту структуру для задания и запросить состояние объекта безопасности. См. также [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor).  
  
 Приложения, которые не следует изменять **SECURITY_DESCRIPTOR** структуры напрямую, а вместо этого следует использовать предоставленные методы класса.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 Конструктор.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CSecurityDesc` Объекта или **SECURITY_DESCRIPTOR** структуры, чтобы назначить для нового `CSecurityDesc` объекта.  
  
### <a name="remarks"></a>Примечания  
 `CSecurityDesc` Можно при необходимости создать объект с помощью **SECURITY_DESCRIPTOR** структуры или ранее определенную `CSecurityDesc` объекта.  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 Деструктор  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы.  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 Преобразует формат строки дескриптора безопасности в дескриптор безопасности допустимый, режим работы.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на строку с завершающим нулем, содержащий [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570) для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true в случае успешного выполнения. Возникло исключение при сбое.  
  
### <a name="remarks"></a>Примечания  
 Строки могут быть созданы с помощью [CSecurityDesc::ToString](#tostring). Преобразование дескриптора безопасности в строку упрощает для хранения и передачи.  
  
 Этот метод доступен только в Windows 2000 и более поздних версий, так как он вызывает [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="getcontrol"></a>CSecurityDesc::GetControl  
 Извлекает задать сведения из дескриптора безопасности.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *psdc*  
 Указатель на **SECURITY_DESCRIPTOR_CONTROL** структуру, которая получает сведения о дескрипторе безопасности элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является только значимые при работе с Windows 2000 или более поздней версии, он вызывает [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 Извлекает сведения о списке (DACL) для управления доступом из дескриптора безопасности.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pDacl`  
 Указатель на `CDacl` структуры, в которой для хранения копии списка DACL дескриптора безопасности. Если избирательные **ACL** существует метода задает `pDacl` адрес безопасности дескриптор избирательные **ACL**. Если избирательные **ACL** не существует, отсутствует значение.  
  
 `pbPresent`  
 Указатель на значение, указывающее наличие избирательные **ACL** в дескрипторе безопасности. Если дескриптор безопасности содержит избирательные **ACL**, этот параметр установлен в значение true. Если дескриптор безопасности не содержит избирательные **ACL**, этот параметр имеет значение false.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_DACL_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры, если избирательные **ACL** существует для дескриптора безопасности. Если этот флаг имеет значение true, избирательные **ACL** был извлечен с помощью механизма по умолчанию; Если значение равно false, избирательные **ACL** было явно указано пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 Получает основную группу сведения из дескриптора безопасности.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатором безопасности), который получает копию группы, хранящиеся в CDacl.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_GROUP_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при возврате метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 Извлекает владельца informaton из дескриптора безопасности.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатором безопасности), который получает копию группы, хранящиеся в CDacl.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_OWNER_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при возврате метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.  
  
##  <a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 Возвращает указатель на **SECURITY_DESCRIPTOR** структуры.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) структуры.  
  
##  <a name="getsacl"></a>CSecurityDesc::GetSacl  
 Извлекает сведения о системе управления доступом список управления ДОСТУПОМ из дескриптора безопасности.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSacl`  
 Указатель на `CSacl` структуры, в которой необходимо сохранить копию списка SACL в дескрипторе безопасности. При использовании системного **ACL** существует метода задает `pSacl` адрес дескриптора безопасности системы **ACL**. При использовании системного **ACL** не существует, отсутствует значение.  
  
 `pbPresent`  
 Указатель на метод устанавливает для обозначения присутствия системы флаг **ACL** в дескрипторе безопасности. Если дескриптор безопасности содержит систему **ACL**, этот параметр установлен в значение true. Если дескриптор безопасности содержит системы **ACL**, этот параметр имеет значение false.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_SACL_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при использовании системного **ACL** существует для дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае неудачи.  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 Определяет, если список управления доступом (DACL) настроена для поддержки автоматического распространения.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит список DACL, который настроен для поддержки автоматическое распространение наследуемых управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Система устанавливает этот бит, при выполнении алгоритм автоматического наследования для объекта и его имеющиеся дочерние объекты.  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Определяет, настроена ли дескриптор безопасности по умолчанию список управления доступом (DACL).  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию DACL, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг может повлиять на способ система обрабатывает DACL говоря о наследовании запись (ACE) для управления доступом. Например если создатель объекта не указан список DACL, объект получает значение по умолчанию DACL создателя маркер доступа. Система не обрабатывает этот флаг, если не установлен флаг SE_DACL_PRESENT.  
  
 Этот флаг используется для определения, как вычислить окончательный список DACL на объекте и физически не хранящийся в элементе управления дескриптор безопасности защищаемого объекта.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Определяет, если дескриптор безопасности содержит список управления доступом (DACL).  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит список DACL, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если этот флаг не установлен, или если этот флаг установлен, а DACL равен NULL, дескриптор безопасности разрешает полный доступ ко всем пользователям.  
  
 Этот флаг используется для хранения сведений о безопасности, указанный вызывающим объектом, пока дескриптора безопасности не связана с защищаемого объекта. После дескриптор безопасности связан с защищаемого объекта, флаг SE_DACL_PRESENT всегда устанавливается в элементе управления дескриптор безопасности.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 Определяет, если список управления доступом (DACL) настроен для предотвращения изменений.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если список DACL настроен для предотвращения дескриптора безопасности от изменения наследуемые управления доступом (ACE). В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
 Этот метод применяется только для Windows 2000 или более поздней версии, как автоматическое распространение наследуемых ACE поддерживает только Windows 2000.  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Определяет, если идентификатор безопасности группы дескриптора безопасности (SID) был установлен по умолчанию.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true если механизм по умолчанию, а не исходной поставщика дескриптора безопасности, предоставленный дескриптор безопасности SID группы. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetGroup](#setgroup) метод.  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Определяет, если идентификатора безопасности (SID) владельца дескриптора безопасности был установлен по умолчанию.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если владельцем дескриптора безопасности SID механизма по умолчанию, а не исходной поставщика дескриптора безопасности. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetOwner](#setowner) метод.  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Определяет, если системного списка управления доступом (SACL) настроена для поддержки автоматического распространения.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит системного списка управления ДОСТУПОМ, который настроен для поддержки автоматическое распространение наследуемых управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Система устанавливает этот бит, при выполнении алгоритм автоматического наследования для объекта и его имеющиеся дочерние объекты.  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Определяет, настроена ли дескриптор безопасности по умолчанию системный список управления доступом (SACL).  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию системного списка управления ДОСТУПОМ, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг может повлиять на способ система обрабатывает SACL, говоря о наследовании запись (ACE) для управления доступом. Система не обрабатывает этот флаг, если не установлен флаг SE_SACL_PRESENT.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Определяет, содержит ли дескриптор безопасности системный список управления доступом (SACL).  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит системного списка управления ДОСТУПОМ, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Определяет, если в целях предотвращения изменений настроена системного списка управления доступом (SACL).  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если список SACL настроен для предотвращения дескриптора безопасности от изменения наследуемые управления доступом (ACE). В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
 Этот метод применяется только для Windows 2000 или более поздней версии, как автоматическое распространение наследуемых ACE поддерживает только Windows 2000.  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Определяет, является ли дескриптор безопасности в относительный формат.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности в относительном формате со всеми данными безопасности в непрерывный блок памяти. Возвращает значение false, если дескриптор безопасности в абсолютном формате. Дополнительные сведения см. в разделе [Absolute и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности в абсолютном формате содержит ссылки на сведения о нем, а не сами сведения. Дескриптор безопасности в относительном формате сведения в непрерывный блок памяти. В дескрипторе безопасности относительный **SECURITY_DESCRIPTOR** структуры всегда начинается сведения, но дескриптор безопасности и другие компоненты могут иметь структуру, в любом порядке. Вместо адреса памяти, компоненты дескриптора безопасности в относительный идентифицируются смещения от начала дескриптор безопасности. Этот формат удобно в тех случаях, когда дескриптор безопасности должна хранящихся на диске или передаются с помощью протокола связи. Дополнительные сведения см. в разделе [Absolute и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительный формат.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности в абсолютном формате содержит указатели на данные, содержащиеся в нем, а не содержащий сами сведения. Дескриптор безопасности в относительном формате сведения в непрерывный блок памяти. В дескрипторе безопасности относительный **SECURITY_DESCRIPTOR** структуры всегда начинается сведения, но дескриптор безопасности и другие компоненты могут иметь структуру, в любом порядке. Компоненты дескриптора безопасности вместо адреса памяти, идентифицируются смещения от начала дескриптор безопасности. Этот формат удобно в тех случаях, когда дескриптор безопасности должна хранящихся на диске или передаются с помощью протокола связи. Дополнительные сведения см. в разделе [Absolute и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="operator_eq"></a>CSecurityDesc::operator =  
 Оператор присвоения.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 **SECURITY_DESCRIPTOR** структуры или `CSecurityDesc` объект для назначения `CSecurityDesc` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CSecurityDesc` объекта.  
  
##  <a name="operator_const_security_descriptor__star"></a>CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 Приводит значение к указателю на **SECURITY_DESCRIPTOR** структуры.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>CSecurityDesc::SetControl  
 Устанавливает управляющие биты дескриптора безопасности.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ControlBitsOfInterest`  
 Объект **SECURITY_DESCRIPTOR_CONTROL** маску, которая указывает управляющие биты. Список флагов, которые можно задать, в разделе [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSet`  
 Маска `SECURITY_DESCRIPTOR_CONTROL`, которая указывает новые значения управляющих битов, заданных маской `ControlBitsOfInterest`. Этот параметр может быть сочетанием флагов, перечисленных для параметра `ControlBitsOfInterest`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод доступен только в Windows 2000 и более поздних версий, поскольку он задает [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="setdacl"></a>CSecurityDesc::SetDacl  
 Задает сведения в списке управления доступом (DACL). Если список DACL уже существует в дескрипторе безопасности, он заменяется.  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *Список DACL*  
 Ссылка на `CDacl` объект, указывающий DACL дескриптора безопасности. Этот параметр не должен иметь значение NULL. Чтобы задать НУЛЕВОЙ DACL в дескрипторе безопасности, следует использовать первую форму метода с `bPresent` значение false.  
  
 `bPresent`  
 Задает флаг, указывающий на наличие DACL в дескрипторе безопасности. Если этот параметр имеет значение true, метод устанавливает флаг SE_DACL_PRESENT **SECURITY_DESCRIPTOR_CONTROL** структуры и использует значения в *Dacl* и `bDefaulted` параметров. Если он имеет значение false, метод очищает флаг SE_DACL_PRESENT и `bDefaulted` учитывается.  
  
 `bDefaulted`  
 Задает флаг, указывающий источник DACL. Если этот флаг имеет значение true, список DACL получено какого-либо механизма по умолчанию. Если значение равно false, список DACL был явно задан пользователем. Метод сохраняет его в флаг SE_DACL_DEFAULTED **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр не указан, снят флаг SE_DACL_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Имеется существенное различие между пустой и несуществующей DACL. Если список DACL пуст, он содержит нет записей управления доступом и явным образом предоставлен нет прав доступа. В результате неявно запрещается доступ к объекту. Если у объекта имеется списки DACL, с другой стороны, без защиты, назначенные объекту, и запрос на доступ предоставляется.  
  
##  <a name="setgroup"></a>CSecurityDesc::SetGroup  
 Задает основную группу информацию абсолютном формате дескриптора безопасности, заменяя любые основную группу данные уже присутствует.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `Sid`  
 Ссылка на [CSid](../../atl/reference/csid-class.md) объекта для новой группы основной дескриптор безопасности. Этот параметр не должен иметь значение NULL. Дескриптор безопасности может быть помечен как не имеющий DACL и SACL, но он должен иметь группу и владельца, даже они имеют значение NULL, ИД безопасности (который является встроенной SID со специальным значением).  
  
 `bDefaulted`  
 Указывает ли основная группа сведений является производным от механизма по умолчанию. Если это значение равно true, сведения по умолчанию и метод сохраняет его как флаг SE_GROUP_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр равен нулю, снят флаг SE_GROUP_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="setowner"></a>CSecurityDesc::SetOwner  
 Задает сведения о владельце абсолютном формате дескриптора безопасности. Он заменяет любые сведения о владельце уже существует.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `Sid`  
 [CSid](../../atl/reference/csid-class.md) объекта для нового основного владельца дескриптора безопасности. Этот параметр не должен иметь значение NULL.  
  
 `bDefaulted`  
 Указывает, является ли информация о владельце производным от механизма по умолчанию. Если это значение равно true, это сведения по умолчанию. Метод сохраняет его как флаг SE_OWNER_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр равен нулю, снят флаг SE_OWNER_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="setsacl"></a>CSecurityDesc::SetSacl  
 Задает сведения в системный список управления доступом (SACL). Если список SACL в дескрипторе безопасности установлен, он заменяется.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *Системный список управления доступом*  
 Указатель на `CSacl` объект, указывающий системного списка управления ДОСТУПОМ для дескриптора безопасности. Этот параметр не должен иметь значение NULL и должен быть объектом CSacl. В отличие от DACL нет никаких различий между NULL и пустые системного списка управления ДОСТУПОМ, как объекты SACL определяют права доступа, только аудит сведения.  
  
 `bDefaulted`  
 Задает флаг, указывающий источник списка SACL. Если этот флаг имеет значение true, список SACL получено какого-либо механизма по умолчанию. Если значение равно false, список SACL был явно задан пользователем. Метод сохраняет его в флаг SE_SACL_DEFAULTED **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр не указан, снят флаг SE_SACL_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 Преобразует формат строки дескриптора безопасности.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на строку символом null, который будет получать [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Задает сочетание битовых флагов SECURITY_INFORMATION, чтобы указать компоненты для включения в выходной строке дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 После формат строки дескриптора безопасности, его можно легко хранить или передачи. Используйте `CSecurityDesc::FromString` метод для преобразования строки в дескриптор безопасности.  
  
 `si` Параметр может содержать следующие флаги SECURITY_INFORMATION:  
  
|Значение|Значение|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Включить владельца.|  
|GROUP_SECURITY_INFORMATION|Включить основную группу.|  
|DACL_SECURITY_INFORMATION|Включить список DACL.|  
|SACL_SECURITY_INFORMATION|Включить список SACL.|  
  
 Если список DACL имеет значение NULL и SE_DACL_PRESENT управления бита в дескрипторе безопасности ввода, произойдет ошибка.  
  
 Если список DACL имеет значение NULL, и бит управления SE_DACL_PRESENT не установлен в дескрипторе безопасности ввода, результирующие строки дескриптора безопасности не установлен компонент D:. В разделе [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570) для получения дополнительных сведений.  
  
 Этот метод доступен только в Windows 2000 и более поздней версии, как он вызывает [ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
