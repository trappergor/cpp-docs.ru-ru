---
title: Приложения UWP, среда выполнения Windows и среда выполнения C | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29e1a67ce57e4ddf726ba64923bbe5a95b5b2f1c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410844"
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>Приложения UWP, среда выполнения Windows и среда выполнения C

Приложения универсальной платформы Windows (UWP) — это программы, запускаемые в среде выполнения Windows на базе [!INCLUDE[win8](../build/reference/includes/win8_md.md)]. Среда выполнения Windows — это надежное окружение, контролирующее функции, переменные и ресурсы, доступные приложению UWP. Но эта среда намеренно содержит ограничения, не позволяющие использовать в приложениях UWP большинство функций библиотеки времени выполнения C (CRT).

Среда выполнения Windows не поддерживает следующие возможности CRT.

- Большая часть функций CRT, связанных с неподдерживаемой функциональностью.

   Например, приложение UWP не может создать процесс с помощью семейств подпрограмм **exec** и **spawn**.

   Если функция CRT не поддерживается в приложении UWP, это будет отражено в справочной статье по этой функции.

- Большая часть функций, работающих с многобайтовыми символами и строками.

   Однако тексты Юникод и ANSI поддерживаются.

- Консольные приложения и аргументы командной строки.

   Однако классические приложения по-прежнему поддерживают консоль и аргументы командной строки.

- Переменные среды.

- Понятие текущего рабочего каталога.

- Приложения и DLL-библиотеки UWP, которые имеют статическую связь с CRT и сборка которых выполняется с использованием параметров компилятора [/MT](../build/reference/md-mt-ld-use-run-time-library.md) или `/MTd`.

   Это означает, что приложение использует многопоточную статическую версию CRT.

- Приложения, которые создаются с использованием параметра компилятора [/MDd](../build/reference/md-mt-ld-use-run-time-library.md).

   То есть, отладочная, многопоточная и DLL-специфичная версия CRT. Такое приложение не поддерживается в среде выполнения Windows.

Полный список функций CRT, которые недоступны в приложениях UWP, и предлагаемые альтернативы см. в статье [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>См. также

[Совместимость](../c-runtime-library/compatibility.md)<br/>
[Функции CRT, которые не поддерживаются средой выполнения Windows](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
