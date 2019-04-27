---
title: Создание объединенного объекта
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: 4be8d0e852da91b58125dc01d44eed4560b2b8d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250762"
---
# <a name="creating-an-aggregated-object"></a>Создание объединенного объекта

Делегаты статистической обработки `IUnknown` вызовов, предоставляя указатель на внешний объект `IUnknown` к внутреннему объекту.

## <a name="to-create-an-aggregated-object"></a>Создание объединенного объекта

1. Добавление `IUnknown` указатель на класс и инициализируйте его в значение NULL в конструктор.

1. Переопределить [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) для создания агрегата.

1. Используйте `IUnknown` указатель, определенные на шаге 1, в качестве второго параметра для [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) макросы.

1. Переопределить [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) для освобождения `IUnknown` указатель.

> [!NOTE]
> Если вы используете и интерфейс из агрегированных объекта во время выпуска `FinalConstruct`, следует добавить [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) макрос в определение класса объекта.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)
