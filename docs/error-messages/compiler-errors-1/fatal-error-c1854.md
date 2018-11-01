---
title: Неустранимая ошибка C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: feb385161c9bc13d89052b4947174fbdce7a0d00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457386"
---
# <a name="fatal-error-c1854"></a>Неустранимая ошибка C1854

> Нельзя перезаписать данные, сформированные во время создания предкомпилированного заголовка в объектном файле: "*filename*"

Вы указали [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md) параметр после указания [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md) параметр для одного файла.

Чтобы устранить эту проблему, как правило, задать только один файл в проекте для компиляции с помощью **/Yc** параметр, а все другие файлы для компиляции с помощью набора **/Yu** параметр. Дополнительные сведения об использовании **/Yc** вкладка и способ задать его в Интегрированной среде разработки Visual Studio, см. в разделе [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md). Дополнительные сведения об использовании предкомпилированных заголовков см. в разделе [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md).
