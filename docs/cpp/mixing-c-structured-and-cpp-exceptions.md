---
title: "Сочетание исключений C++ и C (структурированные) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions, mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling, mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 074ff13ed281d30caeede227cdab2cff090fab1e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="mixing-c-structured-and-c-exceptions"></a>Сочетание исключений C (структурированные) и C++
Если требуется написать более переносимый код, не рекомендуется использовать структурированную обработку исключений в программе на языке C++. Тем не менее, иногда можно компилировать с параметром **/EHa** и комбинирование структурированных исключений и исходного кода C++, а также потребуются некоторые средства для обработки обоих типов исключений. Поскольку обработчик структурированных исключений не различает объекты или типизированные исключения, он не может обработать исключения, созданные кодом C++. Однако C++ **перехватывать** обработчики могут обрабатывать структурированные исключения. В таких, синтаксис обработки исключений C++ (**повторите**, `throw`, **перехватывать**) не принимается в компиляторе, но синтаксис структурированной обработки исключений (`__try`, `__except`, `__finally`) поддерживается компилятором C++.  
  
 В разделе [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) сведения об обработке структурированных исключений, так как исключения C++.  
  
 При комбинировании структурированных исключений и исключений C++ обратите внимание на следующее.  
  
1.  Исключения С++ и структурированные исключения невозможно комбинировать в одной функции.  
  
2.  Обработчики завершения (блоки `__finally`) выполняются всегда, даже во время очитки после создания исключения.  
  
3.  Обработка исключений C++ может перехватываться и сохраняться семантика очистки со всех модулях, скомпилированных с [/EH](../build/reference/eh-exception-handling-model.md) параметр компилятора (этот параметр разрешает семантику очистки).  
  
4.  Могут возникнуть ситуации, когда функции деструктора не вызываются для всех объектов. Например, если структурированное исключение создается при попытке вызова функции с помощью неинициализированного указателя на функцию и эта функция принимает в качестве параметров объекты, созданные перед вызовом, эти объекты не будут иметь деструкторы, вызванные во время очистки стека.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Использование setjmp или longjmp в программах на C++](../cpp/using-setjmp-longjmp.md)  
  
-   [Разница между SEH и C++ EH](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений С++](../cpp/cpp-exception-handling.md)
