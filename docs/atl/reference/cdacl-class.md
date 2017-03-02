---
title: "Класс CDacl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDacl
- CDacl
- ATL.CDacl
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
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
ms.openlocfilehash: bb418919c26e3c0054a151b859cdf3f31c5d73a8
ms.lasthandoff: 02/24/2017

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
 Дескриптор безопасности объекта может содержать список DACL. Список DACL содержит ноль или более элементов управления доступом (элементы управления доступом), определяющих пользователей и групп, которым разрешен доступ к объекту. Если список DACL пуста (то есть, он содержит нулевые элементы ACE), нет явного доступа, поэтому неявно отказано в доступе. Если дескриптора безопасности объекта нет списка DACL, объект не защищен, и у всех есть полный доступ.  
  
 Чтобы получить список DACL объекта, необходимо быть владельцем объекта или иметь READ_CONTROL доступ к объекту. Чтобы изменить список DACL объекта, необходимо иметь доступ WRITE_DAC к объекту.  
  
 Используйте методы класса для создания, добавлять, удалять и удалять записи ACE из `CDacl` объекта. См. также [AtlGetDacl](http://msdn.microsoft.com/library/a0973648-0d46-4c1a-914f-bda861fe5d19) и [AtlSetDacl](http://msdn.microsoft.com/library/eb88ccb6-1f1b-444d-b0c9-8d5cd0dd6c0b).  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="a-nameaddallowedacea--cdacladdallowedace"></a><a name="addallowedace"></a>CDacl::AddAllowedAce  
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
 Задает маску прав доступа, чтобы разрешить для указанного `CSid` объекта.  
  
 `AceFlags`  
 Набор битовые флаги, определяющие наследование ACE.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении записи ACE `CDacl` объекта, **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Объект `CDacl` содержит ноль или более элементов управления доступом (элементы управления доступом), определяющих пользователей и групп, которым разрешен доступ к объекту. Этот метод добавляет запись ACE, которая предоставляет доступ к `CDacl` объекта.  
  
> [!NOTE]
>  Вторая форма `AddAllowedAce` — только на Windows 2000 и более поздних версий.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно установить в `AceFlags` параметр.  
  
##  <a name="a-nameadddeniedacea--cdacladddeniedace"></a><a name="adddeniedace"></a>CDacl::AddDeniedAce  
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
 Задает маску прав запрещается для указанного `CSid` объекта.  
  
 `AceFlags`  
 Набор битовые флаги, определяющие наследование ACE. По умолчанию равно 0, в первой форме метода.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении записи ACE `CDacl` объекта, **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Объект `CDacl` содержит ноль или более элементов управления доступом (элементы управления доступом), определяющих пользователей и групп, которым разрешен доступ к объекту. Этот метод добавляет запись ACE, которая запрещает доступ к `CDacl` объекта.  
  
> [!NOTE]
>  Вторая форма `AddDeniedAce` — только на Windows 2000 и более поздних версий.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно установить в `AceFlags` параметр.  
  
##  <a name="a-namecdacla--cdaclcdacl"></a><a name="cdacl"></a>CDacl::CDacl  
 Конструктор.  
  
```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий **ACL** структуры (список управления доступом).  
  
### <a name="remarks"></a>Примечания  
 `CDacl` Объект может быть также создан с помощью существующего **ACL** структуры. Важно отметить, что только список DACL (список управления доступом), а не системный список управления ДОСТУПОМ (список управления доступом системы), следует передать в качестве этого параметра. В отладочных построениях передача SACL вызывает метод ASSERT. В сборке выпуска передачи SACL вызовет записи ACE (элементы управления доступом) в ACL игнорируются, и ошибок не происходит.  
  
##  <a name="a-namedtora--cdaclcdacl"></a><a name="dtor"></a>CDacl:: ~ CDacl  
 Деструктор  
  
```
~CDacl () throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все элементы управления доступом (элементы управления доступом) с помощью [CDacl::RemoveAllAces](#removeallaces).  
  
##  <a name="a-namegetacecounta--cdaclgetacecount"></a><a name="getacecount"></a>CDacl::GetAceCount  
 Возвращает количество элементов управления доступом (элементы управления доступом) в `CDacl` объекта.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов управления доступом, содержащиеся в `CDacl` объекта.  
  
##  <a name="a-nameoperatoreqa--cdacloperator-"></a><a name="operator_eq"></a>CDacl::operator =  
 Оператор присвоения.  
  
```
CDacl& operator= (const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Список управления Доступом (access control list) назначить существующий объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CDacl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо обеспечить передать DACL (список управления доступом) только для этой функции. Передача SACL (системный список управления доступом) Эта функция вызовет УТВЕРЖДЕНИЕ в отладочных построениях, но вызовет без ошибок в сборке выпуска.  
  
##  <a name="a-nameremoveacea--cdaclremoveace"></a><a name="removeace"></a>CDacl::RemoveAce  
 Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CDacl` объекта.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACE для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="a-nameremoveallacesa--cdaclremoveallaces"></a><a name="removeallaces"></a>CDacl::RemoveAllAces  
 Удаляет все элементы ACE (элементы управления доступом), содержащихся в `CDacl` объекта.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет каждый **ACE** (записи управления доступом) структуры (если таковые имеются) в `CDacl` объекта.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [Класс CAcl](../../atl/reference/cacl-class.md)   
 [Списки управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Элементы управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)

