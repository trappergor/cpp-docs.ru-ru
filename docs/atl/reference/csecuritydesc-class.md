---
title: "Класс CSecurityDesc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6dbd586ee3ee07d3c567fa0aae46446397dfb62b
ms.lasthandoff: 02/24/2017

---
# <a name="csecuritydesc-class"></a>Класс CSecurityDesc
Этот класс является оболочкой для **SECURITY_DESCRIPTOR** структуры.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Конструктор.|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|Преобразует формат строки дескриптора безопасности в дескриптор допустимый, режим безопасности.|  
|[CSecurityDesc::GetControl](#getcontrol)|Получает управление, сведения из дескриптора безопасности.|  
|[CSecurityDesc::GetDacl](#getdacl)|Извлекает сведения управления доступом (DACL) список из дескриптора безопасности.|  
|[CSecurityDesc::GetGroup](#getgroup)|Извлекает сведения основной группы из дескриптора безопасности.|  
|[CSecurityDesc::GetOwner](#getowner)|Возвращает владельца информацию из дескриптора безопасности.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Возвращает указатель на **SECURITY_DESCRIPTOR** структуры.|  
|[CSecurityDesc::GetSacl](#getsacl)|Извлекает сведения о системе управления доступом список управления ДОСТУПОМ из дескриптора безопасности.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Определяет, если список DACL настроен для поддержки автоматического распространения.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Определяет, если значение по умолчанию DACL настроен дескриптор безопасности.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Определяет, если дескриптор безопасности содержит список DACL.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Определяет, если список DACL настроен для предотвращения изменений.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Определяет, если дескриптор безопасности группы идентификатор безопасности (SID) был установлен по умолчанию.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Определяет, если владельцем дескриптора безопасности SID был установлен по умолчанию.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Определяет, если список SACL настроен для поддержки автоматического распространения.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Определяет, если дескриптор безопасности настроен по умолчанию SACL.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Определяет, содержит ли дескриптор безопасности SACL.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Определяет, если список SACL настроен для предотвращения изменений.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Определяет, является ли дескриптор безопасности в относительном формате.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительном формате.|  
|[CSecurityDesc::SetControl](#setcontrol)|Устанавливает управляющие биты дескриптора безопасности.|  
|[CSecurityDesc::SetDacl](#setdacl)|Задает сведения в списке DACL. Если список DACL уже присутствует в дескрипторе безопасности, он заменяется.|  
|[CSecurityDesc::SetGroup](#setgroup)|Задает сведения о основной группы абсолютный формат дескриптора безопасности, заменив данные основной группы уже существует.|  
|[CSecurityDesc::SetOwner](#setowner)|Задает сведения о владельце абсолютный формат дескриптора безопасности, заменив все уже присутствует информация о владельце.|  
|[CSecurityDesc::SetSacl](#setsacl)|Задает сведения в SACL. Если присутствует SACL в дескрипторе безопасности, он заменяется.|  
|[CSecurityDesc::ToString](#tostring)|Преобразует дескриптор безопасности в строковом формате.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|Возвращает указатель на **SECURITY_DESCRIPTOR** структуры.|  
|[CSecurityDesc::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 **SECURITY_DESCRIPTOR** структура содержит сведения о безопасности, связанные с объектом. Приложения используют эту структуру для установки и запроса состояния объекта безопасности. См. также [AtlGetSecurityDescriptor](http://msdn.microsoft.com/library/233578b8-dcc5-4f51-8e62-7cdcc2ff6b11).  
  
 Не следует изменять приложения **SECURITY_DESCRIPTOR** структуры непосредственно, а вместо этого следует использовать предоставленные методы класса.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 `CSecurityDesc` Объекта при необходимости могут создаваться с помощью **SECURITY_DESCRIPTOR** структуры или ранее определенный `CSecurityDesc` объекта.  
  
##  <a name="dtor"></a>CSecurityDesc:: ~ CSecurityDesc  
 Деструктор  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы.  
  
##  <a name="fromstring"></a>CSecurityDesc::FromString  
 Преобразует формат строки дескриптора безопасности в дескриптор допустимый, режим безопасности.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель на нулем строка, содержащая [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570) для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true в случае успешного выполнения. Возникло исключение при сбое.  
  
### <a name="remarks"></a>Примечания  
 Строки могут быть созданы с помощью [CSecurityDesc::ToString](#tostring). Преобразование строки дескриптора безопасности упрощает для хранения и передачи.  
  
 Этот метод доступен только в Windows 2000 и более поздних версий, так как он вызывает [функция ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="getcontrol"></a>CSecurityDesc::GetControl  
 Получает управление, сведения из дескриптора безопасности.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *psdc*  
 Указатель на **SECURITY_DESCRIPTOR_CONTROL** структуру, которая получает сведения о дескрипторе безопасности элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является только значимые при работе с Windows 2000 или более поздней версии, он вызывает [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="getdacl"></a>CSecurityDesc::GetDacl  
 Извлекает сведения управления доступом (DACL) список из дескриптора безопасности.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pDacl`  
 Указатель на `CDacl` структуры для хранения копии DACL дескриптор безопасности. Если избирательные **ACL** существует метода задает `pDacl` адрес безопасности дескриптор избирательные **ACL**. Если избирательные **ACL** не существует, значение не сохраняется.  
  
 `pbPresent`  
 Указатель на значение, которое указывает на присутствие избирательные **ACL** в дескрипторе безопасности. Если дескриптор безопасности содержит избирательные **ACL**, этому параметру задано значение true. Если дескриптор безопасности не содержит избирательные **ACL**, этот параметр имеет значение false.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_DACL_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры, если избирательные **ACL** существует для дескриптора безопасности. Если этот флаг имеет значение true, выбору **ACL** был получен с помощью механизма по умолчанию; Если значение равно false, выбору **ACL** явно указано пользователем.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае сбоя.  
  
##  <a name="getgroup"></a>CSecurityDesc::GetGroup  
 Извлекает сведения основной группы из дескриптора безопасности.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатор безопасности), который получает копию группы, хранящиеся в CDacl.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_GROUP_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при возврате метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае сбоя.  
  
##  <a name="getowner"></a>CSecurityDesc::GetOwner  
 Возвращает владельца информацию из дескриптора безопасности.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSid`  
 Указатель на [CSid](../../atl/reference/csid-class.md) (идентификатор безопасности), который получает копию группы, хранящиеся в CDacl.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_OWNER_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при возврате метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае сбоя.  
  
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
 Указатель на `CSacl` структуру, в которой будут храниться копия списка SACL в дескрипторе безопасности. При использовании системного **ACL** существует метода задает `pSacl` адрес дескриптора безопасности системы **ACL**. При использовании системного **ACL** не существует, значение не сохраняется.  
  
 `pbPresent`  
 Указатель на флаг задает метод для указания наличия системы **ACL** в дескрипторе безопасности. Если дескриптор безопасности содержит систему **ACL**, этому параметру задано значение true. Если дескриптор безопасности содержит систему **ACL**, этот параметр имеет значение false.  
  
 `pbDefaulted`  
 Указатель на флаг присвоено значение флага SE_SACL_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры при использовании системного **ACL** существует для дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в случае сбоя.  
  
##  <a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 Определяет, если список управления доступом (DACL) настроен для поддержки автоматического распространения.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит список DACL, который настроен для поддержки автоматическое распространение записи наследуемые управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Система устанавливает этот бит, при выполнении алгоритм автоматического наследования для объекта и его существующих дочерних объектов.  
  
##  <a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Определяет, если настраивается дескриптор безопасности по умолчанию список управления доступом (DACL).  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию DACL, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг может повлиять на том, как система рассматривает DACL, говоря о наследовании запись (ACE) для управления доступом. Например если создатель объекта не указан список DACL, объект получает значение по умолчанию DACL создателя маркер доступа. Система не обрабатывает этот флаг, если не установлен флаг SE_DACL_PRESENT.  
  
 Этот флаг используется для определения, как вычислить окончательный список DACL на объекте и физически не хранится в элементе управления дескриптор безопасности защищаемого объекта.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
##  <a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Определяет, если дескриптор безопасности содержит список управления доступом (DACL).  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит список DACL, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если этот флаг не установлен, или если этот флаг установлен, и DACL имеет значение NULL, дескриптор безопасности полный доступ для всех пользователей.  
  
 Этот флаг используется для хранения информации о безопасности, указанный вызывающим до дескриптор безопасности связан с защищаемого объекта. После дескриптор безопасности связан с защищаемым объектом, флаг SE_DACL_PRESENT всегда задается в элементе управления дескриптор безопасности.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
##  <a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 Определяет, если список управления доступом (DACL) настроен для предотвращения изменений.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если список DACL настроен для предотвращения изменения записей наследуемые управления доступом (ACE) дескриптора безопасности. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetDacl](#setdacl) метод.  
  
 Этот метод применяется только для Windows 2000 или более поздней версии, как только система Windows 2000 поддерживает автоматическое распространение наследуемых ACE.  
  
##  <a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Определяет, если дескриптор безопасности группы идентификатор безопасности (SID) был установлен по умолчанию.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если механизм по умолчанию, а не поставщик исходного дескриптора безопасности, предоставляемые дескриптор безопасности группы SID. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetGroup](#setgroup) метод.  
  
##  <a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Определяет, если идентификатора безопасности (SID) владельца дескриптора безопасности был установлен по умолчанию.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если механизм по умолчанию, а не поставщик исходного дескриптора безопасности владельца дескриптора безопасности SID. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetOwner](#setowner) метод.  
  
##  <a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Определяет, если системный список управления доступом (SACL) настроен для поддержки автоматического распространения.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит системный список управления ДОСТУПОМ, который настроен для поддержки автоматическое распространение записи наследуемые управления доступом (ACE) для существующих дочерних объектов. В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Система устанавливает этот бит, при выполнении алгоритм автоматического наследования для объекта и его существующих дочерних объектов.  
  
##  <a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Определяет, если настраивается по умолчанию системный список управления доступом (SACL) дескриптора безопасности.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит значение по умолчанию системный список управления ДОСТУПОМ, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот флаг может повлиять на том, как система рассматривает SACL, говоря о наследовании запись (ACE) для управления доступом. Система не обрабатывает этот флаг, если не установлен флаг SE_SACL_PRESENT.  
  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
##  <a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Определяет, содержит ли дескриптор безопасности системный список управления доступом (SACL).  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности содержит системный список управления ДОСТУПОМ, и false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
##  <a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Определяет, если системный список управления доступом (SACL) настроен для предотвращения изменений.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если список SACL настроен на предотвращение дескриптор безопасности от изменения записей наследуемые управления доступом (ACE). В противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Чтобы установить этот флаг, используйте [CSecurityDesc::SetSacl](#setsacl) метод.  
  
 Этот метод применяется только для Windows 2000 или более поздней версии, как только система Windows 2000 поддерживает автоматическое распространение наследуемых ACE.  
  
##  <a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Определяет, является ли дескриптор безопасности в относительном формате.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если дескриптор безопасности в относительном формате со всеми данными безопасности в непрерывном блоке памяти. Возвращает значение false, если дескриптор безопасности в абсолютном формате. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Вызовите этот метод, чтобы преобразовать дескриптор безопасности в абсолютном формате.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности в абсолютном формате содержит ссылки на сведения о нем, а не сами сведения. Дескриптор безопасности в относительном формате сведения в непрерывном блоке памяти. В дескрипторе безопасности относительный **SECURITY_DESCRIPTOR** структуры всегда начинается информацию, но дескриптор безопасности и другие компоненты могут следовать в любом порядке. Вместо адреса памяти, компоненты дескриптор безопасности в относительный идентифицируются смещения от начала дескриптор безопасности. Этот формат удобно в тех случаях, когда дескриптор безопасности должна хранится на диске или передаются при помощи протокола связи. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Вызовите этот метод, чтобы преобразовать дескриптор безопасности в относительном формате.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если метод выполнен успешно, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности в абсолютном формате содержит указатели на данные, содержащиеся в нем, а не содержит сведения о самой. Дескриптор безопасности в относительном формате сведения в непрерывном блоке памяти. В дескрипторе безопасности относительный **SECURITY_DESCRIPTOR** структуры всегда начинается информацию, но дескриптор безопасности и другие компоненты могут следовать в любом порядке. Вместо адреса памяти, компоненты дескриптора безопасности определяются смещения от начала дескриптор безопасности. Этот формат удобно в тех случаях, когда дескриптор безопасности должна хранится на диске или передаются при помощи протокола связи. Дополнительные сведения см. в разделе [абсолютное и дескрипторы безопасности Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
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
 Объект **SECURITY_DESCRIPTOR_CONTROL** маска, которая указывает управляющие биты для установки. Список флагов, которые можно задать в разделе [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSe`t  
 Маска `SECURITY_DESCRIPTOR_CONTROL`, которая указывает новые значения управляющих битов, заданных маской `ControlBitsOfInterest`. Этот параметр может быть сочетанием флагов, перечисленных для параметра `ControlBitsOfInterest`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод доступен только в Windows 2000 и более поздних версий, поскольку он [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="setdacl"></a>CSecurityDesc::SetDacl  
 Задает сведения в список управления доступом (DACL). Если список DACL уже присутствует в дескрипторе безопасности, он заменяется.  
  
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
 Ссылка на `CDacl` указание DACL для дескриптора безопасности объекта. Этот параметр не должен иметь значение NULL. Чтобы задать НУЛЕВОЙ DACL в дескрипторе безопасности, в первой форме метод должен использоваться с `bPresent` значение false.  
  
 `bPresent`  
 Задает флаг, указывающий на наличие DACL в дескрипторе безопасности. Если этот параметр имеет значение true, метод устанавливает флаг SE_DACL_PRESENT **SECURITY_DESCRIPTOR_CONTROL** структуры и использует значения в *Dacl* и `bDefaulted` параметров. Если он имеет значение false, метод снимает флаг SE_DACL_PRESENT и `bDefaulted` учитывается.  
  
 `bDefaulted`  
 Задает флаг, указывающий источник DACL. Если этот флаг имеет значение true, DACL извлекалось некий механизм по умолчанию. Если значение равно false, DACL был явно задан пользователем. Метод сохраняет его в флаг SE_DACL_DEFAULTED **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр не указан, снят флаг SE_DACL_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Существует важное различие между пустой и несуществующей DACL. Если список DACL пуст, он содержит нет записей управления доступом и явным образом было предоставлено нет прав доступа. В результате неявно запрещен доступ к объекту. Если у него нет DACL, с другой стороны, защита не назначается объекту и предоставляется любой запрос доступа.  
  
##  <a name="setgroup"></a>CSecurityDesc::SetGroup  
 Задает сведения о основной группы абсолютный формат дескриптора безопасности, заменив данные основной группы уже существует.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `Sid`  
 Ссылка на [CSid](../../atl/reference/csid-class.md) объект для новой основной группы дескриптор безопасности. Этот параметр не должен иметь значение NULL. Дескриптор безопасности может быть помечен как не имеющий списка DACL и SACL, но оно должно иметь группу и владелец, даже они являются NULL SID (который является встроенной SID со специальным значением).  
  
 `bDefaulted`  
 Указывает ли основная группа сведений является производным от механизма по умолчанию. Если это значение равно true, сведения по умолчанию и метод сохраняет это значение как флаг SE_GROUP_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр равен нулю, снят флаг SE_GROUP_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="setowner"></a>CSecurityDesc::SetOwner  
 Задает сведения о владельце абсолютный формат дескриптора безопасности. Он заменяет любые сведения о владельце уже присутствует.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `Sid`  
 [CSid](../../atl/reference/csid-class.md) объекта для нового основного владельца дескриптора безопасности. Этот параметр не должен иметь значение NULL.  
  
 `bDefaulted`  
 Указывает, является ли информация о владельце производным от механизма по умолчанию. Если это значение равно true, это сведения по умолчанию. Метод сохраняет это значение как флаг SE_OWNER_DEFAULTED в **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр равен нулю, снят флаг SE_OWNER_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="setsacl"></a>CSecurityDesc::SetSacl  
 Задает сведения в системный список управления доступом (SACL). Если присутствует SACL в дескрипторе безопасности, он заменяется.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *Системный список управления доступом*  
 Указатель на `CSacl` указании списка SACL для дескриптора безопасности объекта. Этот параметр не должен иметь значение NULL и должен быть объектом CSacl. В отличие от списков DACL нет никакой разницы между NULL и пустые системный список управления ДОСТУПОМ, как объекты SACL определяют права доступа, только информации аудита.  
  
 `bDefaulted`  
 Задает флаг, указывающий источник списка SACL. Если этот флаг имеет значение true, SACL извлекалось некий механизм по умолчанию. Если значение равно false, SACL был явно задан пользователем. Метод сохраняет его в флаг SE_SACL_DEFAULTED **SECURITY_DESCRIPTOR_CONTROL** структуры. Если этот параметр не указан, снят флаг SE_SACL_DEFAULTED.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
##  <a name="tostring"></a>CSecurityDesc::ToString  
 Преобразует дескриптор безопасности в строковом формате.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pstr`  
 Указатель нулем строку, которая будет получать [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Сочетание битовых флагов SECURITY_INFORMATION, чтобы указать компоненты для включения в выходной строке дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Когда дескриптор безопасности в строковом формате, его можно легко сохранять или передачи. Используйте `CSecurityDesc::FromString` метод преобразует строку обратно в дескриптор безопасности.  
  
 `si` Параметр может содержать следующие флаги SECURITY_INFORMATION:  
  
|Значение|Значение|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Включить владельца.|  
|GROUP_SECURITY_INFORMATION|Включить основной группы.|  
|DACL_SECURITY_INFORMATION|Включить список DACL.|  
|SACL_SECURITY_INFORMATION|Включить список SACL.|  
  
 Если список DACL имеет значение NULL и SE_DACL_PRESENT управления бита в дескрипторе безопасности ввода, происходит сбой метода.  
  
 Если список DACL имеет значение NULL, бит управления SE_DACL_PRESENT не установлен в дескрипторе безопасности ввода результирующие строки дескриптора безопасности не установлен компонент D:. В разделе [формат строки дескриптора безопасности](http://msdn.microsoft.com/library/windows/desktop/aa379570) для получения дополнительных сведений.  
  
 Этот метод доступен только в Windows 2000 и более поздних версий, как он вызывает [функция ConvertStringSecurityDescriptorToSecurityDescriptor](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)

