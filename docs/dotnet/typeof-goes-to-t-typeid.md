---
title: Переход TypeOf в T::typeid | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ae9f772a68735555748e6edbeb6196f1a73d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164522"
---
# <a name="typeof-goes-to-ttypeid"></a>Переход typeof в T::typeid
`typeof` Оператор, используемый в управляемых расширениях для C++ причинах замещения `typeid` ключевого слова в Visual C++.  
  
 В управляемых расширениях `__typeof()` оператор возвращает связанный `Type*` объекта при передаче ему имени управляемого типа. Пример:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 В новом синтаксисе `__typeof` будет заменен дополнительной формы `typeid` , возвращающий `Type^` при указании управляемого типа.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C + +/ CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)