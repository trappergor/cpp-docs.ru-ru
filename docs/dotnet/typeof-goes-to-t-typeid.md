---
title: "Переход TypeOf в T::typeid | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 09ec4aef4c8bc68f8a808193b30d86b8519ba881
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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