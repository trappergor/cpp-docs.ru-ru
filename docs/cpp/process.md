---
title: процесс
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: 049360dddff2b9ca2ea460b96e027e86899f1ecb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344997"
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
