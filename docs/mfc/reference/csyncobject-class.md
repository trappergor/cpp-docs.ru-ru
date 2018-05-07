---
title: Класс CSyncObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1712f0d26fc0d9ac3dcfb0f2a15a906351f43154
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csyncobject-class"></a>Класс CSyncObject
Чисто виртуальный класс, обеспечивающий общую функциональность объектов синхронизации Win32.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Участники  
  
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
|[CSyncObject::m_hObject](#m_hobject)|Дескриптор для базового объекта синхронизации.|  
  
## <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation предоставляет несколько классов, производных от `CSyncObject`. Это [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), и [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Сведения о том, как использовать объекты синхронизации, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="csyncobject"></a>  CSyncObject::CSyncObject  
 Создает объект синхронизации, с указанным именем.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Параметры  
 `pstrName`  
 Имя объекта. Если **NULL**, *pstrName* будет иметь значение null.  
  
##  <a name="lock"></a>  CSyncObject::Lock  
 Эта функция вызывается для доступа к ресурсу, управляются объектом синхронизации.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTimeout`  
 Указывает количество времени в миллисекундах для ожидания объекта синхронизации доступны (сигнал). Если **БЕСКОНЕЧНЫЙ**, `Lock` ожидает сигнала перед возвращением объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если объект синхронизации, получает сигнал, `Lock` возвратит успешно и поток теперь принадлежит объект. Если объект синхронизации является несигнальным (недоступна), `Lock` ожидает объекта синхронизации в сигнальное вплоть до указанного числа миллисекунд в *dwTimeOut* параметра. Если объект синхронизации не был отправлен сигнал за указанный период времени, `Lock` возвращает сбой.  
  
##  <a name="m_hobject"></a>  CSyncObject::m_hObject  
 Дескриптор для базового объекта синхронизации.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>  CSyncObject::operator ДЕСКРИПТОРА  
 Этот оператор используется для получения дескриптора `CSyncObject` объекта.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения, дескриптор объекта синхронизации; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.  
  
##  <a name="unlock"></a>  CSyncObject::Unlock  
 Объявление `Unlock` без параметров является чистой виртуальной функции и должны быть переопределены все классы, производные от `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Не используется реализация по умолчанию.  
  
 `lpPrevCount`  
 Не используется реализация по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию всегда возвращает **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию объявления с двумя параметрами всегда возвращает **TRUE**. Эта функция вызывается для предоставления доступа к объект синхронизации, принадлежащих вызывающему потоку. Второе объявление предоставляется для объекта синхронизации, например, семафоры, позволяющих более одного доступ к контролируемому ресурсу.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



