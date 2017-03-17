---
title: "Класс CComEnum | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 72c172d7a619bb4fd1bd265e465653b691c0bc7b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenum-class"></a>Класс CComEnum
Этот класс определяет перечислитель COM-объекта на основе массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
 public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Перечислитель COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) интерфейса.  
  
 `piid`  
 Указатель на идентификатор интерфейса интерфейс перечислителя.  
  
 `T`  
 Тип элемента, предоставляемых интерфейсом перечислителя.  
  
 `Copy`  
 Однородную [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Потоковая модель класса. Этот параметр по умолчанию используется в проекте модели потоков глобального объекта.  
  
## <a name="remarks"></a>Примечания  
 `CComEnum`Определяет объект перечислителя COM на основе массива. Этот класс является аналогом [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) , реализующий перечислитель, основанное на контейнере стандартной библиотеки C++. Ниже приведены типичные шаги для использования этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>С помощью этого класса:  
  
- `typedef`специализации этого класса.  
  
-   Используйте `typedef` как аргумент шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр `CComObject` специализации.  
  
-   Инициализация объекта-перечислителя, вызвав [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
## <a name="example"></a>Пример  
 Приведенный ниже код предоставляет функцию для повторного использования, для создания и инициализации объекта перечислителя.  
  
 [!code-cpp[NVC_ATL_COM&#32;](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Эта функция шаблона может использоваться для реализации `_NewEnum` свойство коллекции интерфейса, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM&#33;](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnum` , представляет собой вектор **VARIANT**s через **IEnumVariant** интерфейса. **CVariantArrayCollection** класс уточняет **CreateEnumerator** для работы с объектами перечислитель данного типа и передает необходимые аргументы.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Класс CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

