---
title: "Предупреждение компилятора C4394 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab51a4f818e8eb8a94150424124a5c96ebaf241
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4394"></a>Предупреждение компилятора C4394
«функция»: символ по доменам приложения не следует помечать с помощью __declspec(dllexport)  
  
 Функция, помеченная [appdomain](../../cpp/appdomain.md) `__declspec` модификатор компилируется в код MSIL (не в машинный код) и таблицы экспорта ([Экспорт](../../windows/export.md) `__declspec` модификатор) не поддерживаются для управляемых функций.  
  
 Можно объявить управляемой функции открытый доступ. Дополнительные сведения см. в разделе [введите видимость](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [видимость членов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 всегда выдается как ошибка.  Можно отключить это предупреждение с `#pragma warning` или **/wd**; в разделе [предупреждение](../../preprocessor/warning.md) или  [ /w, помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, / wv, / WX (порог предупреждений)](../../build/reference/compiler-option-warning-level.md)для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4394.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```