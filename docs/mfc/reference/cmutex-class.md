---
title: Класс CMutex | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3bde85e64fe8593ec2637e767e8c3c70d3b8200
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038081"
---
# <a name="cmutex-class"></a>Класс CMutex
Представляет «семафор» — объект синхронизации, позволяющий один поток взаимно исключают друг друга доступ к ресурсу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Создает объект `CMutex`.|  
  
## <a name="remarks"></a>Примечания  
 Мьютексы полезны в тех случаях, когда только одному потоку за раз можно разрешается изменять данные или другой управляемый ресурс. Например добавление узлов в связанный список — это процесс, может только по одному потоку за раз. С помощью `CMutex` объекта с целью управления связанного списка только одному потоку за раз можно получить доступ к списку.  
  
 Для использования `CMutex` объектов, создания `CMutex` объекта, когда он необходим. Укажите имя для ожидания семафора, а приложения должны изначально принадлежит вам. Можно затем получить объект взаимного исключения при возврате в конструктор. Вызовите [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) после доступа к управляемому ресурсу.  
  
 Альтернативный метод с помощью `CMutex` объектов является добавление переменной типа `CMutex` как элемент данных, к классу, для управления. При создании управляемого объекта, вызывает конструктор `CMutex` элемент данных, если мьютекс изначально имеет владельца, имя мьютекс (если он будет использоваться разными процессами), и требуемого атрибуты безопасности.  
  
 Для доступа к ресурсам, которые управляются `CMutex` объектов таким образом, сначала создайте переменную любого из этих типов [класс CSingleLock](../../mfc/reference/csinglelock-class.md) или тип [CMultiLock](../../mfc/reference/cmultilock-class.md) в функции-члене доступ к ресурсу. Затем вызовите объект блокировки `Lock` функции-члена (например, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). На этом этапе поток будет либо получить доступ к ресурсу, подождите, пока ресурс освобождается и получить доступ или дождитесь ресурс освобождается и времени ожидания, невозможности получить доступ к ресурсу. В любом случае ресурс осуществлялся в потокобезопасным способом. Для освобождения ресурса, используйте объект блокировки `Unlock` функции-члена (например, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), или разрешить объект блокировки, выходит из области действия.  
  
 Дополнительные сведения об использовании `CMutex` объектов, см. в статье [Многопоточность: использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmt.h  
  
##  <a name="cmutex"></a>  CMutex::CMutex  
 Создает именованный или неименованный `CMutex` объекта.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *bInitiallyOwn*  
 Указывает, если создание потока `CMutex` объект изначально имеет доступ к ресурсу, контролируются мьютекса.  
  
 *lpszName*  
 Имя объекта `CMutex`. Если существует другой мьютекс с тем же именем, *lpszName* необходимо указать, будет ли использоваться объекта через границы процессов. Если **NULL**, объект взаимного исключения будут без имени. Если имя соответствует существующей mutex, конструктор создает новый `CMutex` объект, который ссылается на объект взаимного исключения с тем же именем. Если имя соответствует объект синхронизации, не мьютекс, построения завершится ошибкой.  
  
 *lpsaAttribute*  
 Атрибуты безопасности для объекта mutex. Полное описание этой структуры см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Для доступа или освободить `CMutex` объектов, создания [CMultiLock](../../mfc/reference/cmultilock-class.md) или [класс CSingleLock](../../mfc/reference/csinglelock-class.md) и вызовите его [блокировки](../../mfc/reference/csinglelock-class.md#lock) и [Unlock](../../mfc/reference/csinglelock-class.md#unlock) функции-члены. Если `CMutex` используется объект автономного, вызовите его `Unlock` функции-члена для его освобождения.  
  
> [!IMPORTANT]
>  После создания `CMutex` , используйте [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) чтобы убедиться, что объект взаимного исключения еще не существует. Если мьютекс существовал неожиданно, это может означать незаконных процесс занятие и может вы собираетесь использовать семафор злоумышленником. В этом случае соображениям безопасности рекомендуется закрыть этот дескриптор и продолжить как, если произошел сбой при создании объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CSyncObject](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



