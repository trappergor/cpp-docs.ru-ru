---
title: Класс _variant_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9315c2bb946cd80dd68153543ad6ae532ec9b7a0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460876"
---
# <a name="variantt-class"></a>Класс _variant_t
**Блок, относящийся только к системам Microsoft**  
  
 Объект **_variant_t** инкапсулирует `VARIANT` тип данных. Этот класс управляет выделением и освобождением ресурсов и вызывает функцию `VariantInit` и `VariantClear` соответствующим образом.  
  
### <a name="construction"></a>Создание экземпляра  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Создает **_variant_t** объекта.|  
  
### <a name="operations"></a>Операции  
  
|||  
|-|-|  
|[Attach](../cpp/variant-t-attach.md)|Присоединяет `VARIANT` в коллекцию **_variant_t** объекта.|  
|[Очистить](../cpp/variant-t-clear.md)|Удаляет инкапсулированный `VARIANT` объекта.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Изменяет тип **_variant_t** на указанный `VARTYPE`.|  
|[Detach](../cpp/variant-t-detach.md)|Отключает инкапсулированный `VARIANT` из данного **_variant_t** объекта.|  
|[SetString](../cpp/variant-t-setstring.md)|Присваивает строку данному **_variant_t** объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](../cpp/variant-t-operator-equal.md)|Назначает новое значение к существующему **_variant_t** объекта.|  
|[оператор ==,! =](../cpp/variant-t-relational-operators.md)|Сравнение двух **_variant_t** объектов на Признак равенства или неравенства.|  
|[Средства извлечения](../cpp/variant-t-extractors.md)|Извлечение данных из инкапсулированного `VARIANT` объекта.|  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<comutil.h >  
  
 **LIB:** comsuppw.lib или comsuppwd.lib (см. в разделе [/Zc: wchar_t (wchar_t — собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Дополнительные сведения)  
  
## <a name="see-also"></a>См. также  
 [Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)