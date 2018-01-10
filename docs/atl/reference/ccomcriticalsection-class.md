---
title: "Класс CComCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs: C++
helpviewer_keywords: CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 827ba99a141799af42fab65c36df1f22d212260a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcriticalsection-class"></a>Класс CComCriticalSection
Этот класс предоставляет методы для получения и освобождения владения объект критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|Создает и инициализирует объект критической секции.|  
|[CComCriticalSection::Lock](#lock)|Получает права владельца объекта критической секции.|  
|[CComCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объектом критической секции.|  
|[CComCriticalSection::Unlock](#unlock)|Освобождает владение объект критической секции.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|Объект **CRITICAL_SECTION** объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComCriticalSection`похож на класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), за исключением того, что необходимо явно инициализировать и освободит критический раздел.  
  
 Как правило, используется `CComCriticalSection` через `typedef` имя [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Это имя ссылается на `CComCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) уже используется.  

  
 В разделе [класса CComCritSecLock](../../atl/reference/ccomcritseclock-class.md) для более безопасным способом с помощью этого класса, чем вызов `Lock` и `Unlock` напрямую.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 Конструктор.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_sec](#m_sec) данные-член NULL **.**  
  
##  <a name="init"></a>CComCriticalSection::Init  
 Вызывает функцию Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), который инициализирует объект критической секции, содержащиеся в [m_sec](#m_sec) члена данных.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` при успешном выполнении **E_OUTOFMEMORY** или **E_FAIL** при сбое.  
  
##  <a name="lock"></a>CComCriticalSection::Lock  
 Вызывает функцию Win32 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), который ожидает, пока поток может стать владельцем объект критической секции, содержащиеся в [m_sec](#m_sec) члена данных.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` при успешном выполнении **E_OUTOFMEMORY** или **E_FAIL** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Сначала необходимо инициализировать объект критической секции с помощью вызова [Init](#init) метод. По завершении выполнения защищенный код поток должен вызвать [Unlock](#unlock) владения критической секции.  
  
##  <a name="m_sec"></a>CComCriticalSection::m_sec  
 Содержит объект критической секции, который используется всеми `CComCriticalSection` методы.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>CComCriticalSection::Term  
 Вызывает функцию Win32 [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), который освобождает все ресурсы, используемые объект критической секции, содержащиеся в [m_sec](#m_sec) члена данных.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Один раз `Term` был вызван, критически важные раздел больше не может использоваться для синхронизации.  
  
##  <a name="unlock"></a>CComCriticalSection::Unlock  
 Вызывает функцию Win32 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), который освобождает владение объект критической секции, содержащиеся в [m_sec](#m_sec) члена данных.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сначала получить права владельца, необходимо вызвать поток [блокировки](#lock) метод. Каждый вызов `Lock` требуется соответствующий вызов `Unlock` для освобождения владения критической секции.  
  
## <a name="see-also"></a>См. также  
 [Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)
