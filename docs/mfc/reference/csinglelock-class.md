---
title: Класс класс CSingleLock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 1ae72b7c9c2acf4fa8600903061869ba049cd58c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csinglelock-class"></a>Класс CSingleLock класса
Класс представляет механизм контроля доступа к определенному ресурсу в многопоточных программах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Создает объект `CSingleLock`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Определяет, если этот объект заблокирован.|  
|[CSingleLock::Lock](#lock)|Ожидает объекта синхронизации.|  
|[CSingleLock::Unlock](#unlock)|Освобождает объект синхронизации.|  
  
## <a name="remarks"></a>Примечания  
 `CSingleLock` не имеет базового класса.  
  
 Для использования классов синхронизации [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CEvent](../../mfc/reference/cevent-class.md), необходимо создать либо `CSingleLock` или [CMultiLock](../../mfc/reference/cmultilock-class.md) объект для ожидания и освобождения объекта синхронизации. Используйте `CSingleLock` при требуется только для одного объекта во время ожидания. Используйте **CMultiLock** при наличии нескольких объектов, которые можно использовать в конкретный момент времени.  
  
 Для использования `CSingleLock` объекта, вызовите его конструктор внутри функции-члена в классе управляемого ресурса. Затем вызовите [IsLocked](#islocked) функции-члена для определения доступности ресурса. Если Да, продолжите остальная часть функции-члена. Если ресурс недоступен, подождите на определенное время для освобождения ресурса или возвращена ошибка. После завершения использования ресурса вызвать [Unlock](#unlock) функционировать, если `CSingleLock` должен использоваться повторно, либо разрешить `CSingleLock` объекта будут уничтожены.  
  
 `CSingleLock` объекты требуют наличия объект, производный от [CSyncObject](../../mfc/reference/csyncobject-class.md). Это обычно элемент данных класса управляемых ресурсов. Дополнительные сведения об использовании `CSingleLock` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CSingleLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="csinglelock"></a>  CSingleLock::CSingleLock  
 Создает объект `CSingleLock`.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `pObject`  
 Указывает объект синхронизации должен быть предоставлен доступ. Не может быть **NULL**.  
  
 `bInitialLock`  
 Указывает необходимость сначала пытаются получить доступ к предоставленным объектом.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается из функции-члена доступа управляемого ресурса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>  CSingleLock::IsLocked  
 Определяет, если объект, связанный с `CSingleLock` объекта несигнальное (недоступно).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект заблокирован; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>  CSingleLock::Lock  
 Эта функция вызывается для доступа к ресурсу, контролируются объекта синхронизации, предоставляемого `CSingleLock` конструктор.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 *dwTimeOut*  
 Указывает время ожидания для объекта синхронизации доступны (сигнал). Если **БЕСКОНЕЧНЫЙ**, `Lock` ожидает сигнала перед возвращением объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если объект синхронизации, получает сигнал, `Lock` возвратит успешно и поток теперь принадлежит объект. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметра. Если объект синхронизации не был отправлен сигнал за указанный период времени, `Lock` возвращает сбой.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>  CSingleLock::Unlock  
 Освобождает объект синхронизации, принадлежащих `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Число обращений к выпуска. Должно быть больше 0. Если указанное приводит число объектов превышает максимальный, счетчик не изменяется, и функция возвращает **FALSE**.  
  
 `lPrevCount`  
 Указывает на переменную для получения предыдущее количество в семафоре объекта синхронизации. Если **NULL**, последнее значение счетчика не возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается `CSingleLock`деструктор.  
  
 Если необходимо освободить несколько доступа счетчик семафора, используйте второй формы `Unlock` и указать количество обращений к выпуска.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMultiLock](../../mfc/reference/cmultilock-class.md)
