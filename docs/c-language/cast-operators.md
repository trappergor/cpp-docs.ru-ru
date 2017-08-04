---
title: "Операторы приведения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: c1d8315270f6b69629eca55e7aa1c6198f414117
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="cast-operators"></a>Операторы приведения
Приведение типа позволяет выполнить явное преобразование типа объекта в конкретной ситуации.  
  
## <a name="syntax"></a>Синтаксис  
 *cast-expression*:  
 *unary-expression*  
  
 **(**  *type-name*  **)**  *cast-expression*  
  
 После выполнения приведения типа компилятор считает, что *cast-expression* имеет тип *type-name*. Приведение типов можно использовать для преобразования объектов любого скалярного типа в любой другой скалярный тип и из любого другого скалярного типа. Явное приведение типов ограничено теми же правилами, которые используются для неявных преобразований, как описано в статье [Преобразования назначений](../c-language/assignment-conversions.md). Дополнительные ограничения на операции приведения могут быть связаны с фактическими размерами или представлением конкретных типов. Сведения о фактических размерах целочисленных типов см. в статье [Хранение базовых типов](../c-language/storage-of-basic-types.md). Дополнительные сведения о приведении типов см. в статье [Преобразования с приведением типов](../c-language/type-cast-conversions.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор приведения типа: ()](../cpp/cast-operator-parens.md)
