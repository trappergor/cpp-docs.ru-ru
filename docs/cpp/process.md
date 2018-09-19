---
title: процесс | Документация Майкрософт
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
ms.openlocfilehash: 65ae8eef828a8abd4bf726c99850089c0f30b71b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032572"
---
# <a name="process"></a>процесс

Указывает, что управляемый процесс приложения должен иметь одну копию конкретной глобальной переменной, статической переменной-члена или статической локальной переменной, совместно используемой во всех доменах приложения в этом процессе. Это было в основном предназначен для использования при компиляции с параметром **/CLR: pure**, который является устаревшей в Visual Studio 2017 и не поддерживается в Visual Studio 2017. При компиляции с параметром **/CLR**, глобальные и статические переменные, на уровне процесса по умолчанию и не обязательно должны использовать **__declspec(process)**.

Только глобальная переменная, статическая переменная-член или статическая локальная переменная собственного типа можно пометить **__declspec(process)**.

**процесс** допустим только при компиляции с параметром [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

Каждый домен приложения, чтобы иметь собственную копию глобальной переменной, используйте [appdomain](../cpp/appdomain.md).

См. в разделе [домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md) Дополнительные сведения.

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
