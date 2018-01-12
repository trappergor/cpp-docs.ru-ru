---
title: "Класс CComEnum | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs: C++
helpviewer_keywords: CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 792c5ff95858936d38d9a87350dd3ca405c5ec66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomenum-class"></a>Класс CComEnum
Этот класс определяет COM-объект перечислителя, на основе массива.  
  
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
 Тип элемента, доступные в интерфейсе перечислителя.  
  
 `Copy`  
 Однородную [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Потоковая модель класса. Этот параметр по умолчанию модели глобальный объект потока, используемые в вашем проекте.  
  
## <a name="remarks"></a>Примечания  
 `CComEnum`Определяет COM-объект перечислителя, на основе массива. Этот класс является аналогом [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) которого реализует перечислитель, основанное на контейнере стандартной библиотеки C++. Ниже описаны типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>С помощью этого класса:  
  
- `typedef`специализации этого класса.  
  
-   Используйте `typedef` в качестве аргумента шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр класса `CComObject` специализации.  
  
-   Инициализируйте объект перечислителя, вызвав [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
## <a name="example"></a>Пример  
 Приведенный ниже код предоставляет функцию для повторного использования, для создания и инициализации объекта перечислителя.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Эта функция шаблона можно использовать для реализации `_NewEnum` свойство интерфейса коллекции, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnum` , представляет собой вектор **VARIANT**s через **IEnumVariant** интерфейса. **CVariantArrayCollection** класс уточняет **CreateEnumerator** для работы с объектами перечислитель данного типа и передает необходимые аргументы.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Класс CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)
