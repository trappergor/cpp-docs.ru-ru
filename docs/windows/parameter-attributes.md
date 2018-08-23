---
title: Атрибуты параметра | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], parameter attributes
- parameter attributes
ms.assetid: 024c2dd5-49d7-4ced-a17a-c56c1bc485b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa757834e61dab89ce6ff4682bd9a390c9b650bf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598701"
---
# <a name="parameter-attributes"></a>Атрибуты параметра

Следующие атрибуты применяются к параметрам метода в классе или интерфейсе.

|Атрибут|Описание:|
|---------------|-----------------|
|[Custom](../windows/custom-cpp.md)|Позволяет определять собственный атрибут.|
|[defaultvalue](../windows/defaultvalue.md)|Позволяет задавать значение по умолчанию для типизированного необязательного параметра.|
|[first_is](../windows/first-is.md)|Указывает индекс первого элемента массива для передачи.|
|[iid_is](../windows/iid-is.md)|Указывает индекс первого элемента массива для передачи.|
|[immediatebind](../windows/immediatebind.md)|Указывает, что базы данных будет немедленно оповещаться обо всех изменений свойства объекта привязки данных.|
|[in](../windows/in-cpp.md)|Указывает, что параметр передается из вызывающей процедуры вызываемой процедуры.|
|[last_is](../windows/last-is.md)|Указывает индекс последнего элемента массива для передачи.|
|[lcid](../windows/lcid.md)|Позволяет передать код языка функции.|
|[length_is](../windows/length-is.md)|Указывает количество элементов массива для передачи.|
|[max_is](../windows/max-is.md)|Определяет максимальное значение для индекса допустимым массивом.|
|[Необязательный](../windows/optional-cpp.md)|Задает необязательный параметр для функции-члена.|
|[out](../windows/out-cpp.md)|Определяет параметры-указатели, которые возвращаются из вызываемой процедуры в вызывающую (от сервера к клиенту).|
|[Диапазон](../windows/range-cpp.md)|Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.|
|[ref](../windows/ref-cpp.md)|Определяет указатель ссылки.|
|[retval](../windows/retval.md)|Назначает параметр, который получает возвращаемое значение члена.|
|[satype](../windows/satype.md)|Указывает тип данных `SAFEARRAY` структуры.|
|[size_is](../windows/size-is.md)|Указывает объем памяти, выделенной для размера указатели, размер указателей на указатели по размеру и одно - или многомерные массивы.|
|[unique](../windows/unique-cpp.md)|Указывает уникальный указатель.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](../windows/attributes-by-usage.md)