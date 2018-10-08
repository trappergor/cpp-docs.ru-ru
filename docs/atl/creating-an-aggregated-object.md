---
title: Создание объединенного объекта | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9e11db0a9752ae7f88c5b1b21b81f0bb4c8a20f
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861230"
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

