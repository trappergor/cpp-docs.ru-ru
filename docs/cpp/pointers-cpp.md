---
title: Указатели (C++)
ms.date: 11/19/2019
description: О необработанных указателях и интеллектуальных указателях в Microsoft C.
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 485cee667fa288bff76fdeac7c9f229355c276d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371918"
---
# <a name="pointers-c"></a>Указатели (C++)

Указатель — это переменная, которая хранит адрес памяти объекта. Указатели широко используются как в C, так и в СЗ для трех основных целей:

- выделять новые объекты на куче,
- передавать функции другим функциям
- итерировать элементы в массивах или других структурах данных.

В программировании c-стиля для всех этих сценариев используются *необработанные указатели.* Тем не менее, необработанные указатели являются источником многих серьезных ошибок программирования. Таким образом, их использование настоятельно не рекомендуется, за исключением тех случаев, когда они обеспечивают значительное преимущество производительности и нет никакой двусмысленности в отношении того, какой указатель является *owning указатель,* который отвечает за исключение объекта. Современный СЗ предоставляет *интеллектуальные указатели* для распределения объектов, *итераторы* для обхода структур данных и *выражения лямбда* для прохождения функций. Используя эти языковые и библиотечные средства вместо необработанных указателей, вы сделаете вашу программу более безопасной, легкой для отладки и проще в понимании и обслуживании. Для получения дополнительной информации смотрите [выражения Smart pointers,](smart-pointers-modern-cpp.md) [Iterators](../standard-library/iterators.md)и [Lambda.](lambda-expressions-in-cpp.md)

## <a name="in-this-section"></a>В этом разделе

- [Необработанные указатели](raw-pointers.md)
- [Конст и летучие указатели](const-and-volatile-pointers.md)
- [Операторы new и delete](new-and-delete-operators.md)
- [Смарт-указатели](smart-pointers-modern-cpp.md)
- [Как: Создание и использование unique_ptr экземпляров](how-to-create-and-use-unique-ptr-instances.md)
- [Как: Создание и использование экземпляров shared_ptr](how-to-create-and-use-shared-ptr-instances.md)
- [Как: Создание и использование weak_ptr экземпляров](how-to-create-and-use-weak-ptr-instances.md)
- [Как: Создание и использование экземпляров CComPtr и CCom-IPtr](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>См. также раздел

[Iterators](../standard-library/iterators.md)</br>
[Лямбда-выражения](lambda-expressions-in-cpp.md)
