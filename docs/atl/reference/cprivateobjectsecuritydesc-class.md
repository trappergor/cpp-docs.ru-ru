---
title: "Класс CPrivateObjectSecurityDesc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
dev_langs: C++
helpviewer_keywords: CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 310ccd778a0d681afad40b7dd67067c9e9af875d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cprivateobjectsecuritydesc-class"></a>Класс CPrivateObjectSecurityDesc
Этот класс представляет объект дескриптора безопасности закрытый объект.  
  
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
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Этот метод используется для преобразования в формат, который поддерживает автоматическое распространение наследуемых управления доступом (ACE) в дескрипторе безопасности и его списки управления доступом (ACL).|  
|[CPrivateObjectSecurityDesc::Create](#create)|Этот метод используется для размещения и инициализации дескриптор безопасности в относительный для закрытого объекта, созданного путем вызова диспетчера ресурсов.|  
|[CPrivateObjectSecurityDesc::Get](#get)|Этот метод используется для извлечения сведений из дескриптора безопасности закрытый объект.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Вызовите этот метод, чтобы изменить дескриптор безопасности закрытый объект.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Оператор присвоения.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс, производный от [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), предоставляет методы для создания и управления закрытый объект дескриптора безопасности.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 Этот метод используется для преобразования в формат, который поддерживает автоматическое распространение наследуемых управления доступом (ACE) в дескрипторе безопасности и его списки управления доступом (ACL).  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pParent`  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта, ссылающегося на родительский контейнер объекта. Если нет ни одного родительского контейнера, этот параметр имеет значение NULL.  
  
 `ObjectType`  
 Указатель на **GUID** структура, определяющая тип объекта, связанного с текущим объектом. Задать `ObjectType` значение NULL, если объект не имеет идентификатора GUID.  
  
 `bIsDirectoryObject`  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структуру, которая определяет сопоставление каждой универсального справа определенных прав для объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается определить список ли элементы управления доступом в управления доступом (DACL) и системный список управления доступом (SACL) текущего дескриптора безопасности были унаследованы от родительского дескриптора безопасности. Он вызывает [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) функции.  
  
##  <a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 Конструктор.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CPrivateObjectSecurityDesc` объекта.  
  
##  <a name="dtor"></a>CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 Деструктор  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все выделенные ресурсы и удаляет закрытый объект дескриптора безопасности.  
  
##  <a name="create"></a>CPrivateObjectSecurityDesc::Create  
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
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта, ссылающегося на родительский каталог, в котором создается новый объект. Значение NULL, если нет родительского каталога.  
  
 `pCreator`  
 Указатель на дескриптор безопасности, предоставляемые создатель объекта. Если создатель объекта явно не передает сведения о безопасности для нового объекта, установите этот параметр в значение NULL.  
  
 `bIsDirectoryObject`  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `Token`  
 Ссылка на [CAccessToken](../../atl/reference/caccesstoken-class.md) объекта для процесса клиента, от имени которого создается объект.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структуру, которая определяет сопоставление каждой универсального справа определенных прав для объекта.  
  
 `ObjectType`  
 Указатель на **GUID** структура, определяющая тип объекта, связанного с текущим объектом. Задать `ObjectType` значение NULL, если объект не имеет идентификатора GUID.  
  
 *bIsContainerObject*  
 Указывает, является ли новый объект может содержать другие объекты. Значение true указывает, что новый объект является контейнером. Значение false указывает, что новый объект не является контейнером.  
  
 `AutoInheritFlags`  
 Набор битовых флагов, определяющих способ управления доступом (ACE) наследуются от `pParent`. В разделе [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) или [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581).  
  
 Второй метод, который разрешает указание тип объекта новый объект GUID или Управление наследованием записи управления доступом, только на компьютерах с Windows 2000 и более поздних версий.  
  
> [!NOTE]
>  Дескриптор безопасности в относительный является дескриптора безопасности, который хранит все сведения о безопасности в непрерывный блок памяти.  
  
##  <a name="get"></a>CPrivateObjectSecurityDesc::Get  
 Этот метод используется для извлечения сведений из дескриптора безопасности закрытый объект.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `si`  
 Набор битовых флагов, которые указывают на части для получения дескриптора безопасности. Это значение может представлять собой сочетание [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) битовых флагов.  
  
 `pResult`  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объект, который получает копию требуемую информацию из дескриптора безопасности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор безопасности не является структуры и связанных данных, содержащий сведения о безопасности для защищаемого объекта.  
  
##  <a name="operator_eq"></a>CPrivateObjectSecurityDesc::operator =  
 Оператор присвоения.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `CPrivateObjectSecurityDesc` Объект текущему объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CPrivateObjectSecurityDesc` объекта.  
  
##  <a name="set"></a>CPrivateObjectSecurityDesc::Set  
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
 Набор битовых флагов, которые указывают на части дескриптор безопасности для задания. Это значение может представлять собой сочетание [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) битовых флагов.  
  
 *Изменения*  
 Указатель на [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) объекта. Указывает части дескриптор безопасности `si` параметра применяются для дескриптора безопасности объекта.  
  
 `GenericMapping`  
 Указатель на [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) структуру, которая определяет сопоставление каждой универсального справа определенных прав для объекта.  
  
 `Token`  
 Ссылка на [CAccessToken](../../atl/reference/caccesstoken-class.md) объекта для процесса клиента, от имени которого создается объект.  
  
 `AutoInheritFlags`  
 Набор битовых флагов, определяющих способ управления доступом (ACE) наследуются от `pParent`. В разделе [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) для получения дополнительных сведений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если операция выполнена успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Второй метод, который разрешает указание объекта типа GUID объекта или Управление наследованием записи управления доступом, только на компьютерах с Windows 2000 и более поздних версий.  
  
## <a name="see-also"></a>См. также  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)   
 [Класс CSecurityDesc](../../atl/reference/csecuritydesc-class.md)
