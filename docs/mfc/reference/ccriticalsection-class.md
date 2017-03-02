---
title: "Класс CCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, critical section
- CCriticalSection class
- critical sections
- synchronization classes, CCriticalSection class
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
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
ms.openlocfilehash: 25d4b124d089441503e9cb457e648695fc54660d
ms.lasthandoff: 02/24/2017

---
# <a name="ccriticalsection-class"></a>Класс CCriticalSection
Представляет «критическую секцию» — объект синхронизации, позволяющий одному потоку одновременно получить доступ к определенному фрагменту кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Создает объект `CCriticalSection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|Для получения доступа к `CCriticalSection` объекта.|  
|[CCriticalSection::Unlock](#unlock)|Освобождает объект `CCriticalSection`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Извлекает указатель на внутренний **CRITICAL_SECTION** объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|Объект **CRITICAL_SECTION** объекта.|  
  
## <a name="remarks"></a>Примечания  
 Критические разделы полезны в тех случаях, когда только один поток за раз будет разрешено изменять данные или другой управляемый ресурс. Например добавление узлов связанного списка — это процесс, следует разрешать только одним потоком одновременно. С помощью `CCriticalSection` объекта для управления связанному списку, только один поток за раз можно получить доступ к списку.  
  
> [!NOTE]
>  Функциональные возможности `CCriticalSection` класса обеспечивается фактическое Win32 **CRITICAL_SECTION** объекта.  
  
 Критические разделы используются вместо мьютексы (см. [CMutex](../../mfc/reference/cmutex-class.md)) когда важна скорость и ресурс не будет использоваться через границы процессов.  
  
 Существует два метода для использования `CCriticalSection` объект: изолированное и внедренное в классе.  
  
-   Автономный метод для автономного использования `CCriticalSection` объекта, создания `CCriticalSection` объекта, когда он нужен. После успешного возвращения из конструктора явно заблокировать объект с помощью вызова [блокировки](#lock). Вызов [Unlock](#unlock) после доступа к критической секции. Этот метод при яснее другому чтение исходный код, вероятность возникновения ошибки, необходимо помнить, блокировать и разблокировать критический раздел до и после доступа.  
  
     Более предпочтительным методом является использование [класс CSingleLock](../../mfc/reference/csinglelock-class.md) класса. Он также имеет `Lock` и `Unlock` метода, но не нужно беспокоиться о разблокировании ресурсов при возникновении исключения.  
  
-   Внедренные можно также предоставить класс несколько потоков, добавив метод `CCriticalSection`-члена данных типа к классу и блокировка элемента данных, при необходимости.  
  
 Дополнительные сведения об использовании `CCriticalSection` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="a-nameccriticalsectiona--ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 Создает объект `CCriticalSection`.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Доступ или выпуска `CCriticalSection` объекта, создайте [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены. Если `CCriticalSection` объекта используется автономный, вызвать его [Unlock](#unlock) функции-члена для его освобождения.  
  
 Если конструктор не удается выделить память требуемой системы, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически вызывается исключение.  
  
### <a name="example"></a>Пример  
  В примере показано [CCriticalSection::Lock](#lock).  
  
##  <a name="a-namelocka--ccriticalsectionlock"></a><a name="lock"></a>CCriticalSection::Lock  
 Вызов этой функции-члена для доступа к объекту критический раздел.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTimeout`  
 `Lock`игнорирует значение этого параметра.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `Lock`является блокирующий вызов, который не возвращает значение до сигнал объект критической секции (доступна).  
  
 При необходимости времени ожидания, можно использовать [CMutex](../../mfc/reference/cmutex-class.md) вместо объекта `CCriticalSection` объекта.  
  
 Если `Lock` не удается выделить память необходимые системные, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически вызывается исключение.  
  
### <a name="example"></a>Пример  
 В этом примере показано вложенных критического раздела с помощью управления доступом к общему ресурсу (статический `_strShared` объекта) с помощью общего `CCriticalSection` объекта. `SomeMethod` Функция показано обновление общего ресурса в безопасном режиме.  
  
 [!code-cpp[NVC_MFC_Utilities&11;](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="a-namemsecta--ccriticalsectionmsect"></a><a name="m_sect"></a>CCriticalSection::m_sect  
 Содержит объект критической секции, который используется всеми `CCriticalSection` методы.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="a-nameoperatorcriticalsectionstara--ccriticalsectionoperator-criticalsection"></a><a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 Извлекает **CRITICAL_SECTION** объекта.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения указатель на внутренний **CRITICAL_SECTION** объекта.  
  
##  <a name="a-nameunlocka--ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Unlock  
 Выпуски `CCriticalSection` объекта для использования другим потоком.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CCriticalSection` поток был владельцем объекта и выпуска была успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `CCriticalSection` используется автономный, `Unlock` должен вызываться сразу же после завершения использования ресурсов, контролируются критический раздел. Если [класс CSingleLock](../../mfc/reference/csinglelock-class.md) используется объект, `CCriticalSection::Unlock` будет вызываться объект блокировки `Unlock` функции-члена.  
  
### <a name="example"></a>Пример  
  В примере показано [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMutex](../../mfc/reference/cmutex-class.md)

