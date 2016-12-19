---
title: "Класс _variant_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Variant"
  - "_variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t - класс"
  - "_variant_t - класс, функция-член"
  - "_variant_t - класс, операторы"
  - "VARIANT - объект"
  - "VARIANT - объект, инкапсуляция модели COM"
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс _variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Объект `_variant_t` инкапсулирует тип данных `VARIANT`.  Этот класс управляет выделением и освобождением ресурсов и осуществляет необходимые вызовы функций **VariantInit** и **VariantClear**.  
  
### Создание  
  
|||  
|-|-|  
|[\_variant\_t](../Topic/_variant_t::_variant_t.md)|Создает объект `_variant_t`.|  
  
### Операции  
  
|||  
|-|-|  
|[Attach](../cpp/variant-t-attach.md)|Помещает объект **VARIANT** в объект `_variant_t`.|  
|[Clear](../cpp/variant-t-clear.md)|Удаляет инкапсулированный объект **VARIANT**.|  
|[ChangeType](../Topic/_variant_t::ChangeType.md)|Меняет тип объекта `_variant_t` на указанный **VARTYPE**.|  
|[Detach](../cpp/variant-t-detach.md)|Отключает инкапсулированный объект **VARIANT** от данного объекта `_variant_t`.|  
|[SetString](../cpp/variant-t-setstring.md)|Присваивает строку данному объекту `_variant_t`.|  
  
### Операторы  
  
|||  
|-|-|  
|[Оператор \=](../cpp/variant-t-operator-equal.md)|Присваивает новое значение существующему объекту `_variant_t`.|  
|[Оператор \=\=, \!\=](../cpp/variant-t-relational-operators.md)|Сравнивает два объекта `_variant_t` и определяет, равны ли они.|  
|[Средства извлечения](../cpp/variant-t-extractors.md)|Извлечение данных из инкапсулированного объекта **VARIANT**.|  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## Требования  
 **Заголовок:** comutil.h  
  
 **Библиотека:** comsuppw.lib или comsuppwd.lib \(дополнительные сведения см. в разделе [\/Zc:wchar\_t \(wchar\_t – это собственный тип\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)\)  
  
## См. также  
 [Классы поддержки компилятора COM](../cpp/compiler-com-support-classes.md)