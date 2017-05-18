---
title: "Класс CSemaphore | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 811510bab51ab7909b90b52247d34b71dda5b961
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="csemaphore-class"></a>Класс CSemaphore
Объект класса `CSemaphore` представляет «семафор» — объект синхронизации, позволяющий ограниченному числу потоков в один или несколько процессов, чтобы получить доступ к сохраняет число потоков в настоящее время осуществляют доступ к заданному ресурсу.  
  
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
 Семафоры полезны для управления доступом к общим ресурсом и поддерживает только ограниченное число пользователей. Текущее число используемых `CSemaphore` объект — количество дополнительных пользователей. Когда значение счетчика достигнет нуля, все попытки использовать ресурс, контролируются **CSemaphore** объект будет вставлен в системной очереди и подождите, пока они либо времени ожидания, или значение счетчика превышает 0. Максимальное число пользователей, обращающихся к управляемому ресурсу одновременно задан во время создания `CSemaphore` объекта.  
  
 Для использования **CSemaphore** объектов, создания `CSemaphore` объекта, когда он необходим. Укажите имя для ожидания семафора, а приложения должны изначально принадлежит вам. Теперь можно получить доступ к семафора при возврате в конструктор. Вызовите [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) после доступа к управляемому ресурсу.  
  
 Альтернативный метод с помощью `CSemaphore` объектов является добавление переменной типа `CSemaphore` как элемент данных, к классу, для управления. При создании управляемого объекта, вызывает конструктор `CSemaphore` указания начального члена данных доступ к count, счетчик максимальное доступа, имя семафор (если он будет использоваться разными процессами) и требуемого атрибуты безопасности.  
  
 Для доступа к ресурсам, которые управляются `CSemaphore` объектов таким образом, сначала создайте переменную любого из этих типов [класс CSingleLock](../../mfc/reference/csinglelock-class.md) или тип [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции-члене доступ к ресурсу. Затем вызовите объект блокировки `Lock` функции-члена (например, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). На этом этапе поток будет либо получить доступ к ресурсу, подождите, пока ресурс освобождается и получить доступ или дождитесь ресурс освобождается и времени ожидания, невозможности получить доступ к ресурсу. В любом случае ресурс осуществлялся в потокобезопасным способом. Для освобождения ресурса, используйте объект блокировки `Unlock` функции-члена (например, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), или разрешить объект блокировки, выходит из области действия.  
  
 Кроме того, можно создать **CSemaphore** объекта автономного и доступ к ней явным образом перед попыткой обращения к управляемому ресурсу. Этот метод при яснее кому-либо чтение исходный код, может произойти ошибка.  
  
 Дополнительные сведения об использовании **CSemaphore** объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="csemaphore"></a>CSemaphore::CSemaphore  
 Создает именованный или неименованный `CSemaphore` объекта.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lInitialCount*  
 Счетчик начальной использования семафора. Должен быть больше или равно 0 и меньше или равно `lMaxCount`.  
  
 `lMaxCount`  
 Максимальное использование счетчика семафора. Должно быть больше 0.  
  
 `pstrName`  
 Имя семафора. Необходимо указать, если семафора будет осуществляться через границы процессов. Если `NULL`, объект будет без имени. Если имя соответствует существующей semaphore, конструктор создает новый `CSemaphore` объект, который ссылается семафор с тем же именем. Если имя соответствует объект синхронизации, не семафор, построения завершится ошибкой.  
  
 *lpsaAttributes*  
 Атрибуты безопасности для объекта семафора. Полное описание этой структуры см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Для доступа или освободить `CSemaphore` объектов, создания [CMultiLock](../../mfc/reference/cmultilock-class.md) или [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены.  
  
> [!IMPORTANT]
>  После создания `CSemaphore` , используйте [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) чтобы убедиться, что объект взаимного исключения еще не существует. Если мьютекс существовал неожиданно, это может означать незаконных процесс занятие и может вы собираетесь использовать семафор злоумышленником. В этом случае соображениям безопасности рекомендуется закрыть этот дескриптор и продолжить как, если произошел сбой при создании объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




