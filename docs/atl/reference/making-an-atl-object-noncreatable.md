---
title: Отключение возможности создания объекта ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: b2d0a21ec9e68f76650f0f6cb78446bd93540fa2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506961"
---
# <a name="making-an-atl-object-noncreatable"></a>Отключение возможности создания объекта ATL

Можно изменить атрибуты COM-объекта на основе ATL, чтобы клиент не мог напрямую создать объект. В этом случае объект будет возвращен с помощью вызова метода для другого объекта, а не непосредственно при создании.

## <a name="to-make-an-object-noncreatable"></a>Создание несоздаваемого объекта

1. Удалите [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) для объекта. Если требуется, чтобы объект был несоздаваемым, но зарегистрированным элементом управления, замените OBJECT_ENTRY_AUTO на [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Добавьте [несоздаваемый](../../windows/attributes/noncreatable.md) атрибут в компонент coclass в IDL-файле. Пример:

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>См. также раздел

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов C++ в Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Программирование с помощью ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
