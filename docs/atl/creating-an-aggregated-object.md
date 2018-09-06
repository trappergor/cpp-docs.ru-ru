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
ms.openlocfilehash: a9eb69e05ead437ed5f6c1fe2bb19b07c31daf15
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760280"
---
# <a name="creating-an-aggregated-object"></a>Создание объединенного объекта

Делегаты статистической обработки `IUnknown` вызовов, предоставляя указатель на внешний объект `IUnknown` к внутреннему объекту.

### <a name="to-create-an-aggregated-object"></a>Создание объединенного объекта

1. Добавление `IUnknown` указатель на класс и инициализируйте его в значение NULL в конструктор.

2. Переопределить [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) для создания агрегата.

3. Используйте `IUnknown` указатель, определенные на шаге 1, в качестве второго параметра для [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) макросы.

4. Переопределить [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) для освобождения `IUnknown` указатель.

> [!NOTE]
>  Если вы используете и интерфейс из агрегированных объекта во время выпуска `FinalConstruct`, следует добавить [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) макрос в определение класса объекта.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

