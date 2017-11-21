---
title: "Класс CComSafeDeleteCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs: C++
helpviewer_keywords: CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c9887a64131b8e7153ca54f73007386003c87ac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ccomsafedeletecriticalsection-class"></a>Класс CComSafeDeleteCriticalSection
Этот класс предоставляет методы для получения и освобождения владения объект критической секции.  
  
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
|[CComSafeDeleteCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объектом критической секции.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|Флаги ли внутренний **CRITICAL_SECTION** объект был инициализирован.|  
  
## <a name="remarks"></a>Примечания  
 `CComSafeDeleteCriticalSection`является производным от класса [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем не менее `CComSafeDeleteCriticalSection` обеспечивает дополнительную безопасность механизмы [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).  
  
 При создании экземпляра `CComSafeDeleteCriticalSection` выходит за пределы области или явным образом удалено из памяти, базовый объект критической секции будут автоматически очищены Если по-прежнему действителен. Кроме того [CComSafeDeleteCriticalSection::Term](#term) метод завершит свою работу, если базовый объект критической секции не была выделена или уже был выпущен из памяти.  
  
 В разделе [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критической секции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 Конструктор.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_bInitialized](#m_binitialized) данные-члены **false**.  
  
##  <a name="dtor"></a>CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 Деструктор  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает внутренний **CRITICAL_SECTION** объекта из памяти, если [m_bInitialized](#m_binitialized) член данных имеет значение **true**.  
  
##  <a name="init"></a>CComSafeDeleteCriticalSection::Init  
 Вызывает реализацию базового класса [Init](/visualstudio/debugger/init) и задает [m_bInitialized](#m_binitialized) для **true** в случае успешного выполнения.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).  
  
##  <a name="lock"></a>CComSafeDeleteCriticalSection::Lock  
Вызывает реализацию базового класса [блокировки](ccomcriticalsection-class.md#lock).  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
### <a name="remarks"></a>Примечания  
 Этот метод предполагает [m_bInitialized](#m_binitialized) член данных имеет значение **true** после входа. Утверждение создается в отладочных построениях, если это condidtion не выполнены.  
  
 Дополнительные сведения о работе функции см. [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).  
  
##  <a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized  
 Флаги ли внутренний **CRITICAL_SECTION** объект был инициализирован.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>Примечания  
 **M_bInitialized** член данных используется для отслеживания действия базового **CRITICAL_SECTION** объекта, связанного с [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) класса. Базовый **CRITICAL_SECTION** объект не будет предпринято обновляться из памяти, если этот флаг не установлен **true**.  
  
##  <a name="term"></a>CComSafeDeleteCriticalSection::Term  
 Вызывает реализацию базового класса [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) если внутренний **CRITICAL_SECTION** объект является допустимым.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает результат [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), или **S_OK** Если [m_bInitialized](#m_binitialized) было задано значение **false** после входа.  
  
### <a name="remarks"></a>Примечания  
 Можно безопасно вызывать этот метод даже если внутренний **CRITICAL_SECTION** недопустимый объект. Этот метод вызывается деструктор этого класса, если [m_bInitialized](#m_binitialized) член данных имеет значение **true**.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
