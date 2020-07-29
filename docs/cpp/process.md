---
title: процесс
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: f684c9c2ddfcb0aa166e1240c5f928ee52218f45
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227209"
---
# `process`

Указывает, что управляемый процесс приложения должен иметь одну копию конкретной глобальной переменной, статической переменной-члена или статической локальной переменной, совместно используемой во всех доменах приложения в этом процессе. В основном это было предназначено для использования при компиляции с **`/clr:pure`** , что является устаревшим в Visual studio 2015 и не поддерживается в Visual studio 2017. При компиляции с **`/clr`** , глобальные и статические переменные по умолчанию используются для каждого процесса и не требуют использования **`__declspec(process)`** .

С помощью можно пометить только глобальную переменную, статическую переменную-член или статическую локальную переменную собственного типа **`__declspec(process)`** .

**`process`** допускается только при компиляции с [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) .

Если требуется, чтобы каждый домен приложения имел собственную копию глобальной переменной, используйте [домен приложения](../cpp/appdomain.md).

Дополнительные сведения см. в разделе [домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md) .

## <a name="see-also"></a>См. также статью

[`__declspec`](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
