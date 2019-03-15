---
title: Что делает Noncreatable объекта ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 966c7c1e42cd707726a8ca65bb80914c29ad582e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814505"
---
# <a name="making-an-atl-object-noncreatable"></a>Что делает Noncreatable объекта ATL

Атрибуты на основе ATL COM-объекта можно изменить таким образом, чтобы клиент не может напрямую создать объект. В этом случае объект будет возвращенные с помощью вызова метода на другом объекте, а не создается непосредственно.

## <a name="to-make-an-object-noncreatable"></a>Чтобы сделать объект noncreatable

1. Удалить [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) для объекта. Если объект noncreatable, но Регистрируемый элемент управления, замените OBJECT_ENTRY_AUTO с [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Добавить [noncreatable](../../windows/noncreatable.md) атрибут coclass в IDL-файл. Пример:

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>См. также

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов Visual C++](../../build/reference/visual-cpp-project-types.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
