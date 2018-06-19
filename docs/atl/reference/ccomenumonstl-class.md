---
title: Класс CComEnumOnSTL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs:
- C++
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c380ba7b6c2c13f178a15263e1ff510f9f3c31c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363302"
---
# <a name="ccomenumonstl-class"></a>Класс CComEnumOnSTL
Этот класс определяет COM-объект перечислителя, на основе коллекции стандартной библиотеки C++.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>  
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
 T,
    Copy,
 CollType>,
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
 Объект [копирование политики](../../atl/atl-copy-policy-classes.md) класса.  
  
 `CollType`  
 Класс контейнера стандартной библиотеки C++.  
  
## <a name="remarks"></a>Примечания  
 `CComEnumOnSTL` Определяет COM-объект перечислителя, на основе коллекции стандартной библиотеки C++. Этот класс можно использовать сам по себе или в сочетании с [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Ниже описаны типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Чтобы использовать этот класс ICollectionOnSTLImpl:  
  
- `typedef` специализации этого класса.  
  
-   Используйте `typedef` как последним аргументом шаблона в специализации `ICollectionOnSTLImpl`.  
  
 В разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md) в качестве примера.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>С помощью этого класса, независимо от ICollectionOnSTLImpl:  
  
- `typedef` специализации этого класса.  
  
-   Используйте `typedef` в качестве аргумента шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр класса `CComObject` специализации.  
  
-   Инициализируйте объект перечислителя, вызвав [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
## <a name="example"></a>Пример  
 Приведенный ниже код представляет собой универсальный функцию для создания и инициализации объекта перечислителя:  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 Эта функция шаблона можно использовать для реализации `_NewEnum` свойство интерфейса коллекции, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnumOnSTL` , представляет собой вектор `CComVariant`s с помощью параметра **IEnumVariant** интерфейса. **CVariantCollection** класс уточняет **CreateSTLEnumerator** для работы с объектами перечислитель этого типа.  
  
## <a name="see-also"></a>См. также  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [Образец ATLCollections: Демонстрация ICollectionOnSTLImpl CComEnumOnSTL и пользовательских классов политики копирования](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)
