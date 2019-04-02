---
title: Класс CComEnumOnSTL
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: f9bf9c227984b2fdbf460f970357f395934b238c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779863"
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
[Образец ATLCollections: Демонстрирует пользовательских классов политики копирования, ICollectionOnSTLImpl и CComEnumOnSTL](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)
