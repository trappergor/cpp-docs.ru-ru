---
title: процесс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa1ba2676ebbd04d1fc1a59d210d69efeab6658
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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