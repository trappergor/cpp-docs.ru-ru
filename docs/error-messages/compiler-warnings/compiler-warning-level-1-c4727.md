---
title: Предупреждение компилятора (уровень 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 1bcc029536d2602d50178d7148332b8371db3c7f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630833"
---
# <a name="compiler-warning-level-1-c4727"></a>Предупреждение компилятора (уровень 1) C4727

"PCH с именем pch_file с той же меткой времени обнаружен в obj_file_1 и obj_file_2.  Используется первый PCH.

> [!NOTE]
> В Visual Studio 2017 и более ранних версиях предкомпилированный заголовок по умолчанию называется *stdafx. h* , а в visual Studio 2019 и более поздних версий он называется *PCH. h* по умолчанию.

C4727 возникает при компиляции нескольких компиляндов с параметром **/Yc**и в том месте, где компилятору удалось пометить все OBJ-файлы с одинаковой меткой времени PCH.

Для устранения ошибки скомпилируйте один исходный файл с параметром **/Yc/c** (создает PCH), а остальные компилируются отдельно с **/Yu/c** (использует PCH), а затем свяжите их вместе.

Итак, если вы выполнили следующие действия и создаете C4727:

::: moniker range="<=vs-2017"

**CL/CLR/GL a. cpp b. cpp c. cpp/Икстдафкс.х**

Вместо этого можно сделать следующее:

**CL/CLR/GL a. cpp/Икстдафкс.х/c**

**CL/CLR/GL b. cpp c. cpp/Юстдафкс.х/Link a. obj**

::: moniker-end

::: moniker range=">=vs-2019"

**CL/CLR/GL a. cpp b. cpp c. cpp/ИКПЧ.х**

Вместо этого можно сделать следующее:

**CL/CLR/GL a. cpp/ИКПЧ.х/c**

**CL/CLR/GL b. cpp c. cpp/ЮПЧ.х/Link a. obj**

::: moniker-end


Дополнительные сведения см. на странице

- [/Yc (создание предкомпилированного файла заголовка)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md)