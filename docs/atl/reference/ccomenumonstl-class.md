---
title: "Класс CComEnumOnSTL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
dev_langs:
- C++
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
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
ms.openlocfilehash: 23e234f82ce8c77a6ebde50070475deeab59f362
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumonstl-class"></a>Класс CComEnumOnSTL
Этот класс определяет перечислитель COM-объекта на основе коллекции стандартной библиотеки C++.  
  
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
 Тип элемента, предоставляемых интерфейсом перечислителя.  
  
 `Copy`  
 Объект [копирование политики](../../atl/atl-copy-policy-classes.md) класса.  
  
 `CollType`  
 Класс контейнеров стандартной библиотеки C++.  
  
## <a name="remarks"></a>Примечания  
 `CComEnumOnSTL`Определяет объект перечислителя COM на основе коллекции стандартной библиотеки C++. Этот класс может использоваться сама по себе или в сочетании с [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Ниже приведены типичные шаги для использования этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>С помощью этого класса с ICollectionOnSTLImpl:  
  
- `typedef`специализации этого класса.  
  
-   Используйте `typedef` в качестве аргумента окончательного шаблона в специализации `ICollectionOnSTLImpl`.  
  
 В разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md) пример.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>С помощью этого класса, независимо от ICollectionOnSTLImpl:  
  
- `typedef`специализации этого класса.  
  
-   Используйте `typedef` как аргумент шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр `CComObject` специализации.  
  
-   Инициализация объекта-перечислителя, вызвав [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
## <a name="example"></a>Пример  
 Приведенный ниже код предоставляет универсальную функцию для создания и инициализации объекта перечислителя.  
  
 [!code-cpp[NVC_ATL_COM&#34;](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 Эта функция шаблона может использоваться для реализации `_NewEnum` свойство коллекции интерфейса, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM&#35;](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnumOnSTL` , представляет собой вектор `CComVariant`s с помощью параметра **IEnumVariant** интерфейса. **CVariantCollection** класс уточняет **CreateSTLEnumerator** для работы с объектами перечислитель этого типа.  
  
## <a name="see-also"></a>См. также  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [Образец ATLCollections: Демонстрация пользовательских классов политики копирования, ICollectionOnSTLImpl и CComEnumOnSTL](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

