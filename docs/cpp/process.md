---
title: "процесс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c50948d613a40a03d0249e1930943ef61c855b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="process"></a>процесс
Указывает, что управляемый процесс приложения должен иметь одну копию конкретной глобальной переменной, статической переменной-члена или статической локальной переменной, совместно используемой во всех доменах приложения в этом процессе. Этот сценарий в основном предназначен для использования при компиляции с параметром **/CLR: pure**, который считается устаревшим и будет удален в будущей версии компилятора. При компиляции с параметром **/CLR**, глобальные и статические переменные используются для каждого процесса по умолчанию (не обязательно должны использовать `__declspec(process)`.  
  
 Только глобальная переменная, статическая переменная-член или статическая локальная переменная собственного типа может быть помечена `__declspec(process)`.  
  
  
 `process` допустимо только при компиляции с параметром [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Если требуется, чтобы иметь собственную копию глобальной переменной каждый домен приложения, используйте [appdomain](../cpp/appdomain.md).  
  
 В разделе [домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)