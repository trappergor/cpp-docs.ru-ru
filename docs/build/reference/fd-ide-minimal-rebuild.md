---
title: Параметр /FD (минимальное перестроение интерфейса IDE)
ms.date: 04/08/2019
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: ac63b021dc0cb9ee5964af7fa2e168f710653979
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424057"
---
# <a name="fd-ide-minimal-rebuild"></a>Параметр /FD (минимальное перестроение интерфейса IDE)

**/Fd** доступны только для пользователей в [командной строки](command-line-property-pages.md) страницу свойств C++ проекта **страницы свойств** диалоговое окно. Он будет доступен, только если не рекомендуется и по умолчанию отключено [/Gm (включение минимального перепостроения)](gm-enable-minimal-rebuild.md) параметр не выбран. **/Fd** не влияет, отличных от из среды разработки. **/Fd** не предоставляется в выходных данных `cl /?`.

Если не включить устаревший **/Gm** параметр в среде разработки **/FD** используется. **/Fd** гарантирует IDB-файла имеет достаточные сведения о зависимостях. **/Fd** используется только в среде разработки и не должны использоваться из командной строки или в скрипте построения.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
