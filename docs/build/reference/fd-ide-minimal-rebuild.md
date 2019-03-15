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
ms.openlocfilehash: 323a0045ab11f23ab996d5179a135d0eb4184f20
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817443"
---
# <a name="fd-ide-minimal-rebuild"></a>Параметр /FD (минимальное перестроение интерфейса IDE)

**/Fd** не предоставляется пользователям только на [командной строки](command-line-property-pages.md) страницу свойств проекта C++ **страницы свойств** диалоговое окно, если и только в том случае, если [/Gm (включение минимального перепостроения)](gm-enable-minimal-rebuild.md) не выбран. **/Fd** не влияет, отличных от из среды разработки. **/Fd** не предоставляется в выходных данных **cl /?**.

Если не включить **/Gm** в среде разработки **/FD** будет использоваться. **/Fd** гарантирует наличие достаточных сведений о зависимостях в IDB-файла. **/Fd** используется только в среде разработки, и его не следует использовать в командной строке или сценарии сборки.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
