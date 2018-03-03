---
title: "Класс CCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
dev_langs:
- C++
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16364843ca5d85181b84e56f56b43ca4856a1667
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccriticalsection-class"></a>Класс CCriticalSection
Представляет «критическую секцию» — объект синхронизации, позволяющий одному потоку за раз, чтобы получить доступ к определенному фрагменту кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Создает объект `CCriticalSection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|Использовать для получения доступа к `CCriticalSection` объекта.|  
|[CCriticalSection::Unlock](#unlock)|Освобождает объект `CCriticalSection`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Извлекает указатель на внутренний **CRITICAL_SECTION** объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|Объект **CRITICAL_SECTION** объекта.|  
  
## <a name="remarks"></a>Примечания  
 Критические разделы полезны в тех случаях, когда только одному потоку за раз можно разрешается изменять данные или другой управляемый ресурс. Например добавление узлов в связанный список — это процесс, может только по одному потоку за раз. С помощью `CCriticalSection` объекта с целью управления связанного списка только одному потоку за раз можно получить доступ к списку.  
  
> [!NOTE]
>  Функциональные возможности `CCriticalSection` предоставляет класс фактическое Win32 **CRITICAL_SECTION** объекта.  
  
 Критические секции используются вместо мьютексы (см. [CMutex](../../mfc/reference/cmutex-class.md)) когда скорость имеет большое значение и ресурс не будет использоваться через границы процессов.  
  
 Существует два способа использования `CCriticalSection` объект: изолированное и внедренное в классе.  
  
-   Изолированный метод для использования изолированного `CCriticalSection` объектов, создания `CCriticalSection` объекта, когда он необходим. После успешного возвращения из конструктора, явно блокировать объект с помощью вызова [блокировки](#lock). Вызовите [Unlock](#unlock) после доступ к критической секции. Этот метод при яснее кому-либо чтение исходный код вероятность возникновения ошибки, необходимо помнить, блокировать и разблокировать критический раздел до и после доступа.  
  
     Более предпочтительным методом является использование [класс CSingleLock](../../mfc/reference/csinglelock-class.md) класса. Он также имеет `Lock` и `Unlock` метода, но не нужно беспокоиться о разблокировании ресурс при возникновении исключения.  
  
-   Внедренный метод, вы можете использовать класс с несколькими потоками, добавив `CCriticalSection`-член данных типа к классу и блокировка элемента данных, если это требуется.  
  
 Дополнительные сведения об использовании `CCriticalSection` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 Создает объект `CCriticalSection`.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Примечания  
 Для доступа или освободить `CCriticalSection` объектов, создания [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены. Если `CCriticalSection` используется объект автономного, вызовите его [Unlock](#unlock) функции-члена для его освобождения.  
  
 Если конструктор не удается выделить память необходимые системные, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически создается исключение.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CCriticalSection::Lock](#lock).  
  
##  <a name="lock"></a>CCriticalSection::Lock  
 Вызовите эту функцию-член для получения доступа к объект критической секции.  
  
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
 `Lock`является блокирующий вызов, который будет выполнен после возврата сигнал объект критической секции (становится доступной).  
  
 При необходимости времени ожидания, можно использовать [CMutex](../../mfc/reference/cmutex-class.md) объекта вместо `CCriticalSection` объекта.  
  
 Если `Lock` не удается выделить память необходимые системные, исключение памяти (типа [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) автоматически создается исключение.  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется вложенных критического раздела с помощью управления доступом к общему ресурсу (статический `_strShared` объекта) с помощью общего `CCriticalSection` объекта. `SomeMethod` Функция показывает обновление общего ресурса в безопасном режиме.  
  
 [!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>CCriticalSection::m_sect  
 Содержит объект критической секции, который используется всеми `CCriticalSection` методы.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 Извлекает **CRITICAL_SECTION** объекта.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы получить указатель на внутренний **CRITICAL_SECTION** объекта.  
  
##  <a name="unlock"></a>CCriticalSection::Unlock  
 Выпуски `CCriticalSection` объекта для использования в другом потоке.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CCriticalSection` поток был владельцем объекта и выпуска выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `CCriticalSection` , используется изолированное, `Unlock` должен вызываться сразу после завершения работы использование ресурса, контролируются критической секции. Если [класс CSingleLock](../../mfc/reference/csinglelock-class.md) используется объект, `CCriticalSection::Unlock` будут вызваны объект блокировки `Unlock` функции-члена.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMutex](../../mfc/reference/cmutex-class.md)
