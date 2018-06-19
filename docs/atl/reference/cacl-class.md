---
title: Класс CAcl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bab138d743dc3f5346ce15449c2a31b5b2484fd9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365345"
---
# <a name="cacl-class"></a>Класс CAcl
Этот класс является оболочкой для `ACL` структуры (список управления доступом).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAcl
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Массив `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](#caceflagarray)|Массив `BYTE`s.|  
|[CAcl::CAceTypeArray](#cacetypearray)|Массив `BYTE`s.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|Конструктор.|  
|[CAcl:: ~ CAcl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|Возвращает количество управления доступом объектов для управления доступом.|  
|[CAcl::GetAclEntries](#getaclentries)|Получает записи списка управления Доступом управления доступом из `CAcl` объекта.|  
|[CAcl::GetAclEntry](#getaclentry)|Извлекает все сведения о записи в `CAcl` объекта.|  
|[CAcl::GetLength](#getlength)|Возвращает длину списка управления Доступом.|  
|[CAcl::GetPACL](#getpacl)|Возвращает PACL (указатель на список управления Доступом).|  
|[CAcl::IsEmpty](#isempty)|Тесты `CAcl` объект для записи.|  
|[CAcl::IsNull](#isnull)|Возвращает состояние `CAcl` объекта.|  
|[CAcl::RemoveAce](#removeace)|Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) `CAcl` объекта.|  
|[CAcl::RemoveAces](#removeaces)|Удаляет все элементы управления доступом (элементы управления доступом) из `CAcl` , применимых к данной `CSid`.|  
|[CAcl::SetEmpty](#setempty)|Метки `CAcl` объекта как пустой.|  
|[CAcl::SetNull](#setnull)|Метки `CAcl` объекта в виде `NULL`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|Приведение `CAcl` объект `ACL` структуры.|  
|[CAcl::operator =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 **ACL** структура является заголовок ACL (список управления доступом). Список управления Доступом содержит последовательный список из нуля или более [записи ACE](http://msdn.microsoft.com/library/windows/desktop/aa374868) (элементы управления доступом). Отдельные ACE в ACL нумеруются от 0 до *n-1*, где *n* — количество элементов управления доступом в списке управления Доступом. При редактировании ACL, приложение обращается к записи управления доступом (ACE) в список управления Доступом по его индексу.  
  
 Существует два типа списков ACL:  
  
-   Избирательные  
  
-   Система  
  
 Таблицы управления Доступом управляется владельцем объекта или любой пользователь, предоставлены **WRITE_DAC** доступ к объекту. Он указывает на объект может иметь доступ определенным пользователям и группам. Например владелец файла можно использовать таблицы управления Доступом, указать, какие пользователи и группы могут и не может иметь доступ к файлу.  
  
 Объект также может иметь сведения о безопасности системного уровня, связанные с ним, в виде системы ACL управляются системным администратором. Система ACL можно разрешить системному администратору для аудита любые попытки получить доступ к объекту.  
  
 Дополнительные сведения см. в разделе [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) обсуждения в Windows SDK.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray  
 Массив объектов ACCESS_MASK.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа задает тип массива, который может использоваться для хранения используются права доступа в записи управления доступом (ACE).  
  
##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray  
 Массив байтов.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа задает тип массива, используемые для определения флагов управления конкретного типа управления доступом управления доступом. В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) определение полный список возможных флагов.  
  
##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray  
 Массив байтов.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа задает тип массива, используемые для определения объектов управления доступом (ACE) запись, таких как ACCESS_ALLOWED_ACE_TYPE или ACCESS_DENIED_ACE_TYPE характера. В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) определение полный список возможных типов.  
  
##  <a name="cacl"></a>  CAcl::CAcl  
 Конструктор.  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий объект `CAcl`.  
  
### <a name="remarks"></a>Примечания  
 `CAcl` Можно при необходимости создать объект с помощью существующей `CAcl` объекта.  
  
##  <a name="dtor"></a>  CAcl:: ~ CAcl  
 Деструктор  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные из объекта.  
  
##  <a name="getacecount"></a>  CAcl::GetAceCount  
 Возвращает количество управления доступом объектов для управления доступом.  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число записей управления ДОСТУПОМ в `CAcl` объекта.  
  
##  <a name="getaclentries"></a>  CAcl::GetAclEntries  
 Получает записи списка управления Доступом управления доступом из `CAcl` объекта.  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pSids`  
 Указатель на массив [CSid](../../atl/reference/csid-class.md) объектов.  
  
 *pAccessMasks*  
 Маски доступа.  
  
 *pAceTypes*  
 Записи управления доступом ( **ACE**) типы.  
  
 *pAceFlags*  
 **ACE** флаги.  
  
