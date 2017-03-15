---
title: "Класс CSyncObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSyncObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject class
- synchronization classes, CSyncObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
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
ms.openlocfilehash: a1f0c8ddfbfaf129bb18c14d36b998dd37d35899
ms.lasthandoff: 02/24/2017

---
# <a name="csyncobject-class"></a>Класс CSyncObject
Чисто виртуальный класс, обеспечивающий общую функциональность объектов синхронизации Win32.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Создает объект `CSyncObject`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Улучшение доступа к объекту синхронизации.|  
|[CSyncObject::Unlock](#unlock)|Улучшение доступа к объекту синхронизации.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSyncObject::operator ДЕСКРИПТОРА](#operator_handle)|Предоставляет доступ к объекту синхронизации.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|Дескриптор базового объекта синхронизации.|  
  
## <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation предоставляет несколько классов, производных от `CSyncObject`. Это [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Сведения о том, как использовать объекты синхронизации, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="a-namecsyncobjecta--csyncobjectcsyncobject"></a><a name="csyncobject"></a>CSyncObject::CSyncObject  
 Создает объект синхронизации с предоставленным именем.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Параметры  
 `pstrName`  
 Имя объекта. Если **NULL**, *pstrName* будет иметь значение null.  
  
##  <a name="a-namelocka--csyncobjectlock"></a><a name="lock"></a>CSyncObject::Lock  
 Эта функция вызывается для доступа к ресурсу, контролируются объекта синхронизации.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTimeout`  
 Указывает количество времени в миллисекундах для ожидания объекта синхронизации доступны (сигнал). Если **БЕСКОНЕЧНЫЙ**, `Lock` будет ждать перед возвратом оповещении объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если объект синхронизации, получает сигнал, `Lock` успешного возвращения и поток теперь принадлежит объект. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметр. Если объект синхронизации не был отправлен сигнал в заданного количества времени, `Lock` возвращает сбой.  
  
##  <a name="a-namemhobjecta--csyncobjectmhobject"></a><a name="m_hobject"></a>CSyncObject::m_hObject  
 Дескриптор базового объекта синхронизации.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="a-nameoperatorhandlea--csyncobjectoperator-handle"></a><a name="operator_handle"></a>CSyncObject::operator ДЕСКРИПТОРА  
 Этот оператор используется для получения дескриптора `CSyncObject` объекта.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха дескриптор объекта синхронизации; в противном случае — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.  
  
##  <a name="a-nameunlocka--csyncobjectunlock"></a><a name="unlock"></a>CSyncObject::Unlock  
 Объявление `Unlock` без параметров является чисто виртуальную функцию и должны быть переопределены все классы, производные от `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Не используется в реализации по умолчанию.  
  
 `lpPrevCount`  
 Не используется в реализации по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию всегда возвращает **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию объявления с двумя параметрами всегда возвращает **TRUE**. Эта функция вызывается для предоставления доступа к объект синхронизации, принадлежащий вызывающего потока. Второе объявление предоставляется для объектов синхронизации, например, семафоры, позволяющие более одного доступ к контролируемому ресурсу.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




