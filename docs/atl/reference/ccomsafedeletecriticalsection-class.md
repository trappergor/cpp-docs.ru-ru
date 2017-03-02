---
title: "Класс CComSafeDeleteCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATL::CComSafeDeleteCriticalSection
- ATL.CComSafeDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 511627de9d4f6411c508dd78a237cf546e2493de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafedeletecriticalsection-class"></a>Класс CComSafeDeleteCriticalSection
Этот класс предоставляет методы для получения и освобождения владельца объекта критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Конструктор.|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|Создает и инициализирует объект критической секции.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|Получает права владельца объекта критической секции.|  
|[CComSafeDeleteCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объект критической секции.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Флаги ли внутренний **CRITICAL_SECTION** инициализировать объект.|  
  
## <a name="remarks"></a>Примечания  
 `CComSafeDeleteCriticalSection`является производным от класса [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем не менее `CComSafeDeleteCriticalSection` обеспечивает дополнительную безопасность механизмов [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 При создании экземпляра `CComSafeDeleteCriticalSection` выходит за пределы области или явно удаляется из памяти, базовый объект критической секции будут автоматически удалены, если он все еще действителен. Кроме того [CComSafeDeleteCriticalSection::Term](#term) метод завершит свою работу, если объект базового критический раздел еще не была выделена или уже освобожден из памяти.  
  
 В разделе [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критический раздел.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="a-nameccomsafedeletecriticalsectiona--ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 Конструктор.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_bInitialized](#m_binitialized) член данных **false**.  
  
##  <a name="a-namedtora--ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Деструктор  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает внутренний **CRITICAL_SECTION** объекта из памяти, если [m_bInitialized](#m_binitialized) член данных имеет значение **true**.  
  
##  <a name="a-nameinita--ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComSafeDeleteCriticalSection::Init  
 Вызывает реализацию базового класса [Init](/visualstudio/debugger/init) и задает [m_bInitialized](#m_binitialized) для **true** в случае успешного выполнения.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="a-namelocka--ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CComSafeDeleteCriticalSection::Lock  
Вызывает реализацию базового класса [блокировки](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Примечания  
 Этот метод предполагает [m_bInitialized](#m_binitialized) член данных имеет значение **true** после входа. Утверждение создается в отладочных построениях, если это condidtion не выполнены.  
  
 Дополнительные сведения о работе функции см. [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="a-namembinitializeda--ccomsafedeletecriticalsectionmbinitialized"></a><a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized  
 Флаги ли внутренний **CRITICAL_SECTION** инициализировать объект.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Примечания  
 **M_bInitialized** член данных используется для отслеживания действия базового **CRITICAL_SECTION** объекта, связанного с [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) класса. Базовый **CRITICAL_SECTION** объекта не будет предпринята попытка будет освобожден из памяти, если этот флаг не установлен **true**.  
  
##  <a name="a-nameterma--ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CComSafeDeleteCriticalSection::Term  
 Вызывает реализацию базового класса [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) если внутренний **CRITICAL_SECTION** объект является допустимым.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), или **S_OK** Если [m_bInitialized](#m_binitialized) было задано значение **false** после входа.  
  
### <a name="remarks"></a>Примечания  
 Безопасно для вызова этого метода, даже если внутренний **CRITICAL_SECTION** недопустимый объект. Этот метод вызывается деструктор этого класса, если [m_bInitialized](#m_binitialized) член данных имеет значение **true**.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

