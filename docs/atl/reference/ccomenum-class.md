---
title: Класс Ккоменум
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 7252eb2fa5d34618a1c38484a2506bae27a1106a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497213"
---
# <a name="ccomenum-class"></a>Класс Ккоменум

Этот класс определяет объект перечислителя COM, основанный на массиве.

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

*Из*<br/>
Интерфейс перечислителя COM. Пример см. в разделе [иенумстринг](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, предоставляемого интерфейсом перечислителя.

*Copy*.<br/>
Однородный [класс политики копирования](../../atl/atl-copy-policy-classes.md).

*среадмодел*<br/>
Потоковая модель класса. По умолчанию для этого параметра используется модель потоков глобальных объектов, используемая в проекте.

## <a name="remarks"></a>Примечания

`CComEnum`Определяет объект перечислителя COM на основе массива. Этот класс аналогичен [ккоменумонстл](../../atl/reference/ccomenumonstl-class.md) , который реализует перечислитель на основе контейнера C++ стандартной библиотеки. Ниже приведены типичные действия по использованию этого класса. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Чтобы использовать этот класс, сделайте следующее:

- **Определение** специализации этого класса.

- Используйте **typedef** в качестве аргумента шаблона в специализации `CComObject`.

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя путем вызова [ккоменумимпл:: init](../../atl/reference/ccomenumimpl-class.md#init).

- Возврат интерфейса перечислителя клиенту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[ккоменумимпл](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

## <a name="example"></a>Пример

Приведенный ниже код предоставляет многократно используемую функцию для создания и инициализации объекта перечислителя.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Эта функция шаблона может использоваться для реализации `_NewEnum` свойства интерфейса коллекции, как показано ниже:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Этот код создает **typedef** для `CComEnum` , предоставляющий вектор вариантов через `IEnumVariant` интерфейс. `CVariantArrayCollection` Класс просто `CreateEnumerator` специализируется на работе с объектами перечислителя этого типа и передает необходимые аргументы.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)<br/>
[ккомобжектсреадмодел](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)
