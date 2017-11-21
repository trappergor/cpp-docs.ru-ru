---
title: "Класс CDacl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs: C++
helpviewer_keywords: CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f45a4fc1d69cf0caefb08a7a408ecc836d092851
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdacl-class"></a>Класс CDacl
Этот класс является оболочкой для структуры DACL (список управления доступом).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CDacl : public CAcl
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDacl::CDacl](#cdacl)|Конструктор.|  
|[CDacl:: ~ CDacl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDacl::AddAllowedAce](#addallowedace)|Добавляет допустимое ACE (записи управления доступом) `CDacl` объекта.|  
|[CDacl::AddDeniedAce](#adddeniedace)|Добавляет запрещенного ACE для `CDacl` объекта.|  
|[CDacl::GetAceCount](#getacecount)|Возвращает количество элементов управления доступом (элементы управления доступом) в `CDacl` объекта.|  
|[CDacl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CDacl` объекта.|  
|[CDacl::RemoveAllAces](#removeallaces)|Удаляет все элементы управления доступом, содержащиеся в `CDacl` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDacl::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 Дескриптор безопасности объекта может содержать список DACL. Список DACL содержит ноль или более элементов управления доступом (элементы управления доступом), определяющие пользователями и группами, можно получить доступ к объекту. Если список DACL пуст (то есть, он содержит нулевые элементы управления доступом), нет явного доступа, поэтому неявно отказано в доступе. Если список DACL не имеет дескриптора безопасности объекта, объект не защищен, и у всех есть полный доступ.  
  
 Чтобы получить список DACL объекта, необходимо быть владельцем объекта или иметь READ_CONTROL доступ к объекту. Чтобы изменить список DACL объекта, необходимо иметь WRITE_DAC доступ к объекту.  
  
 Используйте методы класса, предоставленные для создания, добавлять, удалять и удалить элементы управления доступом из `CDacl` объекта. См. также [AtlGetDacl](security-global-functions.md#atlgetdacl) и [AtlSetDacl](security-global-functions.md#atlsetdacl).  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="addallowedace"></a>CDacl::AddAllowedAce  
 Добавляет допустимое ACE (записи управления доступом) `CDacl` объекта.  
  
```
bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 Объект [CSid](../../atl/reference/csid-class.md) объекта.  
  
 `AccessMask`  
 Указывает маску прав доступа, чтобы разрешить для указанного `CSid` объекта.  
  
 `AceFlags`  
 Набор битовых флагов, которые управляют ACE наследования.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении ACE `CDacl` объекта, **false** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Объект `CDacl` объект содержит ноль или более элементов управления доступом (элементы управления доступом), определяющие пользователями и группами, можно получить доступ к объекту. Этот метод добавляет записи управления ДОСТУПОМ, который предоставляет доступ к `CDacl` объекта.  
  
> [!NOTE]
>  Во второй форме `AddAllowedAce` только будет доступен в Windows 2000 и более поздних версий.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно задать в `AceFlags` параметра.  
  
##  <a name="adddeniedace"></a>CDacl::AddDeniedAce  
 Добавляет запрещенного ACE (записи управления доступом) `CDacl` объекта.  
  
```
bool AddDeniedAce(  
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 Объект `CSid`.  
  
 `AccessMask`  
 Указывает маску прав запрещается для указанного `CSid` объекта.  
  
 `AceFlags`  
 Набор битовых флагов, которые управляют ACE наследования. По умолчанию равно 0, в первой форме метода.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении ACE `CDacl` объекта, **false** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Объект `CDacl` объект содержит ноль или более элементов управления доступом (элементы управления доступом), определяющие пользователями и группами, можно получить доступ к объекту. Этот метод добавляет записи управления ДОСТУПОМ, который запрещает доступ к `CDacl` объекта.  
  
> [!NOTE]
>  Во второй форме `AddDeniedAce` только будет доступен в Windows 2000 и более поздних версий.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно задать в `AceFlags` параметра.  
  
##  <a name="cdacl"></a>CDacl::CDacl  
 Конструктор.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий **ACL** структуры (список управления доступом).  
  
### <a name="remarks"></a>Примечания  
 `CDacl` Можно при необходимости создать объект с помощью существующей **ACL** структуры. Важно отметить, что только список DACL (список управления доступом), а не системного списка управления ДОСТУПОМ (список управления доступом системы), следует передать в качестве этого параметра. В отладочных построениях передача SACL вызывает ASSERT. В сборках выпуска передача SACL вызывает в ACL, чтобы игнорировать элементы управления доступом (элементы управления доступом) и ошибка не возникнет.  
  
##  <a name="dtor"></a>CDacl:: ~ CDacl  
 Деструктор  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все элементы управления доступом (элементы управления доступом) с помощью [CDacl::RemoveAllAces](#removeallaces).  
  
##  <a name="getacecount"></a>CDacl::GetAceCount  
 Возвращает количество элементов управления доступом (элементы управления доступом) в `CDacl` объекта.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов управления доступом, содержащиеся в `CDacl` объекта.  
  
##  <a name="operator_eq"></a>CDacl::operator =  
 Оператор присвоения.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 ACL (список управления доступом) для назначения для существующего объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CDacl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо обеспечить только передать DACL (список управления доступом) для этой функции. Передача SACL (системный список управления доступом) для этой функции приведет к ASSERT в отладочных построениях, но вызовет ошибки не в сборке выпуска.  
  
##  <a name="removeace"></a>CDacl::RemoveAce  
 Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CDacl` объекта.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACE для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>CDacl::RemoveAllAces  
 Удаляет все элементы управления доступом (элементы управления доступом) содержится в `CDacl` объекта.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет каждый **ACE** структуры (записи управления доступом) (если таковые имеются) в `CDacl` объекта.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [Класс CAcl](../../atl/reference/cacl-class.md)   
 [Списки управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Элементы управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
