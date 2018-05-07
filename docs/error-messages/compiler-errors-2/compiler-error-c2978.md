---
title: Ошибка компилятора C2978 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2978
dev_langs:
- C++
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cabf938343b375fdd27647711bb3e5b1d1f16d39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2978"></a>Ошибка компилятора C2978
синтаксическая ошибка: требуется "ключевое_слово1" или "ключевое_слово2"; обнаружен тип "ключевое_слово3"; параметры, не являющиеся параметрами типа, не поддерживаются в универсальных классах  
  
 Универсальный класс был объявлен неправильно. В разделе [универсальных типов](../../windows/generics-cpp-component-extensions.md)Дополнительные сведения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2978:  
  
```  
// C2978.cpp  
// compile with: /clr /c  
generic <ref class T>   // C2978  
// try the following line instead  
// generic <typename T>   // OK  
ref class Utils {  
   static void sort(T elems, size_t size);  
};  
  
generic <int>  
// try the following line instead  
// generic <class T>  
ref class Utils2 {  
   static void sort(T elems, size_t size);  
};  
```