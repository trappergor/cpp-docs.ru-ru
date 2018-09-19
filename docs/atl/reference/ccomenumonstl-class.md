---
title: Класс CComEnumOnSTL | Документация Майкрософт
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
ms.openlocfilehash: a4821ba572d2719ebba6c693cc39b96971002512
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106328"
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

*Base*<br/>
COM-перечислитель. См. в разделе [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) пример.

*piid*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, доступные в интерфейсе перечислителя.

*Копировать*<br/>
Объект [Копировать политику](../../atl/atl-copy-policy-classes.md) класса.

*CollType*<br/>
Класс контейнера стандартной библиотеки C++.

## <a name="remarks"></a>Примечания

`CComEnumOnSTL` Определяет объект перечислителя COM на основе коллекции стандартной библиотеки C++. Этот класс может использоваться сама по себе или в сочетании с [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Стандартная последовательность действий при помощи этого класса приводятся ниже. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Чтобы использовать этот класс с ICollectionOnSTLImpl:

- **TypeDef** специализации этого класса.

- Используйте **typedef** как последним аргументом шаблона в специализации `ICollectionOnSTLImpl`.

См. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md) пример.

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Чтобы использовать этот класс, независимо от ICollectionOnSTLImpl:

- **TypeDef** специализации этого класса.

- Используйте **typedef** в качестве аргумента шаблона в специализации `CComObject`.

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя, вызвав [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).

- Возвращает интерфейс перечислителя для клиента.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="example"></a>Пример

Приведенный ниже код обеспечивает общую функцию для создания и инициализации объекта перечислителя.

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Эта функция шаблона можно использовать для реализации `_NewEnum` свойство интерфейса коллекции, как показано ниже:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Этот код создает **typedef** для `CComEnumOnSTL` , предоставляющий вектор `CComVariant`s с помощью параметра `IEnumVariant` интерфейс. `CVariantCollection` Класс уточняет `CreateSTLEnumerator` для работы с объектами перечислитель этого типа.

## <a name="see-also"></a>См. также

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[ATLCollections: в нем демонстрируется пользовательских классов политики копирования, ICollectionOnSTLImpl и CComEnumOnSTL](../../visual-cpp-samples.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)
