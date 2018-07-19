---
title: Предупреждение компилятора C4394 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05535621443770a2b414f1c4312efbc46e6be858
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276225"
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