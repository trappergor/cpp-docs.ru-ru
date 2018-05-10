---
title: Функции CRT, которые не поддерживаются средой выполнения Windows | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8db95e066b68bed4288456eccb43f737f15842d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Функции CRT, которые не поддерживаются средой выполнения Windows

Многие API среды выполнения C (CRT) не могут использоваться в приложениях универсальной платформы Windows (UWP), выполняемых в среде выполнения Windows. Для сборки таких приложений используется флаг компилятора /ZW. Список неподдерживаемых функций CRT см. в статье [CRT functions not supported in Universal Windows Platform apps](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) (Функции CRT, которые не поддерживаются приложениями универсальной платформы Windows).

Все API CRT описаны в документации в статье [CRT Alphabetical Function Reference](../c-runtime-library/reference/crt-alphabetical-function-reference.md) (Алфавитный указатель функций CRT).

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
