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
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3c074061955adbb1682bb7d96345a31fcf8f04e7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-class"></a>Класс _variant_t
**Блок, относящийся только к системам Майкрософт**  
  
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
 **Заголовок:** comutil.h  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (в разделе [/Zc: wchar_t (wchar_t – это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) для получения дополнительной информации)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)
