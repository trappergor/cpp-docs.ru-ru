---
title: "Класс CSemaphore | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, semaphores
- CSemaphore class
- semaphores
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
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
ms.openlocfilehash: 31de1e553ea2facea6b70c284aecdbf10e22c89f
ms.lasthandoff: 02/24/2017

---
# <a name="csemaphore-class"></a>Класс CSemaphore
Объект класса `CSemaphore` представляет «семафор» — объект синхронизации, позволяющий ограниченному числу потоков в один или несколько процессов, для доступа к сохраняет число потоков, которые в настоящее время доступа к заданному ресурсу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|Создает объект `CSemaphore`.|  
  
## <a name="remarks"></a>Примечания  
 Семафоры полезны при управлении доступом к общему ресурсу, который поддерживает только ограниченное число пользователей. Текущее количество `CSemaphore` объекта — количество дополнительных пользователей. Значение счетчика достигнет нуля, все попытки использовать ресурс, контролируются **CSemaphore** объект будет вставлен в системной очереди и дождитесь, пока они либо времени ожидания или значение счетчика превышает 0. Максимальное число пользователей, которым разрешен доступ к управляемому ресурсу одновременно указывается во время создания `CSemaphore` объекта.  
  
 Для использования **CSemaphore** объекта, создания `CSemaphore` объекта, когда он нужен. Укажите имя для ожидания семафора и приложения должны изначально он принадлежит. После завершения работы конструктор возвращает, может связываться семафора. Вызов [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) после доступа к управляемому ресурсу.  
  
 Альтернативный метод с помощью `CSemaphore` объектов является добавление переменной типа `CSemaphore` как данные-член класса для элемента управления. Во время создания управляемого объекта, вызовите конструктор `CSemaphore` элемент данных, указав первоначального доступа число, счетчик максимального доступа, именем семафора (если он будет использоваться через границы процессов) и требуемой атрибуты безопасности.  
  
 Для доступа к ресурсам, которые управляются `CSemaphore` объектов таким образом, сначала создайте переменную любого типа [класс CSingleLock](../../mfc/reference/csinglelock-class.md) или [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции-члене доступ к ресурсу. Затем вызовите объект блокировки `Lock` функции-члена (например, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). На этом этапе потока будет либо получить доступ к ресурсу, дождитесь, пока ресурс освобождается и получить доступ или подождите ресурсов, которые будут выпущены и время ожидания, невозможности получить доступ к ресурсу. В любом случае ресурс осуществлялся в потокобезопасным способом. Чтобы освободить ресурс, используйте объект блокировки `Unlock` функции-члена (например, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), или разрешить объект блокировки, выходит из области действия.  
  
 Кроме того, можно создать **CSemaphore** объекта автономного и доступ к ней явным образом перед попыткой доступа к управляемому ресурсу. Этот метод при яснее другому чтение исходного кода, подвержены ошибкам.  
  
 Дополнительные сведения об использовании **CSemaphore** объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="a-namecsemaphorea--csemaphorecsemaphore"></a><a name="csemaphore"></a>CSemaphore::CSemaphore  
 Создает именованные `CSemaphore` объекта.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lInitialCount*  
 Счетчик начальной использования семафора. Должно быть больше или равно 0 и меньше или равно `lMaxCount`.  
  
 `lMaxCount`  
 Максимально эффективное использование счетчик семафора. Должно быть больше 0.  
  
 `pstrName`  
 Имя семафора. Должен быть указан, если семафора будет осуществляться через границы процессов. Если `NULL,` объект будет без имени. Если имя соответствует существующей семафора, конструктор создает новый `CSemaphore` объекта, на который ссылается данное имя семафором. Если имя соответствует объект синхронизации, не семафор, построение завершится ошибкой.  
  
 *lpsaAttributes*  
 Атрибуты безопасности для объекта семафора. Полное описание этой структуры см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Доступ или выпуска `CSemaphore` объекта, создайте [CMultiLock](../../mfc/reference/cmultilock-class.md) или [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены.  
  
> [!IMPORTANT]
>  После создания `CSemaphore` , используйте [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) чтобы убедиться, что объект взаимного исключения еще не существует. Если мьютекс существовал неожиданно, это может означать нелегальные процессы — занятие и может вы собираетесь использовать мьютекса злоумышленником. В этом случае соображениям безопасности рекомендуется закрыть дескриптор и продолжается как, если произошел сбой при создании объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




