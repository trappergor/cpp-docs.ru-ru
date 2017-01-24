---
title: "Функции SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции, SafeInt"
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
caps.latest.revision: 13
caps.handback.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Функции SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека SafeInt предоставляет несколько функций, которые можно использовать без создания экземпляра [Класс SafeInt](../windows/safeint-class.md).  Если требуется защита одной математических операций из переполнения целые числа, эти функции.  Если требуется защита несколько математические операции, необходимо создать объекты `SafeInt`.  Он более эффективен для создания объектов `SafeInt`, чем использовать эти несколько раз функций.  
  
 Эти функции позволяют сравнить или выполнения математических операций над 2 различных типов параметров без преобразования их в один и тот же тип первым.  
  
 Каждая из этих функций содержит 2 типа шаблона: `T` и `U`.  Каждый из этих типов может быть логическим, символом или знака.  Целочисленные типы могут быть знаковым или удаление и размер любой из 8 бит на 64 бита.  
  
## В этом подразделе  
  
|Функция|Описание|  
|-------------|--------------|  
|[SafeAdd](../windows/safeadd.md)|Добавляет 2 числа и защищает от переполнения.|  
|[SafeCast](../windows/safecast.md)|Приведения один тип параметра в другой тип.|  
|[SafeDivide](../windows/safedivide.md)|Делит 2 числа и защищает от при делении на ноль.|  
|[SafeEquals](../windows/safeequals.md), [SafeGreaterThan](../windows/safegreaterthan.md), [SafeGreaterThanEquals](../windows/safegreaterthanequals.md), [SafeLessThan](../windows/safelessthan.md), [SafeLessThanEquals](../windows/safelessthanequals.md), [SafeNotEquals](../Topic/SafeNotEquals.md)|Сравнивает числа 2.  Эти функции позволяют сравнивать 2 другого типа чисел без изменения их типов.|  
|[SafeModulus](../windows/safemodulus.md)|Выполняет операцию модуля на номерах 2.|  
|[SafeMultiply](../Topic/SafeMultiply.md)|Умножает число 2 и обеспечить защищает от переполнения.|  
|[SafeSubtract](../windows/safesubtract.md)|Вычитает 2 числа и защищает от переполнения.|  
  
## Связанные подразделы  
  
|Раздел|Описание|  
|------------|--------------|  
|[Класс SafeInt](../windows/safeint-class.md)|Класс `SafeInt`.|  
|[Класс SafeIntException](../windows/safeintexception-class.md)|Для класса исключений в библиотеке SafeInt.|