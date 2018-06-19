---
title: Функции SafeInt | Документы Microsoft
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97edd25abca3c9e80a35745165eedc93cc13a9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889311"
---
# <a name="safeint-functions"></a>Функции SafeInt
Библиотека SafeInt предоставляет несколько функций, которые можно использовать без создания экземпляра [класс SafeInt](../windows/safeint-class.md). Если вы хотите защитить один математическую операцию от переполнения для целочисленных значений, можно использовать эти функции. Если вы хотите защиты множества математических операций, необходимо создать `SafeInt` объектов. Это более эффективный способ — создать `SafeInt` объекты, а не для используются эти функции несколько раз.  
  
 Эти функции позволяют сравнения, а также для выполнения математических операций над двумя различными типами параметров без преобразования их к одному типу.  
  
 Каждая из этих функций имеет два типа шаблонов: `T` и `U`. Каждый из этих типов может быть логическое значение, символ или целочисленный тип. Целочисленные типы могут быть подписанные или не подписанные и любых размеров из 8 бит до 64 бит.  
  
## <a name="in-this-section"></a>В этом разделе  
  
|Функция|Описание|  
|--------------|-----------------|  
|[SafeAdd](../windows/safeadd.md)|Складывает два числа и обеспечивает защиту от переполнения.|  
|[SafeCast](../windows/safecast.md)|Приводит один тип параметра в другой тип.|  
|[SafeDivide](../windows/safedivide.md)|Делит два числа и обеспечивает защиту от деления на ноль.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [ SafeNotEquals](../windows/safenotequals.md)|Сравнивает два числа. Эти функции позволяют сравнивать два различных типов чисел без изменения их типов.|  
|[SafeModulus](../windows/safemodulus.md)|Выполняет операцию остатка от деления двух чисел.|  
|[SafeMultiply](../windows/safemultiply.md)|Перемножает два числа и обеспечивает защиту от переполнения.|  
|[SafeSubtract](../windows/safesubtract.md)|Вычитает два числа и обеспечивает защиту от переполнения.|  
  
## <a name="related-sections"></a>Связанные разделы  
  
|Раздел|Описание|  
|-------------|-----------------|  
|[Класс SafeInt](../windows/safeint-class.md)|класс `SafeInt`;|  
|[Класс SafeIntException](../windows/safeintexception-class.md)|Класс исключения, относящиеся к библиотека SafeInt.|