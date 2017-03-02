---
title: "Определения типов ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: aa57212b602538e4e8d2854c6075562e72472796
ms.lasthandoff: 02/24/2017

---
# <a name="atl-typedefs"></a>Определения типов ATL
Active Template Library включает в себя следующие определения типов.  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|Определяется как typedef, на основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).|  
|[_ATL_COM_MODULE](#_atl_com_module)|Определяется как typedef, на основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).|  
|[_ATL_MODULE](#_atl_module)|Определяется как typedef, на основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).|  
|[_ATL_WIN_MODULE](#_atl_win_module)|Определяется как typedef, на основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|Тип, используемый [CUrl](../../atl/reference/curl-class.md) для указания номера порта.|  
|[CComDispatchDriver](#ccomdispatchdriver)|Этот класс управляет указателей интерфейса СОМ.|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|Вызывает методы модели, независимо от того, потоковую модель, соответствующем потоке.|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|Вызывает методы модели, независимо от того, потоковую модель, соответствующем потоке.|  
|[CContainedWindow](#ccontainedwindow)|Этот класс является специализацией **CContainedWindowT.**|  
|[CPath](#cpath)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CString`.|  
|[CPathA](#cpatha)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringA`.|  
|[CPathW](#cpathw)|Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringW`.|  
|[CSimpleValArray](#csimplevalarray)|Представляет массив для хранения простых типов.|  
|[DefaultThreadTraits](#defaultthreadtraits)|Класс характеристик потока по умолчанию.|  
|[LPCURL](#lpcurl)|Указатель на константу [CUrl](../../atl/reference/curl-class.md) объекта.|  
|[LPURL](#lpurl)|Указатель на [CUrl](../../atl/reference/curl-class.md) объекта.|  
  
##  <a name="a-nameatlbasemodulea--atlbasemodule"></a><a name="_atl_base_module"></a>_ATL_BASE_MODULE  
 Определен как на _ATL_BASE_MODULE70 основе typedef.  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>Примечания  
 Используется в каждом проекте ATL. На основе [_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md).  
  
 Классы, которые являются частью модульные классы ATL 7.0 являются производными от структуры _ATL_BASE_MODULE.  Дополнительные сведения о модульные классы ATL см. [классы COM модулей](../../atl/com-modules-classes.md).  
  
##  <a name="a-nameatlcommodulea--atlcommodule"></a><a name="_atl_com_module"></a>_ATL_COM_MODULE  
 Определен как на _ATL_COM_MODULE70 основе typedef.  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>Примечания  
 Используемые проекты ATL, которые используют COM-компонентов. На основе [_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md).  
  
##  <a name="a-nameatlmodulea--atlmodule"></a><a name="_atl_module"></a>_ATL_MODULE  
 Определен как на _ATL_MODULE70 основе typedef.  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
  
### <a name="remarks"></a>Примечания  
 На основе [_ATL_MODULE70](../../atl/reference/atl-module70-structure.md).  
  
##  <a name="a-nameatlwinmodulea--atlwinmodule"></a><a name="_atl_win_module"></a>_ATL_WIN_MODULE  
 Определен как на _ATL_WIN_MODULE70 основе typedef.  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>Примечания  
 Используются все проекты ATL, использующие оконные функции. На основе [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md).  
  
##  <a name="a-nameatlurlporta--atlurlport"></a><a name="atl_url_port"></a>ATL_URL_PORT 
  Тип, используемый [CUrl](curl-class.md) для указания номера порта.
```  
typedef WORD ATL_URL_PORT;
```  

##  <a name="a-nameccomdispatchdrivera--ccomdispatchdriver"></a><a name="ccomdispatchdriver"></a>CComDispatchDriver  
 Этот класс управляет указателей интерфейса СОМ.  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
  
##  <a name="a-nameccomglobalsthreadmodela--ccomglobalsthreadmodel"></a><a name="ccomglobalsthreadmodel"></a>CComGlobalsThreadModel  
 Вызывает методы модели, независимо от того, потоковую модель, соответствующем потоке.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Примечания  
 В зависимости от модели потоков, используемых приложением `typedef` имя `CComGlobalsThreadModel` ссылается либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имена для ссылки на класс критический раздел.  
  
> [!NOTE]
> `CComGlobalsThreadModel`не ссылается на класс [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 С помощью `CComGlobalsThreadModel` избавляет от необходимости указывать определенный класс потоковой модели. Независимо от того, используется модель потоков вызываются соответствующие методы.  
  
 В дополнение к `CComGlobalsThreadModel`, библиотека ATL предоставляет `typedef` имя [CComObjectThreadModel](#ccomobjectthreadmodel). Ссылаться на каждый класс `typedef` зависит потоковую модель, как показано в следующей таблице:  
  
|typedef|Последовательная обработка|Потоковое|Свободных потоков|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|С|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Используйте `CComObjectThreadModel` в пределах одного объекта класса. Используйте `CComGlobalsThreadModel` в объекте это глобально доступные для программы, или если требуется защитить ресурсы модуля в нескольких потоках.  
  
##  <a name="a-nameccomobjectthreadmodela--ccomobjectthreadmodel"></a><a name="ccomobjectthreadmodel"></a>CComObjectThreadModel  
 Вызывает методы модели, независимо от того, потоковую модель, соответствующем потоке.  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>Примечания  
 В зависимости от модели потоков, используемых приложением `typedef` имя `CComObjectThreadModel` ссылается либо [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md). Эти классы предоставляют дополнительные `typedef` имена для ссылки на класс критический раздел.  
  
> [!NOTE]
> `CComObjectThreadModel`не ссылается на класс [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  
  
 С помощью `CComObjectThreadModel` избавляет от необходимости указывать определенный класс потоковой модели. Независимо от того, используется модель потоков вызываются соответствующие методы.  
  
 В дополнение к `CComObjectThreadModel`, библиотека ATL предоставляет `typedef` имя [CComGlobalsThreadModel](#ccomglobalsthreadmodel). Ссылаться на каждый класс `typedef` зависит потоковую модель, как показано в следующей таблице:  
  
|typedef|Последовательная обработка|Потоковое|Свободных потоков|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|С|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 Используйте `CComObjectThreadModel` в пределах одного объекта класса. Используйте `CComGlobalsThreadModel` в объекте, либо глобально доступной в программу или вы хотите защитить ресурсы модуля в нескольких потоках.  
  
##  <a name="a-nameccontainedwindowa--ccontainedwindow"></a><a name="ccontainedwindow"></a>CContainedWindow  
 Этот класс является специализацией **CContainedWindowT.**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  
  
### <a name="remarks"></a>Примечания  
 `CContainedWindow`является специализацией [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md). Если вы хотите изменить базовый класс или характеристик, используйте `CContainedWindowT` напрямую.  
  
##  <a name="a-namecpatha--cpath"></a><a name="cpath"></a>CPath  
 Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CString`.  
  
```   
typedef CPathT<CString> CPath;   
```  
  
##  <a name="a-namecpathaa--cpatha"></a><a name="cpatha"></a>CPathA  
 Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringA`.  
  
```   
typedef CPathT<CStringA> CPathA;   
```  
  
##  <a name="a-namecpathwa--cpathw"></a><a name="cpathw"></a>CPathW  
 Специализация [CPathT](../../atl/reference/cpatht-class.md) с помощью `CStringW`.  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
  
##  <a name="a-namecsimplevalarraya--csimplevalarray"></a><a name="csimplevalarray"></a>CSimpleValArray  
 Представляет массив для хранения простых типов.  
  
```   
#define CSimpleValArray CSimpleArray   
```  
  
### <a name="remarks"></a>Примечания  
 `CSimpleValArray`служит для создания и управления массивы, содержащие простые типы данных. Это простое #define из [CSimpleArray](../../atl/reference/csimplearray-class.md).  
  
##  <a name="a-namelpcurla--lpcurl"></a><a name="lpcurl"></a>LPCURL  
 Указатель на константу [CUrl](../../atl/reference/curl-class.md) объекта.  
  
```   
typedef const CUrl* LPCURL;   
```  

##  <a name="a-namedefaultthreadtraitsa--defaultthreadtraits"></a><a name="defaultthreadtraits"></a>DefaultThreadTraits
Класс характеристик потока по умолчанию.

### <a name="syntax"></a>Синтаксис
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>Примечания
Если текущий проект использует многопоточные CRT, DefaultThreadTraits определяется как CRTThreadTraits. В противном случае используется Win32ThreadTraits.
  
##  <a name="a-namelpurla--lpurl"></a><a name="lpurl"></a>LPURL  
 Указатель на [CUrl](../../atl/reference/curl-class.md) объекта.  
  
```   
typedef CUrl* LPURL;   
```  
  
## <a name="see-also"></a>См. также  
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)   
 [Функции](../../atl/reference/atl-functions.md)   
 [Глобальные переменные](../../atl/reference/atl-global-variables.md)   
 [Структуры](../../atl/reference/atl-structures.md)   
 [Макросы](../../atl/reference/atl-macros.md)   
 [Классы](../../atl/reference/atl-classes.md)
