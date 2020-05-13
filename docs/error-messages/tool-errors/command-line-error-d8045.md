---
title: Ошибка командной строки D8045
ms.date: 11/04/2016
f1_keywords:
- D8045
helpviewer_keywords:
- D8045
ms.assetid: 01c8808c-bac1-4b4d-8a90-b595f95e9318
ms.openlocfilehash: 05a2d3851e58062e1e326781a223e2f4b0346620
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196850"
---
# <a name="command-line-error-d8045"></a>Ошибка командной строки D8045

невозможно скомпилировать файл C "файл" с параметром/CLR

В C++ компиляцию, использующую **/CLR**, могут быть переданы только файлы исходного кода.  Используйте **/TP** , чтобы скомпилировать c-файл как CPP-файл; Дополнительные сведения см. в разделе [/TC,/TP,/TC,/TP (указание типа исходного файла)](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) .

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

D8045 также может возникать при компиляции приложения ATL с помощью Visual C++. Дополнительные сведения см. в разделе [инструкции. Миграция в/CLR](../../dotnet/how-to-migrate-to-clr.md) .
