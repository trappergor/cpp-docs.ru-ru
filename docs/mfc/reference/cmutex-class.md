---
title: "Класс CMutex | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex class
- synchronization classes, CMutex class
- synchronization objects, mutex
- mutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
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
ms.openlocfilehash: 159f2e02dfe44d74ebcaad687a23cef734b61fc9
ms.lasthandoff: 02/24/2017

---
# <a name="cmutex-class"></a>Класс CMutex
Класс представляет мьютекс «» — объект синхронизации, позволяющий один поток взаимоисключающими доступ к ресурсу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Создает объект `CMutex`.|  
  
## <a name="remarks"></a>Примечания  
 Мьютексы полезны в тех случаях, когда только один поток за раз будет разрешено изменять данные или другой управляемый ресурс. Например добавление узлов связанного списка — это процесс, следует разрешать только одним потоком одновременно. С помощью `CMutex` объекта для управления связанному списку, только один поток за раз можно получить доступ к списку.  
  
 Для использования `CMutex` объекта, создания `CMutex` объекта, когда он нужен. Укажите имя мьютекса, вы хотите Ожидание и приложения должны изначально он принадлежит. После завершения работы конструктор возвращает, может связываться мьютекса. Вызов [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) после доступа к управляемому ресурсу.  
  
 Альтернативный метод с помощью `CMutex` объектов является добавление переменной типа `CMutex` как данные-член класса для элемента управления. Во время создания управляемого объекта, вызовите конструктор `CMutex` элемент данных, указав Если мьютекс изначально принадлежит, имя мьютекса (если он будет использоваться через границы процессов) и требуемой атрибуты безопасности.  
  
 Для доступа к ресурсам, которые управляются `CMutex` объектов таким образом, сначала создайте переменную любого типа [класс CSingleLock](../../mfc/reference/csinglelock-class.md) или [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции-члене доступ к ресурсу. Затем вызовите объект блокировки `Lock` функции-члена (например, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). На этом этапе потока будет либо получить доступ к ресурсу, дождитесь, пока ресурс освобождается и получить доступ или подождите ресурсов, которые будут выпущены и время ожидания, невозможности получить доступ к ресурсу. В любом случае ресурс осуществлялся в потокобезопасным способом. Чтобы освободить ресурс, используйте объект блокировки `Unlock` функции-члена (например, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), или разрешить объект блокировки, выходит из области действия.  
  
 Дополнительные сведения об использовании `CMutex` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="cmutex"></a>CMutex::CMutex  
 Создает именованные `CMutex` объекта.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bInitiallyOwn`  
 Указывает, если создание потока `CMutex` объект изначально имеет доступ к ресурсу, контролируются мьютекса.  
  
 `lpszName`  
 Имя объекта `CMutex`. Если существует другой мьютекс с тем же именем, `lpszName` должен указываться, если объект будет использоваться через границы процессов. Если **NULL**, объект взаимного исключения будут без имени. Если имя соответствует существующей мьютекс, конструктор создает новый `CMutex` объект, который ссылается на объект взаимного исключения с этим именем. Если имя соответствует объект синхронизации, не является мьютексом, построение завершится ошибкой.  
  
 `lpsaAttribute`  
 Атрибуты безопасности для объекта mutex. Полное описание этой структуры см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Доступ или выпуска `CMutex` объекта, создайте [CMultiLock](../../mfc/reference/cmultilock-class.md) или [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены. Если `CMutex` объекта используется автономный, вызвать его `Unlock` функции-члена для его освобождения.  
  
> [!IMPORTANT]
>  После создания `CMutex` , используйте [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) чтобы убедиться, что объект взаимного исключения еще не существует. Если мьютекс существовал неожиданно, это может означать нелегальные процессы — занятие и может вы собираетесь использовать мьютекса злоумышленником. В этом случае соображениям безопасности рекомендуется закрыть дескриптор и продолжается как, если произошел сбой при создании объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




