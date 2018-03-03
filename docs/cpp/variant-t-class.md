---
title: "Класс _variant_t | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57a4d7e4019e742ff8adc50bb78a926dff34d55a
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="variantt-class"></a>Класс _variant_t
**Блок, относящийся только к системам Microsoft**  
  
 Объект `_variant_t` инкапсулирует тип данных `VARIANT`. Данный класс управляет выделением и освобождением ресурсов и осуществляет необходимые вызовы функций **VariantInit** и **VariantClear** соответствующим образом.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Создает объект `_variant_t`.|  
  
### <a name="operations"></a>Операции  
  
|||  
|-|-|  
|[Attach](../cpp/variant-t-attach.md)|Присоединяет **VARIANT** объекта в `_variant_t` объекта.|  
|[Очистить](../cpp/variant-t-clear.md)|Удаляет инкапсулированный **VARIANT** объекта.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Изменяет тип `_variant_t` на указанный **VARTYPE**.|  
|[Detach](../cpp/variant-t-detach.md)|Отключает инкапсулированный **VARIANT** объекта из этого `_variant_t` объекта.|  
|[SetString](../cpp/variant-t-setstring.md)|Присваивает строку данному объекту `_variant_t`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[Оператор =](../cpp/variant-t-operator-equal.md)|Присваивает новое значение существующему объекту `_variant_t`.|  
|[оператор ==,! =](../cpp/variant-t-relational-operators.md)|Сравнивает два объекта `_variant_t` и определяет, равны ли они.|  
|[Средства извлечения](../cpp/variant-t-extractors.md)|Извлечение данных из инкапсулированного **VARIANT** объекта.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Header:** \<comutil.h>  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)