---
title: "Класс CSacl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSacl
- ATL::CSacl
- CSacl
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
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
ms.openlocfilehash: 50f10ab765648d4b587a941ccf24726b53f14c88
ms.lasthandoff: 02/24/2017

---
# <a name="csacl-class"></a>Класс CSacl
Этот класс является оболочкой для структуры SACL (системный список управления доступом).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Конструктор.|  
|[CSacl:: ~ CSacl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSacl::AddAuditAce](#addauditace)|Добавляет запись управления доступом (ACE) аудита `CSacl` объекта.|  
|[CSacl::GetAceCount](#getacecount)|Возвращает количество записей управления доступом (ACE) в `CSacl` объекта.|  
|[CSacl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) **CSacl** объекта.|  
|[CSacl::RemoveAllAces](#removeallaces)|Удаляет все элементы управления доступом, содержащиеся в `CSacl` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSacl::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 SACL содержит записи управления доступом (ACE), определяющих типы попыток доступа, формирующих записи аудита в журнале событий безопасности контроллера домена. Обратите внимание, что список SACL создает записи журнала только на контроллере домена, где произошла попытка доступа, а не на каждый контроллер домена, который содержит реплику объекта.  
  
 Чтобы задать или получить SACL в дескрипторе безопасности объекта, необходимо включить привилегией SE_SECURITY_NAME в маркере доступа запрашивающего потока. Группы «Администраторы» имеет эту привилегию, определенным параметрами по умолчанию, и могут предоставляться другим пользователям или группам. Право предоставил не требуется: до выполнения операции, определяется привилегия, привилегии должны быть включены в маркере безопасности доступа для вступили в силу. Модель позволяет правами должен быть включен только для определенной системы операций, а затем выключено, когда они больше не нужны. В разделе [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) и [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547) примеры Включение SE_SECURITY_NAME.  
  
 Используйте методы класса, позволяющих добавлять, удалять, создавать и удалять записи ACE из **SACL** объекта. См. также [AtlGetSacl](http://msdn.microsoft.com/library/1d69611f-d8a7-467b-9d57-cbe2f1610bf8) и [AtlSetSacl](http://msdn.microsoft.com/library/54daab9a-8c69-45fd-86c4-18eb30d59547).  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="a-nameaddauditacea--csacladdauditace"></a><a name="addauditace"></a>CSacl::AddAuditAce  
 Добавляет запись управления доступом (ACE) аудита `CSacl` объекта.  
  
```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) объекта.  
  
 `AccessMask`  
 Задает маску прав доступа для аудита для указанного `CSid` объекта.  
  
 `bSuccess`  
 Указывает, будут ли проводить аудит попыток разрешенного доступа. Установка этого флага значение true, чтобы включить аудит; в противном случае присвойте ему значение false.  
  
 *bFailure*  
 Указывает, будут ли проводить аудит попыток запрещен доступ. Установка этого флага значение true, чтобы включить аудит; в противном случае присвойте ему значение false.  
  
 `AceFlags`  
 Набор битовые флаги, определяющие наследование ACE.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении записи ACE `CSacl` объекта, **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Объект `CSacl` содержит записи управления доступом (ACE), определяющих типы попыток доступа, формирующих записи аудита в журнале событий безопасности. Этот метод добавляет такие ACE для `CSacl` объекта. Вторая форма `AddAuditAce` — только на Windows 2000 и более поздних версий.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно установить в `AceFlags` параметр.  
  
##  <a name="a-namecsacla--csaclcsacl"></a><a name="csacl"></a>CSacl::CSacl  
 Конструктор.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий **ACL** структуры (список управления доступом).  
  
### <a name="remarks"></a>Примечания  
 `CSacl` Объект может быть также создан с помощью существующего **ACL** структуры. Убедитесь, что этот параметр является системный список управления доступом (SACL), а не список управления доступом (DACL). В отладочных построениях, если предоставляется список DACL утверждение будет выполняться. В окончательных построениях игнорируются все записи из списка DACL.  
  
##  <a name="a-namedtora--csaclcsacl"></a><a name="dtor"></a>CSacl:: ~ CSacl  
 Деструктор  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все записи управления доступом (ACE).  
  
##  <a name="a-namegetacecounta--csaclgetacecount"></a><a name="getacecount"></a>CSacl::GetAceCount  
 Возвращает количество записей управления доступом (ACE) в `CSacl` объекта.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов управления доступом, содержащиеся в `CSacl` объекта.  
  
##  <a name="a-nameoperatoreqa--csacloperator-"></a><a name="operator_eq"></a>CSacl::operator =  
 Оператор присвоения.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 **ACL** (список управления доступом) для назначения к существующему объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CSacl` объекта. Убедитесь, что **ACL** параметр является на самом деле система список управления доступом (SACL), а не список управления доступом (DACL). В отладочных построениях, утверждение будет выполняться и в сборке выпуска **ACL** параметр будет игнорироваться.  
  
##  <a name="a-nameremoveacea--csaclremoveace"></a><a name="removeace"></a>CSacl::RemoveAce  
 Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) **CSacl** объекта.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACE для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="a-nameremoveallacesa--csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::RemoveAllAces  
 Удаляет все записи управления доступом (ACE), содержащихся в `CSacl` объекта.  
  
```
void RemoveAllAces() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет каждый **ACE** структуры (если таковые имеются) в `CSacl` объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CAcl](../../atl/reference/cacl-class.md)   
 [Списки управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [Элементы управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)

