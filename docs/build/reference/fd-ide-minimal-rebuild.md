---
title: Параметр /FD (минимальное перестроение интерфейса IDE)
ms.date: 11/04/2016
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: a902096bf13105e6a6a66b7bd3ccc56b8f7cf624
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433597"
---
# <a name="fd-ide-minimal-rebuild"></a>Параметр /FD (минимальное перестроение интерфейса IDE)

**/Fd** не предоставляется пользователям только на [командной строки](../../ide/command-line-property-pages.md) страницу свойств проекта C++ **страницы свойств** диалоговое окно, если и только в том случае, если [/Gm (включение минимального перепостроения)](../../build/reference/gm-enable-minimal-rebuild.md) не выбран. **/Fd** не влияет, отличных от из среды разработки. **/Fd** не предоставляется в выходных данных **cl /?**.

Если не включить **/Gm** в среде разработки **/FD** будет использоваться. **/Fd** гарантирует наличие достаточных сведений о зависимостях в IDB-файла. **/Fd** используется только в среде разработки, и его не следует использовать в командной строке или сценарии сборки.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](../../build/reference/output-file-f-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)