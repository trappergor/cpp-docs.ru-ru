---
title: -FD (минимальное перестроение интерфейса IDE) | Документы Microsoft
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
ms.openlocfilehash: 18e31955b131e4ca22d23013565e53f83493275d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373404"
---
# <a name="fd-ide-minimal-rebuild"></a>Параметр /FD (минимальное перестроение интерфейса IDE)
**Параметр /Fd** не предоставляется пользователям только на [командной строки](../../ide/command-line-property-pages.md) страницу свойств проекта C++ **страницы свойств** диалоговое окно, если и только в том случае, если [/Gm (включение минимального перепостроения)](../../build/reference/gm-enable-minimal-rebuild.md) не выбран. **Параметр /Fd** не влияет, отличных от из среды разработки. **Параметр /Fd** не предоставляется в выходных данных **cl /?**.  
  
 Если не включить **/Gm** в среде разработки **/FD** будет использоваться. **Параметр /Fd** гарантирует наличие достаточных сведений о зависимостях в IDB-файла. **Параметр /Fd** используется только в среде разработки и не должны использоваться в командной строке или в скрипте построения.  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)