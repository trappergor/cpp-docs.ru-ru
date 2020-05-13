---
title: Предупреждение компилятора (уровень 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: 295a183afb24121a2abefd336f6ea92110220155
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185508"
---
# <a name="compiler-warning-level-3-c4622"></a>Предупреждение компилятора (уровень 3) C4622

перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"

Информация CodeView в указанном файле была утеряна при выполнении компиляции с параметром [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (использование предкомпилированных заголовков).

Переименуйте объектный файл (с использованием параметра [/Fo](../../build/reference/fo-object-file-name.md)) при создании или использовании файла предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.
