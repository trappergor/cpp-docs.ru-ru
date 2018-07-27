---
title: Класс CComEnum | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd8fe2120ad42d7df223d05a43591937ffcce6e2
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885393"
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
 *Base*  
 Перечислителя COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) интерфейса.  
  
 *piid*  
 Указатель на идентификатор интерфейса интерфейса перечислителя.  
  
 *T*  
 Тип элемента, доступные в интерфейсе перечислителя.  
  
 *Копировать*  
 Однородную [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).  
  
 *ThreadModel*  
 Потоковая модель класса. Значение по умолчанию потоковую модель глобальный объект, используемый в проекте.  
  
## <a name="remarks"></a>Примечания  
 `CComEnum` Определяет объект перечислителя COM на основе массива. Этот класс является аналогом [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) реализующий перечислитель, основанное на контейнере стандартной библиотеки C++. Стандартная последовательность действий при помощи этого класса приводятся ниже. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Чтобы использовать этот класс:  
  
- **TypeDef** специализации этого класса.  
  
-   Используйте **typedef** в качестве аргумента шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр `CComObject` специализации.  
  
-   Инициализируйте объект перечислителя, вызвав [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Возвращает интерфейс перечислителя для клиента.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
## <a name="example"></a>Пример  
 Приведенный ниже код предоставляет функцию многократно используемых для создания и инициализации объект перечислителя.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Эта функция шаблона можно использовать для реализации `_NewEnum` свойство интерфейса коллекции, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Этот код создает **typedef** для `CComEnum` , предоставляющий вектор вариантов через `IEnumVariant` интерфейс. `CVariantArrayCollection` Класс уточняет `CreateEnumerator` для работы с объектами перечислитель данного типа и передает необходимые аргументы.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Класс CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)
