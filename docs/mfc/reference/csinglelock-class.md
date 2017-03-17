---
title: "Класс класс CSingleLock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock class
- threading [MFC], access control
- synchronization objects, access control
- threading [MFC], synchronization
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
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
ms.openlocfilehash: b1efc2daf1c3714446223cc69f9cc2a6a3401173
ms.lasthandoff: 02/24/2017

---
# <a name="csinglelock-class"></a>Класс CSingleLock класса
Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Создает объект `CSingleLock`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Определяет объект заблокирован.|  
|[CSingleLock::Lock](#lock)|Ожидает объекта синхронизации.|  
|[CSingleLock::Unlock](#unlock)|Освобождает объект синхронизации.|  
  
## <a name="remarks"></a>Примечания  
 `CSingleLock`не имеет базового класса.  
  
 Чтобы использовать классы синхронизации [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CEvent](../../mfc/reference/cevent-class.md), необходимо создать либо `CSingleLock` или [CMultiLock](../../mfc/reference/cmultilock-class.md) объект для ожидания и освободить объект синхронизации. Использование `CSingleLock` при достаточно ожидает один объект за раз. Используйте **CMultiLock** при наличии нескольких объектов, которые можно использовать в конкретный момент времени.  
  
 Для использования `CSingleLock` объекта, вызывается его конструктор внутри функции-члена в классе управляемый ресурс. Затем вызовите [IsLocked](#islocked) функции-члена для определения доступности ресурса. Если это так, продолжите остальная часть функции-члена. Если ресурс недоступен, подождите на определенное время для освобождения ресурса или сбой запроса. После завершения использования ресурсов, либо вызовите [Unlock](#unlock) работать, если `CSingleLock` должен использоваться повторно, или разрешить `CSingleLock` объект будет уничтожен.  
  
 `CSingleLock`объекты требуют наличия объект, производный от [CSyncObject](../../mfc/reference/csyncobject-class.md). Обычно это члена данных класса управляемый ресурс. Дополнительные сведения об использовании `CSingleLock` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CSingleLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="csinglelock"></a>CSingleLock::CSingleLock  
 Создает объект `CSingleLock`.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указывает объект синхронизации должен осуществляться. Не может быть **NULL**.  
  
 `bInitialLock`  
 Указывает, следует сначала пытаются получить доступ к предоставленным объектом.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается из функции-члена доступа управляемого ресурса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&19;](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>CSingleLock::IsLocked  
 Определяет объект, связанной с `CSingleLock` объекта несигнальное (недоступно).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект заблокирован; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&20;](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>CSingleLock::Lock  
 Эта функция вызывается для доступа к ресурсу, контролируются синхронизации объекта, предоставляемого `CSingleLock` конструктор.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 *dwTimeOut*  
 Указывает время ожидания для объекта синхронизации доступны (сигнал). Если **БЕСКОНЕЧНЫЙ**, `Lock` будет ждать перед возвратом оповещении объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если объект синхронизации, получает сигнал, `Lock` успешного возвращения и поток теперь принадлежит объект. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметр. Если объект синхронизации не был отправлен сигнал в заданного количества времени, `Lock` возвращает сбой.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>CSingleLock::Unlock  
 Освобождает объект синхронизации, принадлежащий `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Количество обращений к выпуска. Должно быть больше 0. Если указанное вызовет число объектов превышает максимальное значение, значение счетчика не изменяются, и функция возвращает **FALSE**.  
  
 `lPrevCount`  
 Указывает на переменную для получения предыдущих число объекта синхронизации. Если **NULL**, предыдущее количество не возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается `CSingleLock`деструктор.  
  
 Если необходимо освободить несколько доступа счетчик семафора, используйте второй формы `Unlock` и указать количество обращений к выпуска.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&#21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMultiLock](../../mfc/reference/cmultilock-class.md)

