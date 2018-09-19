---
title: Неустранимая ошибка C1854 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83450169ec928bb77e46916619c84b3b9a3443a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029394"
---
# <a name="fatal-error-c1854"></a>Неустранимая ошибка C1854

> Нельзя перезаписать данные, сформированные во время создания предкомпилированного заголовка в объектном файле: "*filename*"

Вы указали [/Yu (использование файла предкомпилированного заголовка)](../../build/reference/yu-use-precompiled-header-file.md) параметр после указания [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md) параметр для одного файла.

Чтобы устранить эту проблему, как правило, задать только один файл в проекте для компиляции с помощью **/Yc** параметр, а все другие файлы для компиляции с помощью набора **/Yu** параметр. Дополнительные сведения об использовании **/Yc** вкладка и способ задать его в Интегрированной среде разработки Visual Studio, см. в разделе [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md). Дополнительные сведения об использовании предкомпилированных заголовков см. в разделе [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md).
