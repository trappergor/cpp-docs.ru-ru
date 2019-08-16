---
title: Класс Ккоменумонстл
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: ab11ea5e5347c9c8684e8710e9742fdbcad8a46b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497164"
---
# <a name="ccomenumonstl-class"></a>Класс Ккоменумонстл

Этот класс определяет объект перечислителя COM на основе коллекции C++ стандартной библиотеки.

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

*Из*<br/>
Перечислитель COM. Пример см. в разделе [иенумстринг](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, предоставляемого интерфейсом перечислителя.

*Copy*.<br/>
Класс [политики копирования](../../atl/atl-copy-policy-classes.md) .

*коллтипе*<br/>
Класс C++ контейнера стандартной библиотеки.

## <a name="remarks"></a>Примечания

`CComEnumOnSTL`Определяет объект перечислителя COM на основе коллекции C++ стандартной библиотеки. Этот класс можно использовать самостоятельно или в сочетании с [иколлектиононстлимпл](../../atl/reference/icollectiononstlimpl-class.md). Ниже приведены типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Чтобы использовать этот класс с Иколлектиононстлимпл:

- **Определение** специализации этого класса.

- Используйте **typedef** в качестве окончательного аргумента шаблона в специализации `ICollectionOnSTLImpl`.

Пример см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md) .

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Использование этого класса независимо от Иколлектиононстлимпл:

- **Определение** специализации этого класса.

- Используйте **typedef** в качестве аргумента шаблона в специализации `CComObject`.

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя путем вызова [иенумонстлимпл:: init](../../atl/reference/ienumonstlimpl-class.md#init).

- Возврат интерфейса перечислителя клиенту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

## <a name="example"></a>Пример

Приведенный ниже код предоставляет универсальную функцию для управления созданием и инициализацией объекта перечислителя.

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Эта функция шаблона может использоваться для реализации `_NewEnum` свойства интерфейса коллекции, как показано ниже:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Этот код создает **typedef** `CComEnumOnSTL` для, который предоставляет вектор из `CComVariant`с помощью `IEnumVariant` интерфейса. `CVariantCollection` Класс просто `CreateSTLEnumerator` специализируется на работе с объектами перечислителя этого типа.

## <a name="see-also"></a>См. также

[иенумонстлимпл](../../atl/reference/ienumonstlimpl-class.md)<br/>
[Пример Атлколлектионс: Демонстрирует классы политики Иколлектиононстлимпл, Ккоменумонстл и пользовательского копирования](../../overview/visual-cpp-samples.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)
