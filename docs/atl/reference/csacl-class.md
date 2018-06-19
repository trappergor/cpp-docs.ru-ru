---
title: Класс CSacl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116e66d36dde016ef902a0b345eec33e46177b6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363588"
---
# <a name="csacl-class"></a>Класс CSacl
Этот класс является оболочкой для структуры системного списка управления ДОСТУПОМ (список управления доступом системы).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSacl : public CAcl
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSacl::CSacl](#csacl)|Конструктор.|  
|[CSacl::~CSacl](#dtor)|Деструктор|  
  
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
 SACL содержит записи управления доступом (ACE), определяющих типы попыток доступа, которые создают записи аудита в журнал событий безопасности контроллера домена. Обратите внимание, что список SACL создаются записи журнала только на контроллере домена, где произошла попытка доступа, а не для каждого контроллера домена, который содержит реплику объекта.  
  
 Чтобы задать или получить список SACL в дескрипторе безопасности объекта, необходимо включить привилегию SE_SECURITY_NAME в маркере доступа запрашивающего потока. Группа администраторов имеет эту привилегию по умолчанию предоставляемый и могут быть предоставлены другим пользователям или группам. Право предоставил не требуется: перед выполнением операции, определяется право доступа, необходимо включить в маркере безопасности доступа для вступили в силу. Модель позволяет правами должен быть включен только для конкретной системы операций, а затем отключены, когда они больше не нужны. В разделе [AtlGetSacl](security-global-functions.md#atlgetsacl) и [AtlSetSacl](security-global-functions.md#atlsetsacl) примеры Включение SE_SECURITY_NAME.  
  
 Используйте методы класса, предоставленные для добавления, удаления, создания и удаления элементов управления доступом из **SACL** объекта. См. также [AtlGetSacl](security-global-functions.md#atlgetsacl) и [AtlSetSacl](security-global-functions.md#atlsetsacl).  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="addauditace"></a>  CSacl::AddAuditAce  
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
 Указывает маску прав доступа для аудита для указанного `CSid` объекта.  
  
 `bSuccess`  
 Указывает, будут ли проводить аудит попыток разрешенного доступа. Этот флаг в значение true, чтобы включить аудит; в противном случае присвоить ему значение false.  
  
 *bFailure*  
 Указывает, будут ли проводить аудит попыток запрещен доступ. Этот флаг в значение true, чтобы включить аудит; в противном случае присвоить ему значение false.  
  
 `AceFlags`  
 Набор битовых флагов, которые управляют ACE наследования.  
  
 `pObjectType`  
 Тип объекта.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** при добавлении ACE `CSacl` объекта, **false** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Объект `CSacl` объект содержит записи управления доступом (ACE), определяющих типы попыток доступа, которые создают записи аудита в журнал событий безопасности. Этот метод добавляет такие записи управления ДОСТУПОМ к `CSacl` объекта.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Описание различных флагов, которые можно задать в `AceFlags` параметра.  
  
##  <a name="csacl"></a>  CSacl::CSacl  
 Конструктор.  
  
```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий **ACL** структуры (список управления доступом).  
  
### <a name="remarks"></a>Примечания  
 `CSacl` Можно при необходимости создать объект с помощью существующей **ACL** структуры. Убедитесь, что этот параметр используется системный список управления доступом (SACL), а не список управления доступом (DACL). В отладочных построениях, если список DACL предоставляется утверждение будет выполняться. В сборках выпуска все записи из списка DACL учитываются.  
  
##  <a name="dtor"></a>  CSacl::~CSacl  
 Деструктор  
  
```
~CSacl() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные с помощью объекта, включая все записи управления доступом (ACE).  
  
##  <a name="getacecount"></a>  CSacl::GetAceCount  
 Возвращает количество записей управления доступом (ACE) в `CSacl` объекта.  
  
```
UINT GetAceCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов управления доступом, содержащиеся в `CSacl` объекта.  
  
##  <a name="operator_eq"></a>  CSacl::operator =  
 Оператор присвоения.  
  
```
CSacl& operator=(const ACL& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 **ACL** (список управления доступом) для назначения для существующего объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CSacl` объекта. Убедитесь, что **ACL** параметр является фактически системы список управления доступом (SACL), а не список управления доступом (DACL). В отладочных построениях, утверждения будет выполняться и в сборках выпуска **ACL** параметр будет игнорироваться.  
  
##  <a name="removeace"></a>  CSacl::RemoveAce  
 Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) **CSacl** объекта.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACE для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeallaces"></a>  CSacl::RemoveAllAces  
 Удаляет все элементы управления доступом (ACE), содержащихся в `CSacl` объекта.  
  
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