### <a name="remarks"></a>Примечания  
 Этот метод заполняет параметров массива подробные сведения о каждом **ACE** объектов, содержащихся в `CAcl` объекта. Используйте значение NULL, если не требуются сведения для этого конкретного массива.  
  
 Содержимое каждого массива соответствуют друг к другу, то есть первый элемент `CAccessMaskArray` соответствует на первый элемент в массиве `CSidArray` массива и т. д.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Дополнительные сведения о типах элементов управления ДОСТУПОМ и флаги.  
  
##  <a name="getaclentry"></a>  CAcl::GetAclEntry  
 Извлекает все сведения о записи в списке управления доступом (ACL).  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACL для получения.  
  
 `pSid`  
 [CSid](../../atl/reference/csid-class.md) объекта, к которому применяется запись ACL.  
  
 *pMask*  
 Маска, задающая разрешения для предоставления или запрета доступа.  
  
 `pType`  
 Тип элемента управления ДОСТУПОМ.  
  
 `pFlags`  
 Флаги управления ДОСТУПОМ.  
  
 `pObjectType`  
 Тип объекта. Это будет присвоено GUID_NULL Если тип объекта не указан в записи управления ДОСТУПОМ или ACE не ОБЪЕКТА ACE.  
  
 `pInheritedObjectType`  
 Типом наследуемого объекта. Это будет присвоено GUID_NULL типом наследуемого объекта не указан в записи управления ДОСТУПОМ или ACE не ОБЪЕКТА ACE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлечет все сведения об отдельных ACE, предоставляющий дополнительные сведения, чем [CAcl::GetAclEntries](#getaclentries) отдельно делает доступными.  
  
 В разделе [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) Дополнительные сведения о типах элементов управления ДОСТУПОМ и флаги.  
  
##  <a name="getlength"></a>  CAcl::GetLength  
 Возвращает длину списка управления доступом (ACL).  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает требуемую длину в байтах, необходимым для размещения **ACL** структуры.  
  
##  <a name="getpacl"></a>  CAcl::GetPACL  
 Возвращает указатель на список управления доступом (ACL).  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на **ACL** структуры.  
  
##  <a name="isempty"></a>  CAcl::IsEmpty  
 Тесты `CAcl` объект для записи.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает **true** Если `CAcl` объект не имеет значение NULL и не содержит записей. Возвращает **false** Если `CAcl` объект имеет значение NULL или содержит по крайней мере одну запись.  
  
##  <a name="isnull"></a>  CAcl::IsNull  
 Возвращает состояние `CAcl` объекта.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CAcl` объект имеет значение NULL, **false** в противном случае.  
  
##  <a name="operator_const_acl__star"></a>  CAcl::operator const ACL *  
 Приведение `CAcl` объект **ACL** структуры (список управления доступом).  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает адрес **ACL** структуры.  
  
##  <a name="operator_eq"></a>  CAcl::operator =  
 Оператор присвоения.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CAcl` Для назначения для существующего объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CAcl` объекта.  
  
##  <a name="removeace"></a>  CAcl::RemoveAce  
 Удаляет из конкретного элемента управления ДОСТУПОМ (записи управления доступом) **CAcl** объекта.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Указатель записи ACE для удаления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является производным от [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeaces"></a>  CAcl::RemoveAces  
 Удаляет записи ACE alls (элементы управления доступом) из `CAcl` , применимых к данной `CSid`.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>Параметры  
 `rSid`  
 Ссылка на объект `CSid`.  
  
##  <a name="setempty"></a>  CAcl::SetEmpty  
 Метки `CAcl` объекта как пустой.  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>Примечания  
 `CAcl` Можно задать пустое или значение NULL: два состояния должны быть уникальными.  
  
##  <a name="setnull"></a>  CAcl::SetNull  
 Метки `CAcl` объект как NULL.  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>Примечания  
 `CAcl` Можно задать пустое или значение NULL: два состояния должны быть уникальными.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
