---
title: Класс CComCriticalSection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5926f92ae636a13c1e5241792790151ee48ceddc
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884874"
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
|[CComCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объектом критический раздел.|  
|[CComCriticalSection::Unlock](#unlock)|Освобождает владение объект критической секции.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|Объект CRITICAL_SECTION.|  
  
## <a name="remarks"></a>Примечания  
 `CComCriticalSection` Аналогично класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), за исключением того, что необходимо явно инициализировать и освободит критический раздел.  
  
 Как правило, используется `CComCriticalSection` через **typedef** имя [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Это имя ссылается на `CComCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) используется.  

  
 См. в разделе [класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md) для более безопасным способом использовать этот класс, чем вызов `Lock` и `Unlock` напрямую.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection  
 Конструктор.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Наборы [m_sec](#m_sec) элемент данных в значение NULL.  
  
##  <a name="init"></a>  CComCriticalSection::Init  
 Вызывает функцию Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), который инициализирует объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения E_OUTOFMEMORY или E_FAIL в случае сбоя.  
  
##  <a name="lock"></a>  CComCriticalSection::Lock  
 Вызывает функцию Win32 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), которого ожидает, пока поток может стать владельцем объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения E_OUTOFMEMORY или E_FAIL в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Сначала необходимо инициализировать объект критической секции с вызовом [Init](#init) метод. Если защищенный код завершения выполнения, поток должен вызвать [Unlock](#unlock) для освобождения владения критический раздел.  
  
##  <a name="m_sec"></a>  CComCriticalSection::m_sec  
 Содержит объект критической секции, который используется всеми `CComCriticalSection` методы.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>  CComCriticalSection::Term  
 Вызывает функцию Win32 [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), который освобождает все ресурсы, используемые объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Один раз `Term` был вызван, критически важные раздел больше не может использоваться для синхронизации.  
  
##  <a name="unlock"></a>  CComCriticalSection::Unlock  
 Вызывает функцию Win32 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), который освобождает владение объект критической секции, содержащиеся в [m_sec](#m_sec) данные-член.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Сначала получить права владельца, поток должен вызвать [блокировки](#lock) метод. Каждый вызов `Lock` требует соответствующего вызова `Unlock` для освобождения владения критический раздел.  
  
## <a name="see-also"></a>См. также  
 [Класс CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)
