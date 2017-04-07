---
title: "Класс CMultiLock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock class
- synchronization objects, access control
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a58d59d8e4d7a1c542dee80295dd8eef6c8be338
ms.lasthandoff: 02/24/2017

---
# <a name="cmultilock-class"></a>Класс CMultiLock
Класс представляет механизм контроля доступа к ресурсам в многопоточных программах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|Создает объект `CMultiLock`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|Определяет, заблокирован при синхронизации конкретного объекта в массиве.|  
|[CMultiLock::Lock](#lock)|Ожиданий в массиве объектов синхронизации.|  
|[CMultiLock::Unlock](#unlock)|Освобождает все объекты собственную синхронизацию.|  
  
## <a name="remarks"></a>Примечания  
 `CMultiLock`не имеет базового класса.  
  
 Использование классов синхронизации [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), и [CEvent](../../mfc/reference/cevent-class.md), можно создать либо **CMultiLock** или [класс CSingleLock](../../mfc/reference/csinglelock-class.md) объект для ожидания и освободить объект синхронизации. Используйте **CMultiLock** при наличии нескольких объектов, которые можно использовать в конкретный момент времени. Использование `CSingleLock` при достаточно ожидает один объект за раз.  
  
 Для использования **CMultiLock** объекта, сначала создайте массив объектов синхронизации, которые вы хотите ожидание. Затем вызовите **CMultiLock** конструктор объекта внутри функции-члена в классе управляемый ресурс. Затем вызовите [блокировку](#lock) функции-члена для определения доступности ресурса (сигнал). Если такой объект, продолжите остальная часть функции-члена. Если ресурс не доступен, ожидания на определенное время для ресурса, освобождения или сбой запроса. После завершения использования ресурса, либо вызвать [Unlock](#unlock) работать, если **CMultiLock** должен использоваться повторно, или разрешить **CMultiLock** объект будет уничтожен.  
  
 **CMultiLock** объектов наиболее полезны, когда поток имеет большое количество `CEvent` может отвечать на объекты. Создайте массив, содержащий все `CEvent` указатели и вызвать метод `Lock`. В результате поток ожидает завершения события, получает сигнал.  
  
 Дополнительные сведения об использовании **CMultiLock** объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CMultiLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="cmultilock"></a>CMultiLock::CMultiLock  
 Создает **CMultiLock** объекта.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `ppObjects`  
 Массив указателей на объекты синхронизации для ожидания на. Не может быть **NULL**.  
  
 `dwCount`  
 Число объектов в `ppObjects`. Должно быть больше 0.  
  
 `bInitialLock`  
 Указывает, следует сначала пытаются получить доступ к любой из предоставленных объектов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после создания массива объектов синхронизации для ожидания на. Она обычно вызывается из потока, который необходимо дождаться один из объектов синхронизации станет доступным.  
  
##  <a name="islocked"></a>CMultiLock::IsLocked  
 Определяет, является ли указанный объект несигнальное (недоступно).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>Параметры  
 *dwItem*  
 Индекс в массиве объектов, соответствующих объекту, состояние которого выполняется запрос.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанный объект заблокирован; в противном случае — 0.  
  
##  <a name="lock"></a>CMultiLock::Lock  
 Эта функция вызывается для получения доступа к одной или нескольким ресурсы, управляемые объекты синхронизации, передаваемые **CMultiLock** конструктор.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *dwTimeOut*  
 Указывает время ожидания для объекта синхронизации доступны (сигнал). Если **БЕСКОНЕЧНЫЙ**, `Lock` будет ждать перед возвратом оповещении объекта.  
  
 `bWaitForAll`  
 Указывает, должны принять сигнал ожидания на все объекты, в то же время перед возвратом. Если **FALSE**, `Lock` вернет когда сигнал один из объектов, ожидается.  
  
 `dwWakeMask`  
 Указывает другие условия, которые могут прервать ожидание. Полный список доступных параметров для этого параметра в разделе [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `Lock` завершается ошибкой, возвращается-1. В случае успеха возвращает одно из следующих значений:  
  
-   Между **WAIT_OBJECT_0** и **WAIT_OBJECT_0** + (число объектов — 1)  
  
     Если `bWaitForAll` — **TRUE**, все объекты получают сигнал (доступна). Если `bWaitForAll` — **FALSE**, возвращаемое значение — **WAIT_OBJECT_0** — это индекс в массиве объектов объекта, который получает сигнал (доступно).  
  
- **WAIT_OBJECT_0** + (число объектов)  
  
     События, указанного в `dwWakeMask` доступен в очереди входного потока.  
  
-   Между **WAIT_ABANDONED_0** и **WAIT_ABANDONED_0** + (число объектов — 1)  
  
     Если `bWaitForAll` — **TRUE**, все объекты сигнал, и по крайней мере один из объектов является объект Брошенный mutex. Если `bWaitForAll` — **FALSE**, возвращаемое значение — **WAIT_ABANDONED_0** — это индекс в массиве объектов Брошенный mutex объекта, удовлетворившего операцию ожидания.  
  
- **WAIT_TIMEOUT**  
  
     Интервал времени ожидания, указанный в *dwTimeOut* даже без успешного ожидания истек.  
  
### <a name="remarks"></a>Примечания  
 Если `bWaitForAll` — **TRUE**, `Lock` вернет успешно, как только все объекты синхронизации сигнальное одновременно. Если `bWaitForAll` — **FALSE**, `Lock` будет возвращать а оповещенным, один или несколько объектов синхронизации.  
  
 Если `Lock` не может возвращать значение немедленно, он будет ожидать не более указанного числа миллисекунд в *dwTimeOut* параметр перед возвратом. Если *dwTimeOut* — **БЕСКОНЕЧНЫЙ**, `Lock` не возвращается до получили доступ к объекту или условия, указанного в `dwWakeMask` было выполнено. В противном случае, если `Lock` была возможность получения объекта синхронизации, то возвращается успешно; в противном случае возвращается ошибка.  
  
##  <a name="unlock"></a>CMultiLock::Unlock  
 Освобождает объект синхронизации, принадлежащий `CMultiLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Номер ссылки счетчики для выпуска. Должно быть больше 0. Если указанное вызовет число объектов превышает максимальное значение, значение счетчика не изменяются, и функция возвращает **FALSE**.  
  
 `lPrevCount`  
 Указывает на переменную для получения предыдущих счетчик для объекта синхронизации. Если **NULL**, предыдущее количество не возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается `CMultiLock`деструктор.  
  
 Первая форма `Unlock` пытается разблокировать объект синхронизации, управляются `CMultiLock`. Вторая форма `Unlock` пытается разблокировать `CSemaphore` объектов, принадлежащих `CMultiLock`. Если `CMultiLock` не владеет заблокированные `CSemaphore` объекта, функция возвращает **FALSE**; в противном случае, она возвращает **TRUE**. `lCount`и `lpPrevCount` одинаковы как параметры [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). Вторая форма `Unlock` редко применяется к multilock ситуациях.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




