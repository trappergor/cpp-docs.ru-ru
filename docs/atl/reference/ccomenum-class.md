---
title: Класс CComEnum
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 4d83b06f37c132c0d2325304e2cc155ccb490690
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290369"
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

*Base*<br/>
COM-интерфейса перечислителя. См. в разделе [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) пример.

*piid*<br/>
Указатель на идентификатор интерфейса интерфейса перечислителя.

*T*<br/>
Тип элемента, доступные в интерфейсе перечислителя.

*Копировать*<br/>
Однородную [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).

*ThreadModel*<br/>
Потоковая модель класса. Значение по умолчанию потоковую модель глобальный объект, используемый в проекте.

## <a name="remarks"></a>Примечания

`CComEnum` Определяет объект перечислителя COM на основе массива. Этот класс является аналогом [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) реализующий перечислитель, основанное на контейнере стандартной библиотеки C++. Стандартная последовательность действий при помощи этого класса приводятся ниже. Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Чтобы использовать этот класс:

- **TypeDef** специализации этого класса.

- Используйте **typedef** в качестве аргумента шаблона в специализации `CComObject`.

- Создайте экземпляр `CComObject` специализации.

- Инициализируйте объект перечислителя, вызвав [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).

- Возвращает интерфейс перечислителя для клиента.

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

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[Класс CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)
