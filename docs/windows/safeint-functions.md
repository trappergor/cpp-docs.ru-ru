---
title: Функции SafeInt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions, SafeInt
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf9a35d2198c78290bb6e60adef40fc88fdf4879
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604432"
---
# <a name="safeint-functions"></a>Функции SafeInt

Библиотека SafeInt предоставляет ряд функций, которые можно использовать без создания экземпляра [класс SafeInt](../windows/safeint-class.md). Если вы хотите защитить от переполнения для целочисленного значения одной математической операции, можно использовать эти функции. Если вы хотите защиты множества математических операций, следует создать **SafeInt** объектов. Более эффективно, чтобы создать **SafeInt** объектов, чем для используются эти функции несколько раз.

Эти функции позволяют сравнить или выполняют математические операции над двумя различные типы параметров без преобразования их к одному типу.

Каждая из этих функций имеет два типа шаблонов: `T` и `U`. Каждый из этих типов может быть значение типа Boolean, символ или целочисленный тип. Целочисленные типы могут быть подписанные или не подписанные и любого размера, от 8-битных до 64 бит.

## <a name="in-this-section"></a>В этом разделе

|Функция|Описание:|
|--------------|-----------------|
|[SafeAdd](../windows/safeadd.md)|Складывает два числа и обеспечивает защиту от переполнения.|
|[SafeCast](../windows/safecast.md)|Преобразует один тип параметра в другой тип.|
|[SafeDivide](../windows/safedivide.md)|Делит два числа и обеспечивает защиту от деления на ноль.|
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|Сравнивает два числа. Эти функции предназначены для сравнения двух различных типов чисел без изменения их типы.|
|[SafeModulus](../windows/safemodulus.md)|Выполняет операцию взятия по модулю на двух чисел.|
|[SafeMultiply](../windows/safemultiply.md)|Перемножает два числа и обеспечивает защиту от переполнения.|
|[SafeSubtract](../windows/safesubtract.md)|Вычитает два числа и обеспечивает защиту от переполнения.|

## <a name="related-sections"></a>Связанные разделы

|Раздел|Описание:|
|-------------|-----------------|
|[Класс SafeInt](../windows/safeint-class.md)|**SafeInt** класса.|
|[Класс SafeIntException](../windows/safeintexception-class.md)|Класс исключений, определенных в библиотеку SafeInt.|