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
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d4f2500adaaa7941444b22d7ce548370fc370533
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="process"></a>процесс
Указывает, что управляемый процесс приложения должен иметь одну копию конкретной глобальной переменной, статической переменной-члена или статической локальной переменной, совместно используемой во всех доменах приложения в этом процессе. В основном предназначен для использования при компиляции с параметром **/CLR: pure**, так как в разделе **/CLR: pure** глобальные и статические переменные, домена приложения по умолчанию. Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать. При компиляции с параметром **/CLR**, глобальные и статические переменные используются для каждого процесса по умолчанию (не обязательно должны использовать `__declspec(process)`.  
  
 Только глобальная переменная, статическая переменная-член или статическая локальная переменная собственного типа может быть помечена `__declspec(process)`.  
  
 При компиляции с параметром **/CLR: pure**, переменные, помеченные для отдельных процессов, также должен быть объявлен как `const`. Это гарантирует, что переменные конкретных процессов не изменятся в одном домене приложения и не дадут неожиданных результатов в другом домене приложения. Основное целевое использование `__declspec(process)` — включить инициализацию времени компиляции глобальной переменной, статической переменной-члена или статической локальной переменной в **/CLR: pure**.  
  
 `process`допустимо только при компиляции с параметром [/CLR](../build/reference/clr-common-language-runtime-compilation.md) или **/CLR: pure** и не является допустимым при компиляции с параметром **/CLR: safe**.  
  
 Если требуется, чтобы иметь собственную копию глобальной переменной каждый домен приложения, используйте [appdomain](../cpp/appdomain.md).  
  
 В разделе [домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
