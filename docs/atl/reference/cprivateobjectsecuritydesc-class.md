---
title: "Класс CPrivateObjectSecurityDesc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CPrivateObjectSecurityDesc
- ATL::CPrivateObjectSecurityDesc
- CPrivateObjectSecurityDesc
dev_langs:
- C++
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 154a4229f8963d3081e6e0518354d17968ee0e20
ms.lasthandoff: 02/24/2017

---
# <a name="cprivateobjectsecuritydesc-class"></a>Класс CPrivateObjectSecurityDesc
Этот класс представляет частного дескриптора безопасности объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Конструктор.|  
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Этот метод используется для преобразования в формат, который поддерживает автоматическое распространение записи наследуемые управления доступом (ACE) дескриптора безопасности и ее списки управления доступом (ACL).|  
|[CPrivateObjectSecurityDesc::Create](#create)|Этот метод используется для размещения и инициализации дескриптор безопасности в относительный для закрытого объекта, созданного путем вызова диспетчера ресурсов.|  
|[CPrivateObjectSecurityDesc::Get](#get)|Этот метод используется для извлечения сведений из дескриптора безопасности закрытый объект.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Вызовите этот метод, чтобы изменить дескриптор безопасности закрытый объект.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс, производный от [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), предоставляет методы для создания и управления дескриптор безопасности закрытого объекта.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="a-nameconverttoautoinherita--cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 Этот метод используется для преобразования в формат, который поддерживает автоматическое распространение записи наследуемые управления доступом (ACE) дескриптора безопасности и ее списки управления доступом (ACL).  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта, ссылающегося на родительский контейнер объекта. Если нет родительского контейнера, этот параметр имеет значение NULL.  
  
 `ObjectType`  
 Указатель на **GUID** структура, определяющая тип объекта, связанного с текущим объектом. Задайте `ObjectType` значение NULL, если объект не имеет идентификатор GUID.  
  
 `bIsDirectoryObject`  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структура, которая задает сопоставление каждого универсальные права на особые права для объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается определить список ли элементы управления доступом в управления доступом (DACL) и системный список управления доступом (SACL) текущего дескриптора безопасности были унаследованы от родительского дескриптора безопасности. Он вызывает [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) функции.  
  
##  <a name="a-namecprivateobjectsecuritydesca--cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 Конструктор.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CPrivateObjectSecurityDesc` объекта.  
  
##  <a name="a-namedtora--cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 Деструктор  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы и удаляет закрытый объект дескриптора безопасности.  
  
##  <a name="a-namecreatea--cprivateobjectsecuritydesccreate"></a><a name="create"></a>CPrivateObjectSecurityDesc::Create  
 Этот метод используется для размещения и инициализации дескриптор безопасности в относительный для закрытого объекта, созданного путем вызова диспетчера ресурсов.  
  
```
bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта, ссылающегося на родительский каталог, в котором создается новый объект. Значение NULL, если не существует родительского каталога.  
  
 `pCreator`  
 Указатель на дескриптор безопасности, предоставляемые создатель объекта. Если создатель объекта явным образом не передает сведения о безопасности для нового объекта, этот параметр в значение NULL.  
  
 `bIsDirectoryObject`  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `Token`  
 Ссылка на [CAccessToken](../../atl/reference/caccesstoken-class.md) объекта для процесса клиента, от лица которого создается объект.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структура, которая задает сопоставление каждого универсальные права на особые права для объекта.  
  
 `ObjectType`  
 Указатель на **GUID** структура, определяющая тип объекта, связанного с текущим объектом. Задайте `ObjectType` значение NULL, если объект не имеет идентификатор GUID.  
  
 *bIsContainerObject*  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `AutoInheritFlags`  
 Набор битовых флагов, которые управляют наследованием записи управления доступом (ACE) из `pParent`. В разделе [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) или [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581).  
  
 Второй метод, позволяющий указывать тип объекта новый объект GUID или Управление наследованием записи ACE, только на компьютерах с Windows 2000 и более поздних версий.  
  
> [!NOTE]
>  Дескриптор безопасности в относительный является дескриптор безопасности, который хранит все свои сведения о безопасности в непрерывном блоке памяти.  
  
##  <a name="a-namegeta--cprivateobjectsecuritydescget"></a><a name="get"></a>CPrivateObjectSecurityDesc::Get  
 Этот метод используется для извлечения сведений из дескриптора безопасности закрытый объект.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `si`  
 Набор битовых флагов, которые указывают на части для получения дескриптора безопасности. Это значение может быть сочетанием [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) битовые флаги.  
  
 `pResult`  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объект, который получает копию запрошенную информацию из дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности не является структуры и связанных данных, содержащий сведения о безопасности для защищаемого объекта.  
  
##  <a name="a-nameoperatoreqa--cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>CPrivateObjectSecurityDesc::operator =  
 Оператор присвоения.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CPrivateObjectSecurityDesc` Объект текущему объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CPrivateObjectSecurityDesc` объекта.  
  
##  <a name="a-nameseta--cprivateobjectsecuritydescset"></a><a name="set"></a>CPrivateObjectSecurityDesc::Set  
 Вызовите этот метод, чтобы изменить дескриптор безопасности закрытый объект.  
  
```
bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `si`  
 Набор битовых флагов, которые указывают на части дескриптора безопасности. Это значение может быть сочетанием [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) битовые флаги.  
  
 *Изменения*  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта. Части этого дескриптора безопасности обозначается `si` параметра применяются в дескрипторе безопасности объекта.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структура, которая задает сопоставление каждого универсальные права на особые права для объекта.  
  
 `Token`  
 Ссылка на [CAccessToken](../../atl/reference/caccesstoken-class.md) объекта для процесса клиента, от лица которого создается объект.  
  
 `AutoInheritFlags`  
 Набор битовых флагов, которые управляют наследованием записи управления доступом (ACE) из `pParent`. В разделе [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Второй метод, позволяющий указывать тип GUID объекта или Управление наследованием записи ACE, только на компьютерах с Windows 2000 и более поздних версий.  
  
## <a name="see-also"></a>См. также  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)   
 [Класс CSecurityDesc](../../atl/reference/csecuritydesc-class.md)

