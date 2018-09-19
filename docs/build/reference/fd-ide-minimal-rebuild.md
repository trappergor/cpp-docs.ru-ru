---
title: -FD (минимальное перестроение интерфейса IDE) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74fb35ec25bed808e2165498c00b65723aba5bac
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702446"
---
# <a name="fd-ide-minimal-rebuild"></a>Параметр /FD (минимальное перестроение интерфейса IDE)

**/Fd** не предоставляется пользователям только на [командной строки](../../ide/command-line-property-pages.md) страницу свойств проекта C++ **страницы свойств** диалоговое окно, если и только в том случае, если [/Gm (включение минимального перепостроения)](../../build/reference/gm-enable-minimal-rebuild.md) не выбран. **/Fd** не влияет, отличных от из среды разработки. **/Fd** не предоставляется в выходных данных **cl /?**.

Если не включить **/Gm** в среде разработки **/FD** будет использоваться. **/Fd** гарантирует наличие достаточных сведений о зависимостях в IDB-файла. **/Fd** используется только в среде разработки, и его не следует использовать в командной строке или сценарии сборки.

## <a name="see-also"></a>См. также

[Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)
[параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)